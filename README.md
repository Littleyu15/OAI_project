# OAI_projectSchedule-and-Goal-Planning
Schedule and Goal Planning

oai-aerial-metanoia-internship/
├── README.md
│
├── lab-handover/
│   └── ming-handover-notes.md
│
├── internship-notes/
│   ├── background/
│   │   ├── 5g-ran-basic-map.md
│   │   ├── oai-l2-basic-role.md
│   │   ├── aerial-cuphy-basic-role.md
│   │   ├── oran-fronthaul-basic.md
│   │   └── glossary.md
│   │
│   ├── reproduce/
│   │   ├── official-manual-annotated.md
│   │   ├── config-file-index.md
│   │   ├── log-file-index.md
│   │   ├── baseline-success-log-summary.md
│   │   └── reproduction-report-for-company.md
│   │
│   ├── e2e-architecture/
│   │   ├── e2e-system-architecture.md
│   │   ├── component-role-table.md
│   │   ├── data-flow-ue-to-cn.md
│   │   ├── control-plane-flow.md
│   │   ├── user-plane-flow.md
│   │   └── layer-by-layer-debug-map.md
│   │
│   ├── oai-l2-cuphy/
│   │   ├── oai-l2-plus-role.md
│   │   ├── fapi-overview.md
│   │   ├── nvipc-overview.md
│   │   ├── oai-to-cuphy-message-flow.md
│   │   ├── slot-timing-notes.md
│   │   ├── oai-config-map.md
│   │   ├── cuphycontroller-yaml-map.md
│   │   └── l2-l1-debug-checklist.md
│   │
│   ├── metanoia-oru-prep/
│   │   ├── metanoia-hardware-profile.md
│   │   ├── metanoia-access-method.md
│   │   ├── metanoia-network-config.md
│   │   ├── metanoia-ptp-config.md
│   │   ├── metanoia-rf-config.md
│   │   ├── metanoia-ecpri-config.md
│   │   ├── metanoia-eaxc-mapping.md
│   │   ├── metanoia-compression-setting.md
│   │   └── metanoia-oru-readiness-checklist.md
│   │
│   ├── metanoia-integration/
│   │   ├── bringup-plan.md
│   │   ├── bringup-daily-log.md
│   │   ├── cuphycontroller-metanoia-yaml-notes.md
│   │   ├── oai-gnb-metanoia-config-notes.md
│   │   ├── ptp-lock-test-result.md
│   │   ├── ecpri-connectivity-test.md
│   │   ├── oru-onair-check.md
│   │   ├── ue-attach-test-result.md
│   │   ├── ping-test-result.md
│   │   ├── iperf-test-result.md
│   │   └── integration-issue-list.md
│   │
│   └── final-report/
│       ├── internship-final-summary.md
│       ├── e2e-architecture-summary.md
│       ├── reproduction-summary.md
│       ├── metanoia-oru-integration-summary.md
│       ├── config-mapping-summary.md
│       ├── test-result-summary.md
│       ├── unresolved-issues.md
│       ├── debug-guide.md
│       └── next-step-recommendation.md
│
├── logs/
│   ├── 2026-06.md
│   ├── 2026-07.md
│   └── 2026-08.md
│
└── issues/
    ├── open-questions.md
    ├── technical-blockers.md
    └── questions-for-company.md
時間	主題	重點	主要產出
06/26～07/03	Ming 交接 + E2E 架構第一版	完成交接；先完整理解 UE、O-RU、fronthaul、cuPHY、OAI L2+、5GC 的位置	ming-handover-notes.md, e2e-system-architecture.md, component-role-table.md, glossary.md
07/04～07/10	帶著 E2E 架構重現學長實驗	每個 command 都對應到 E2E component；建立 config / log 索引與 baseline	senior-experiment-reproduction.md, config-file-index.md, log-file-index.md, baseline-success-log-summary.md
07/11～07/17	用重現結果修正 E2E 架構	把實際 container、config、log 放回 E2E；整理 control plane、user plane、debug map	control-plane-flow.md, user-plane-flow.md, layer-by-layer-debug-map.md, e2e-architecture.drawio
07/18～07/25	重現成果收斂	完成官方 manual 註解版、重現報告、baseline log summary、問題清單	official-manual-annotated.md, reproduction-report-for-company.md, questions-for-company.md, technical-blockers.md
07/26～08/02	OAI L2+ ↔ Aerial cuPHY 深入	深入 FAPI、NVIPC、cuPHYController、slot timing、config map	fapi-overview.md, nvipc-overview.md, oai-to-cuphy-message-flow.md, slot-timing-notes.md, l2-l1-debug-checklist.md
08/03～08/09	Metanoia O-RU 接入前準備	蒐集 Metanoia hardware、network、PTP、RF、eCPRI、eAxC、compression 資訊	metanoia-hardware-profile.md, metanoia-network-config.md, metanoia-ptp-config.md, metanoia-oru-readiness-checklist.md
08/10～08/16	Metanoia O-RU bring-up	修改 cuPHYController YAML 與 OAI config；確認 PTP、VLAN、eCPRI、fronthaul	bringup-plan.md, cuphycontroller-metanoia-yaml-notes.md, oai-gnb-metanoia-config-notes.md, ptp-lock-test-result.md, ecpri-connectivity-test.md
08/17～08/23	OTA 驗證與 UE attach	確認 O-RU on-air、UE detect cell、RACH、RRC/NAS、PDU session	ue-attach-test-result.md
08/24～08/31	E2E traffic + final report	ping / iperf / debug；整理 final summary、unresolved issues、next step	ping-test-result.md, iperf-test-result.md, internship-final-summary.md, debug-guide.md, next-step-recommendation.md
Repository File Guide
