
### After work reocrd daily log (On own PC)
```
cd C:\Users\kevin\auto-daily-log
.\.venv\Scripts\Activate.ps1
python main.py --apply --today --ensure-comments --seed-from-commits
```

# 一、整體七月目標

## 總目標

完成實驗基礎環境建置與進階網路攻擊及模型研究，包含：DGX spark安裝與筆記、重現 Richard 論文結果、完成 HTC Jamming attack、OAI NTN Channel Model 獨立抽離，以及 DURANTA 與 O-CU-DU 研究筆記，建立可交接與可驗證的技術文件。

| 月份  | 月目標                                                                  | 月檢查點 |
| --- | -------------------------------------------------------------------- | ---- |
| 7 月 | 完成 OAI 環境建置、重現 Richard 實驗、HTC Jamming 攻擊設計、Channel Model 抽離及 DURANTA/O-CU-DU 研究 、 完成 DGX 環境建置 | 7/31 |

---

# 二、每週里程碑總表

| 週次    | 日期        | 週五檢查點 | 週里程碑                                                   | 預期總進度 |
| ----- | --------- | ----- | ------------------------------------------------------ | ----: |
| W1    | 7/1–7/3   | 7/3   | 完成 OAI/DGX spark 安裝、環境設定與學習筆記                               | 20%   |
| W2    | 7/6–7/10  | 7/10  | 研讀並重現 Richard 論文結果，產出對應實驗數據與比較分析                      | 40% |
| W3    | 7/13–7/17 | 7/17  | 針對 HTC 基站完成 Jamming attack 的攻擊、封包擷取與驗證報告            | 60%  |
| W4    | 7/20–7/24 | 7/24  | 完成 OAI NTN Channel Model 獨立抽離模組設計，並提交單元測試              | 80%  |
| W5    | 7/27–7/31 | 7/31  | 完成 DURANTA 與 O-CU-DU 研究筆記，並總結 7 月各項實驗報告與交接文件          | 100%  |

---

# 三、週計畫

## 工時估算原則

每日預估工時以 6–7 小時為基準。

每一天通常安排一個主要工作，但實際工時包含資料查找、參數確認、文件整理、log / evidence 整理、Pending / Blocked 紀錄，以及隔天工作準備。

若主要工作提前完成，剩餘時間用於補齊本週其他產出；若主要工作無法完成，則保留目前進度、blocked reason 與 next step。

## 協作者與分工

| 協作者 | 角色 | 分工 |
|---|---|---|
| Kevin | Owner | 負責執行各項環境部署、實驗重現、攻擊設計、程式碼開發(Channel Model)與筆記撰寫 |
| Richard | Supporter | 協助提供論文相關原始資料、程式碼與實驗重現的基準數據 |
| Professor | Reviewer | 檢查研究方向與產出是否符合目標 |

---

# W1：2026/7/1（三）–2026/7/3（五）

## 週里程碑

完成 OAI 安裝，並將相關測試與學習紀錄整理成筆記。

## 每日工作

| 日期 | 主要工作 | 預估工時 | 補充工作 / 緩衝 | 截止日期 | 預期產出 |
|---|---|---:|---|---|---|
| 7/1（三） | 完成 OAI 建置以及 Log 筆記 | 6h | 能夠做出完整E2E user guide筆記以及Log說明 | 7/1 | `oai_user_guide.md` |
| 7/2（四） | 執行 DGX spark 安裝與 Container 環境設定測試 | 7h | 解決 Container 啟動時的掛載問題，保存 command 與 log | 7/2 | `dgx-spark-installation-log.md` |
| 7/3（五） | 週檢查點：撰寫 DGX spark 學習筆記並確認環境可穩定運行 | 6h | 補齊截圖與執行 evidence，盤點下週重現實驗的檔案 | 7/3 | `dgx-spark-study-notes.md`, `week1-checkpoint.md` |

## 本週產出與百分比

| 產出 | 完成度 | 截止日期 |
|---|---:|---|
| `oai_user_guide.md` | 100% | 7/1 |
| `dgx-spark-installation-log.md` | 100% | 7/2 |
| `dgx-spark-study-notes.md` | 100% | 7/3 |
| `week1-checkpoint.md` | 100% | 7/3 |

## 7/3 通過標準
* **安裝日誌**：`dgx-spark-installation-log.md` 需包含完整的安裝指令、設定檔與啟動成功的 terminal output。
* **學習筆記**：`dgx-spark-study-notes.md` 需紀錄操作流程與常見問題的 Trouble Shooting 方法。

