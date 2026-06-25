- [nrUE_log](https://github.com/Littleyu15/OAI_project/blob/main/OAI/Background%20knowledge/log/nrUE_log.txt)
- [gNB_log](https://github.com/Littleyu15/OAI_project/blob/main/OAI/Background%20knowledge/log/gNB_log.txt)


### 控制平面 (Control Plane)
| 標籤 | 功能 | LOG 訊息說明 |
|---|---|---|
| `[RRC]` | 無線資源控制 | 處理與 UE 的連線建立、重配置、測量報告信令。 |
| `[NR_RRC]` | 5G NR RRC | 專用於 5G NR 的連線狀態機與控制指令處理。<br> `NR` : RAN 裡負責無線傳輸的技術規範|
| `[NGAP]` | N2 介面協議 | gNB 與核心網 AMF 間的信令傳遞 (如初始存取)。 |
| `[X2AP]` | X2 介面協議 | 基地台間的交接與資源協調信令。 |
| `[E1AP]` | E1 介面協議 | CU-CP 與 CU-UP 之間的控制平面訊息交換。 |


### 使用者平面 (User Plane)
| 標籤 | 功能 | LOG 訊息說明 |
|---|---|---|
| `[PDCP]` | 封包數據收斂 | 加解密、標頭壓縮與序列號管理。 |
| `[RLC]` | 無線鏈路控制 | 資料的分段、重組與 ARQ 錯誤更正。 |
| `[NR_MAC]` | NR MAC 層 | 排程器運作、HARQ 程序與無線資源分配。 |
| `[GTPU]` | GTP 使用者平面 | 建立與維護 gNB 和 UPF 間的數據隧道。 |

### 物理訊號與硬體 (Physical & Hardware)
| 標籤 | 功能 | LOG 訊息說明 |
|---|---|---|
| `[NR_PHY]` | NR 實體層 | 處理波形生成、調變/解調、通道估測與同步。 |
| `[PHY]` | 實體層 | 通用實體層功能與底層訊號處理。 |
| `[HW]` | 硬體驅動 | 與 USRP 等底層射頻卡的互動狀態。 |

### 系統應用與管理 (System & Utilities)
| 標籤 | 功能 | LOG 訊息說明 |
|---|---|---|
| `[GNB_APP]` | gNB 應用層 | 整個 gNB 節點的應用邏輯、初始化與狀態監控。 |
| `[CONFIG]` | 配置模組 | 解析啟動參數與設定檔讀取狀況。 |
| `[UTIL]` | 工具模組 | 系統輔助功能、時間戳記與除錯工具輸出。 |
| `[OPT]` | 優化模組 | 效能指標監控、統計數據與調優相關 LOG。 |
