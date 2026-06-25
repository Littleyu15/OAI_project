# auto_daily_note (Windows)

## Table Of Content
- [Step](#install)
- [Rules](#rules)
- [Holiday / Time-Replacement Policy](#holiday---time-replacement-policy)

### Make sure you install git
[Download](https://git-scm.com/install/windows)

### Install 
> ```
> git clone https://github.com/bmw-ece-ntust/auto-daily-log.git
> cd auto-daily-log
> python3 -m venv .venv
> .\.venv\Scripts\Activate.ps1  # 啟動虛擬環境 (每次執行工具前都要確保已啟動)
> pip install -r requirements.txt
> ```

### Copy and Edit Config
> ```
> # Edit env.yaml — set github.login, contribution_sources, etc.
> cp env.example.yaml env.yaml
> ```
> ### Edit 
> <img width="752" height="442" alt="image" src="https://github.com/user-attachments/assets/95a92d25-063b-4701-856e-3bb3f6ad7ac2" />

### Authenticate GitHub CLI (one time only)
```
gh auth login
```
---

## Daily-Log Comment Format
```
### YYYY/MM/DD

**Short-term Goal**:
<one-line goal>

**Daily-logs**:
- `HH.MM - HH.MM`: [description](https://github.com/org/repo/blob/abc1234/path/to/file.md#section)
- `HH.MM - `: <ongoing activity>
```

### Rules:

- Heading: ### YYYY/MM/DD (Asia/Taipei timezone)
- Short-term Goal: one-line goal for the day
- Daily-logs: one bullet per activity
  - Time range in backticks: `HH.MM - HH.MM` (end time from commit timestamp)
  - Evidence link: specific file URL with 7-digit commit hash + heading anchor  *需附上hyperlink*
  - Special entries: `SICK LEAVE`, `HOLIDAY`, `ABSENT` *病假、國定假日、補假*
 

### Holiday / Time-Replacement Policy
When you worked on a public holiday or weekend :
```
### YYYY/MM/DD

> 🏖️ **HOLIDAY: <Holiday Name>** — Worked on public holiday; time replacement for `YYYY-MM-DD` absence.

**Daily-logs**:
- `HH.MM - HH.MM`: [description](url)
```
  