---

# W2：2026/7/6（一）–2026/7/10（五）

## 週里程碑

重現 Richard 論文結果，包含理解架構、部署實驗環境、執行並產出對應數據。

## 每日工作

| 日期 | 主要工作 | 預估工時 | 補充工作 / 緩衝 | 截止日期 | 預期產出 |
|---|---|---:|---|---|---|
| 7/6（一） | 研讀 Richard 論文與實驗架構簡報 | 6h | 標註論文中的關鍵實驗數據、圖表與成功條件 | 7/6 | `richard-thesis-summary.md` |
| 7/7（二） | 解析實驗相關程式碼，確認環境配置參數 | 6h | 釐清程式邏輯與需要的 dependency | 7/7 | `reproduction-config-notes.md` |
| 7/8（三） | 配置重現實驗的基礎環境並進行初測 | 6h | 確認不影響既有伺服器運作，保留 error log | 7/8 | `reproduction-environment-setup.md` |
| 7/9（四） | 實際執行實驗程式，擷取運作數據與圖表 | 7h | 針對數據偏差進行微調與 debug | 7/9 | `thesis-experiment-logs.md` |
| 7/10（五） | 週檢查點：完成實驗重現，比對產出結果與論文數據 | 6h | 撰寫比較報告與差異分析，準備 W3 工具 | 7/10 | `thesis-reproduction-report.md`, `week2-checkpoint.md` |

## 本週產出與百分比

| 產出 | 完成度 | 截止日期 |
|---|---:|---|
| `richard-thesis-summary.md` | 100% | 7/6 |
| `reproduction-config-notes.md` | 100% | 7/7 |
| `thesis-experiment-logs.md` | 100% | 7/9 |
| `thesis-reproduction-report.md` | 100% | 7/10 |
| `week2-checkpoint.md` | 100% | 7/10 |

## 7/10 通過標準
* **結果對齊**：`thesis-reproduction-report.md` 必須有明確的數據對照表（Baseline vs 實際跑出結果）。
* **Log 完整性**：實驗日誌必須包含 Command、Environment 與實際輸出。

---

# W3：2026/7/13（一）–2026/7/17（五）

## 週里程碑

對 HTC 基站進行 Jamming attack 攻擊方法設計、封包擷取與測試驗證。

## 每日工作

| 日期 | 主要工作 | 預估工時 | 補充工作 / 緩衝 | 截止日期 | 預期產出 |
|---|---|---:|---|---|---|
| 7/13（一） | 盤點 HTC 基站設備規格與 Jamming 理論基礎 | 6h | 確認硬體限制，研讀 RACH 攻擊相關文獻 | 7/13 | `htc-equipment-specs.md` |
| 7/14（二） | 提出 HTC Jamming attack 的攻擊方法設計草案 | 7h | 包含預期影響層面、頻段選擇與腳本邏輯 | 7/14 | `jamming-attack-design.md` |
| 7/15（三） | 建立封包擷取環境（確保 PCAP 可正常錄製解析） | 6h | 確保控制面與資料面流量皆可正常擷取 | 7/15 | `packet-capture-guide.md` |
| 7/16（四） | 執行 Jamming 攻擊實測，記錄系統影響與封包特徵 | 7h | 分析封包以證明攻擊成功干擾基站 | 7/16 | `jamming-execution-logs.md` |
| 7/17（五） | 週檢查點：完成攻擊設計與實測驗證報告 | 6h | 整理風險與限制，歸檔 PCAP 證據 | 7/17 | `jamming-attack-report.md`, `week3-checkpoint.md` |

## 本週產出與百分比

| 產出 | 完成度 | 截止日期 |
|---|---:|---|
| `htc-equipment-specs.md` | 100% | 7/13 |
| `jamming-attack-design.md` | 100% | 7/14 |
| `packet-capture-guide.md` | 100% | 7/15 |
| `jamming-attack-report.md` | 100% | 7/17 |
| `week3-checkpoint.md` | 100% | 7/17 |

## 7/17 通過標準
* **設計完整**：設計草案需明確定義攻擊的情境與目標。
* **驗證證據**：必須提供封包擷取的截圖或特徵分析，證明攻擊腳本確實發揮作用。

---

# W4：2026/7/20（一）–2026/7/24（五）

