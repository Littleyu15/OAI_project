# 5G Background Knowledge (5G 基礎知識與實務操作)

本文檔紀錄了 5G 網路相關的基礎知識、OAI (OpenAirInterface) 參數設定，以及硬體設備與頻段的實務配置。

## 目錄 (Table Of Contents)
1. [USRP 硬體限制](#1-usrp-硬體限制)
2. [FR1 頻段與 OAI 參數設定](#2-fr1-頻段與-oai-參數設定)
3. [頻段應用與硬體實務 (n48 vs n78)](#3-頻段應用與硬體實務-n48-vs-n78)
4. [鎖頻運算與設定](#4-鎖頻運算與設定)
5. [SSB Offset 計算](#5-ssb-offset-計算)
6. [Nemo UE 與訊號測試](#6-nemo-ue-與訊號測試)

---

## 1. USRP 硬體限制
此 USRP 開發板的頻道頻寬 (Channel Bandwidth) 最高僅支援至 **56 MHz**。

<img width="1123" height="764" alt="image" src="https://github.com/user-attachments/assets/08508cb2-127c-44e1-b8e3-cacfd65c9980" />

---

## 2. FR1 頻段與 OAI 參數設定
> **Reference:** [ShareTechnote - 5G FR Bandwidth](https://www.sharetechnote.com/html/5G/5G_FR_Bandwidth.html)

<img width="773" height="163" alt="image" src="https://github.com/user-attachments/assets/cbdaeba6-ef20-473c-9b6b-750f00d56fe6" />

5G 實務上常用的頻寬為 **40 MHz / 100 MHz**。
在 OAI 環境中，啟動 UE 的指令設定如下：

```bash
sudo ./nr-uesoftmodem -r 106 --numerology 1 --band 78 -C 3619200000 --uicc0.imsi 001010000000001 --rfsim --rfsimulator.serveraddr 127.0.0.1
```

- `-r`: Number of Resource Block
- `--numerology 1`: 通常使用30kHz
- `--band 78`: 指定使用 n78 頻段。


### 常見頻段比較表
|頻段	|雙工模式|	ƒ（MHz）|	別名|	子集頻段|	上行（MHz）	|下行（MHz）|	雙工間隔（MHz）	|頻道頻寬（MHz）|
|---|---|---|---|---|---|---|---|---|
|n48|	TDD	|3500	|CBRS（美）|	n77, n78	|3550 – 3700	|3550 – 3700|不適用|5, 10, 15, 20, 30, 40, 50, 60, 70, 80, 90, 100|
|n78|	TDD|	3500|	C波段|	n77|	3300 – 3800	|3300 – 3800|不適用	|10, 15, 20, 25, 30, 40, 50, 60, 70, 80, 90, 100	|

### 3. 頻段應用與硬體實務 (n48 vs n78)
- n78 頻段：目前台灣主流的 5G 頻段包含 n78 與 n79，因此市面上大多數設備皆可接收此 5G 訊號。
- n48 頻段 (CBRS)：屬於美國的免費頻段。公民寬頻無線電服務 (CBRS) 是美國的一種頻寬共享系統，允許用戶使用 3550 - 3700 MHz 的頻段來部署 5G 專網 (Private Network)。

#### 實務測試紀錄
- G Reigns 基站與 RU 配置：G Reigns 基地台使用 n48 頻段。原先連接的 Foxconn RU 因缺乏 n48 的韌體而不支援該頻段，因此實務上必須替換為 Pegatron RU。

- 安全性測試 (6/29)：掃描到一個作為 UE 的 Pegatron dongle，並成功對其進行攻擊，導致該 dongle 無法連線。

- 鎖頻策略：在攻擊端 (Attacker) 設定鎖頻，是為了確保 MTK UE 能穩定鎖定在我們自建的基地台上。

### 4. 鎖頻運算與設定
在針對特定目標進行設定時，需計算並指定準確的下行頻率 (Downlink Frequency)。

#### 測試場景設定
- Band:  n78
- Bandwidth: 40 MHz
- SCS: 30 kHz (106 PRBs)
- downlink_frequency = 3619200000;      # 3619.2 MHz
- absoluteFrequencySSB = 641280;        # SSB ARFCN (GSCN = 7929)

轉換過程如下

 <img width="639" height="519" alt="image" src="https://github.com/user-attachments/assets/1a447205-4ce5-41cf-87ab-59c9f155ba64" />
 
- 因此，攻擊端 (Attacker) 的指令需要鎖定在該頻率：

```
-C 3619200000
```

### 5. SSB Offset 計算
`ssb_offset` 實際上是指 SSB 相對於中心頻率 (Center Frequency) 的位移量。
可透過 `get_ssb_offset_to_pointA` 來了解。

#### 計算範例

<img width="786" height="611" alt="image" src="https://github.com/user-attachments/assets/8a3b8173-b25d-4d3a-96a6-01d4e2468b32" />

根據上圖推算：

ssb = 12 * 86 / 2 = 516

因此在指令中需要加上參數：

```
--ssb 516
```

### 6. Nemo UE 與訊號測試

Nemo 工具可以幫助我們檢視周遭網路環境。

- 功能：透過在三星 (Samsung) 手機內安裝此分析軟體，可以直接讀取掃描到的 SIB1 訊息，並查看基地台的詳細資訊。

- 攻擊條件限制：理論上，所有的基地台都可以作為攻擊目標。但實務上，由於 USRP 發射的訊號功率有限，若基地台距離太遠會導致無法接收訊號。因此，成功的先決條件是目標基地台的接收增益 (RX Gain) 必須夠大。
