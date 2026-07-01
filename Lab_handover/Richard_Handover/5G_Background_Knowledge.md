# 5G_Background_Knowledge

## Table Of Contents



### USRP

這塊板子頻道頻寬最高只支援到56MHz
<img width="1123" height="764" alt="image" src="https://github.com/user-attachments/assets/08508cb2-127c-44e1-b8e3-cacfd65c9980" />


### FR1

> Refrence: https://www.sharetechnote.com/html/5G/5G_FR_Bandwidth.html

<img width="773" height="163" alt="image" src="https://github.com/user-attachments/assets/cbdaeba6-ef20-473c-9b6b-750f00d56fe6" />

5G常用頻段為 40/100 MHz

所以OAI指令裡
```
sudo ./nr-uesoftmodem -r 106 --numerology 1 --band 78 -C 3619200000 --uicc0.imsi 001010000000001 --rfsim --rfsimulator.serveraddr 127.0.0.1

```
- `-r`: Number of Resource Block
- `--numerology 1`: 通常使用30kHz
<img width="247" height="159" alt="image" src="https://github.com/user-attachments/assets/cc481e24-5688-4e37-845d-b5a7e077a3d4" />

- `--band 78`: 使用n78頻段

|頻段	|雙工模式|	ƒ（MHz）|	別名|	子集頻段|	上行（MHz）	|下行（MHz）|	雙工間隔（MHz）	|頻道頻寬（MHz）|
|---|---|---|---|---|---|---|---|---|
|n48|	TDD	|3500	|CBRS（美）|	n77, n78	|3550 – 3700	|3550 – 3700|不適用|5, 10, 15, 20, 30, 40, 50, 60, 70, 80, 90, 100|
|n78|	TDD|	3500|	C波段|	n77|	3300 – 3800	|3300 – 3800|不適用	|10, 15, 20, 25, 30, 40, 50, 60, 70, 80, 90, 100	|

目前台灣主流5G使用n78/n79頻段，所以任何設備都可以接收到此5G訊號。

所以6/29有掃描到一個UE，此UE為pegatron dongle，且成功進行攻擊使dongle無法連線

但G Reigns基站使用n48頻段，而原本接在G Reigns的RU是foxconn RU，但這個RU沒有n48的韌體，所以不支援n48 ，必須改用pegatron RU


在attacker裡，鎖頻是為了確保MTK UE鎖定我們這台基地台

- n48: 屬於美國的免費頻段

- 公民寬頻無線電服務(CBRS) 是美國開創性的頻寬共享系統，允許用戶使用3,550-3,700MHz 的頻寬來部署5G 私有網絡


### 鎖頻運算式

#### 場景
- Band:  n78
- Bandwidth: 40 MHz
- SCS: 30 kHz (106 PRBs)
- downlink_frequency = 3619200000;      # 3619.2 MHz
- absoluteFrequencySSB = 641280;        # SSB ARFCN (GSCN = 7929)

  <img width="639" height="519" alt="image" src="https://github.com/user-attachments/assets/1a447205-4ce5-41cf-87ab-59c9f155ba64" />

因此Attacker指令要鎖定在
```
-C 3619200000
```


### ssb offset
實際上ssb相對於中心頻的位移
```
get_ssb_offset_to_pointA
```

<img width="1028" height="466" alt="image" src="https://github.com/user-attachments/assets/e389a763-9fa4-46ca-be59-b446b15f5409" />


#### Ex 
<img width="786" height="611" alt="image" src="https://github.com/user-attachments/assets/8a3b8173-b25d-4d3a-96a6-01d4e2468b32" />

ssb = 12*86 /2 = 516

所以指令要寫
```
-- ssb 516
```

### nemo ue
可以打開來看掃到的sib1

在三星的手機裡灌一套分析軟體，可以看到基地台資訊

理論上全部的基站都可以攻擊，但礙於USRP發射的訊號 基站太遠都收不到

所以條件是基地台的rx gain要夠大