## 週里程碑

完成 OAI NTN Channel Model 的獨立抽離設計與 Python 單元測試驗證。

## 每日工作

| 日期 | 主要工作 | 預估工時 | 補充工作 / 緩衝 | 截止日期 | 預期產出 |
|---|---|---:|---|---|---|
| 7/20（一） | 整理 TR38.901 與 NTN 參數比較表 | 6h | 確認衰落參數與傳播延遲的差異 | 7/20 | `tr38.901-vs-ntn-comparison.md` |
| 7/21（二） | 設計 Channel Model 獨立抽離架構 | 7h | 定義輸入/輸出資料結構與 API 介面 | 7/21 | `channel-model-architecture.md` |
| 7/22（三） | 實作獨立抽離邏輯與 Python 單元測試程式 | 7h | 處理邊界條件與訊號模擬邏輯 | 7/22 | `channel_model_test.py` |
| 7/23（四） | 執行單元測試，比對抽離前後的輸出一致性 | 6h | 記錄測試 error 與修正過程 | 7/23 | `unit-test-results.md` |
| 7/24（五） | 週檢查點：完成抽離技術報告與代碼提交 | 6h | 確認文件 traceability，盤點 W5 研究資料 | 7/24 | `channel-model-extraction-report.md`, `week4-checkpoint.md` |

## 本週產出與百分比

| 產出 | 完成度 | 截止日期 |
|---|---:|---|
| `tr38.901-vs-ntn-comparison.md` | 100% | 7/20 |
| `channel-model-architecture.md` | 100% | 7/21 |
| `channel_model_test.py` (Code) | 100% | 7/22 |
| `unit-test-results.md` | 100% | 7/23 |
| `channel-model-extraction-report.md`| 100% | 7/24 |
| `week4-checkpoint.md` | 100% | 7/24 |

## 7/24 通過標準
* **架構清晰**：API 介面定義必須清楚，確保後續容易與主程式對接。
* **測試通過**：Python 腳本需具備高覆蓋率，且 `unit-test-results.md` 顯示 Pass。

---

# W5：2026/7/27（一）–2026/7/31（五）

## 週/月里程碑

完成 DURANTA 與 O-CU-DU 研究筆記，並總結 7 月份的所有專案成果。

## 每日工作

| 日期 | 主要工作 | 預估工時 | 補充工作 / 緩衝 | 截止日期 | 預期產出 |
|---|---|---:|---|---|---|
| 7/27（一） | 閱讀 DURANTA 系統架構相關文獻 | 6h | 釐清其在 5G OAI 系統中的定位 | 7/27 | `duranta-architecture-notes.md` |
| 7/28（二） | 閱讀 O-CU-DU 架構設計，並比對 DURANTA 差異 | 6h | 整理 OAI 與兩者的整合優劣與特徵 | 7/28 | `o-cu-du-study-notes.md` |
| 7/29（三） | 製作 OAI、DURANTA 與 O-CU-DU 的總和比較表 | 7h | 針對擴充性、效能、對接容易度進行評估 | 7/29 | `oai-duranta-ocudu-comparison.md` |
| 7/30（四） | 收斂 7 月所有實驗日誌（DGX, Richard, HTC, Channel Model） | 6h | 確認所有超連結有效、檢查 evidence 是否齊全 | 7/30 | `month-7-open-issues.md` |
| 7/31（五） | 月檢查點：產出 7 月總結報告，並規劃下一步計畫 | 6h | 完成 handover guide 基礎準備 | 7/31 | `month-7-summary.md`, `week5-checkpoint.md` |

## 本週產出與百分比

| 產出 | 完成度 | 截止日期 |
|---|---:|---|
| `duranta-architecture-notes.md` | 100% | 7/27 |
| `o-cu-du-study-notes.md` | 100% | 7/28 |
| `oai-duranta-ocudu-comparison.md` | 100% | 7/29 |
| `month-7-open-issues.md` | 100% | 7/30 |
| `month-7-summary.md` | 100% | 7/31 |
| `week5-checkpoint.md` | 100% | 7/31 |

## 7/31 月檢查通過標準
* **研究深度**：DURANTA 與 O-CU-DU 的筆記不能僅是翻譯，需結合 OAI 系統寫出具體差異。
* **月總結**：`month-7-summary.md` 需清楚回顧本月設定的所有里程碑是否達成，並附上相關文件連結。
