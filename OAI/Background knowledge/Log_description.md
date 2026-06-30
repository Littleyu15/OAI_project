- [nrUE_Log (process inform)](https://github.com/Littleyu15/OAI_project/blob/main/OAI/Background%20knowledge/log/nrUE_log.txt)
- [gNB_Log (process inform)](https://github.com/Littleyu15/OAI_project/blob/main/OAI/Background%20knowledge/log/gNB_log.txt)

## Table Of Content 
- [Log Introduction](#控制平面-control-plane)
- [gNB Log (package inform)](#gnb-log)
- [nrUR_Log (package inform)](#nrue-log)

### 控制平面 (Control Plane)
| 標籤 | 功能 | 說明 |
|---|---|---|
| `[RRC]` | 無線資源控制 | 處理與 UE 的連線建立、重配置、測量報告信令。 |
| `[NR_RRC]` | 5G NR RRC | 專用於 5G NR 的連線狀態機與控制指令處理。<br> `NR` : RAN 裡負責無線傳輸的技術規範|
| `[NGAP]` | N2 介面協議 | gNB 與核心網 AMF 間的信令傳遞 (如初始存取)。 |
| `[X2AP]` | X2 介面協議 | 基地台間的交接與資源協調信令。 |
| `[E1AP]` | E1 介面協議 | CU-CP 與 CU-UP 之間的控制平面訊息交換。 |


### 使用者平面 (User Plane)
| 標籤 | 功能 | 說明 |
|---|---|---|
| `[PDCP]` | 封包數據收斂 | 加解密、標頭壓縮與序列號管理。 |
| `[RLC]` | 無線鏈路控制 | 資料的分段、重組與 ARQ 錯誤更正。 |
| `[NR_MAC]` | NR MAC 層 | 排程器運作、HARQ 程序與無線資源分配。 |
| `[GTPU]` | GTP 使用者平面 | 建立與維護 gNB 和 UPF 間的數據隧道。 |

### 物理訊號與硬體 (Physical & Hardware)
| 標籤 | 功能 | 說明 |
|---|---|---|
| `[NR_PHY]` | NR 實體層 | 處理波形生成、調變/解調、通道估測與同步。 |
| `[PHY]` | 實體層 | 通用實體層功能與底層訊號處理。 |
| `[HW]` | 硬體驅動 | 與 USRP 等底層射頻卡的互動狀態。 |

### 系統應用與管理 (System & Utilities)
| 標籤 | 功能 | 說明 |
|---|---|---|
| `[GNB_APP]` | gNB 應用層 | 整個 gNB 節點的應用邏輯、初始化與狀態監控。 |
| `[CONFIG]` | 配置模組 | 解析啟動參數與設定檔讀取狀況。 |
| `[UTIL]` | 工具模組 | 系統輔助功能、時間戳記與除錯工具輸出。 |
| `[OPT]` | 優化模組 | 效能指標監控、統計數據與調優相關 Log。 |


---
### gNB Log
```
[NR_MAC] Frame.Slot 896.0
UE RNTI 8e03 CU-UE-ID 1 in-sync PH 48 dB PCMAX 20 dBm, average RSRP -44 (16 meas)
UE 8e03: UL-RI 1, TPMI 0
UE 8e03: dlsch_rounds 56/0/0/0, dlsch_errors 0, pucch0_DTX 0, BLER 0.00133 MCS (0) 0 CCE fail 0
UE 8e03: ulsch_rounds 415/0/0/0, ulsch_errors 0, ulsch_DTX 0, BLER 0.00000 MCS (0) 0 (Qm 2 deltaMCS 0 dB) NPRB 5  SNR 51.0 dB CCE fail 0
UE 8e03: MAC:    TX           1541 RX           8948 bytes
UE 8e03: LCID 1: TX            552 RX            281 bytes
UE 8e03: LCID 2: TX              0 RX              0 bytes
UE 8e03: LCID 4: TX             12 RX            216 bytes
```

項目|參數名稱|數值 / 狀態|說明
|---|---|---|---|
系統參數|Frame.Slot|896.0|當前系統時間點
|CU-UE-ID|1|基地台識別 ID
|狀態|in-sync|與基地台保持同步
功率/訊號|PH|48 dB|功率餘量 (剩餘傳輸空間)
|PCMAX|20 dBm|UE 設定的最大發射功率限制
|RSRP|-44 dBm|平均接收訊號強度 (基於 16 次測量)|接收到的訊號強度高
|SNR|51.0 dB|訊號雜訊比 (極佳)
傳輸效能|UL-RI / TPMI|1 / 0|上行採用單層傳輸|無複雜預編碼
|DL HARQ|56/0/0/0|下行傳輸 (首發即成功|無重傳)
|UL HARQ|415/0/0/0|上行傳輸 (首發即成功|無重傳)
|BLER (DL/UL)|0.0013 / 0.0000|區塊錯誤率 (趨近於 0)|無線通道品質接近完美

頻道 ID|方向|流量 (Bytes)|說明
|---|---|---|---|
LCID 1|TX / RX|552 / 281|通常信令無線載體 (SRB1)，處理控制資訊
LCID 2|TX / RX|0 / 0|目前閒置
LCID 4|TX / RX|12 / 216|通常數據無線載體 (DRB)，處理實際用戶流量
總計 (MAC)|TX / RX|1541 / 8948|該區間內 MAC 層總吞吐量(Payload + MAC Subheader)

### nrUE Log
```
[NR_MAC] UE 0 RNTI 8e03 stats sfn: 512.8| cumulated bad DCI 0      
    DL harq: 52/0
    UL harq: 378/0 avg code rate 0.1| avg bit/symbol 2.0| avg per TB: (nb RBs 9.8| nb symbols 11.7)
```

項目|數值|說明
|---|---|---|
UE |0|索引值為0
RNTI|8e03|無線網路暫時識別碼 : 用於區分 UE 的識別碼
SFN|512.8|System Frame Number : 系統影格號碼 (時間戳)
DCI|0|Downlink Control Information : 錯誤累積
DL HARQ|52/0|下行傳輸 (成功/失敗)
UL HARQ|378/0|上行傳輸 (成功/失敗)
Code Rate|0.1|編碼率
Bits/Sym|2.0|調變效率
avg per TB(Transport Block)|nb RBs 9.8<br>nb symbols 11.7|平均每個傳輸區塊使用了約 10 個資源區塊 (Resource Blocks)<br>平均每個傳輸區塊佔用了約 12 個 OFDM 符號。

