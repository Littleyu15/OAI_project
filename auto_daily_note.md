# auto_daily_note (On Windows)

## Table Of Content
- [Step](#install)
- [Daily-Log Comment Format](#daily-log-comment-format)
- [Holiday / Time-Replacement Policy](#holiday--time-replacement-policy)
- [How to Run (Daily)](#how-to-run)

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
 

## Holiday / Time-Replacement Policy
When you worked on a public holiday or weekend :
```
### YYYY/MM/DD

> 🏖️ **HOLIDAY: <Holiday Name>** — Worked on public holiday; time replacement for `YYYY-MM-DD` absence.

**Daily-logs**:
- `HH.MM - HH.MM`: [description](url)
```

For the compensated absence day :
```
### YYYY/MM/DD

**Short-term Goal**:
<absent — compensated by working on YYYY-MM-DD (Holiday Name)>

**Daily-logs**:
- `ABSENT — compensated by 2026-05-01 (Labor Day)`
```


## How to Run
> Activate the venv first :
> ```
> .\.venv\Scripts\Activate.ps1
> ```

### Step 0 — Check missing dates (run this first every time)
```
python3 main.py \
  --dry-run --since YYYY-MM-DD --until YYYY-MM-DD \
  --ensure-comments --seed-from-commits
```

### Step 1 — Today only
```
# Preview
python3 main.py --dry-run --today --ensure-comments --seed-from-commits

# Apply
python3 main.py --apply --today --ensure-comments --seed-from-commits
```
Fetches commits from all configured contribution_sources, creates the day's comment if missing, and seeds Daily-logs bullets.

### Step 2 — Backfill a date range
```
python3 main.py \
  --apply --since YYYY-MM-DD --until YYYY-MM-DD \
  --ensure-comments --seed-from-commits --max-create 20
```
> Skip weekends — run one Mon–Fri range at a time to avoid empty weekend entries.

### Step 3 — Generate reminder.md
Lists missing dates and activities lacking evidence links :    *列出缺少日期以及沒有hyperlink的事項*
```
python3 main.py \
  --generate-reminder reminder.md \
  --since YYYY-MM-DD --until YYYY-MM-DD
```
Output sections:

1. Missing Daily-Log Entries — weekdays with no comment
2. Activities Without Evidence — bullets with no hyperlink (class/lecture events excluded)

Evidence links must point to a specific file with a **7-digit commit hash** :
```
[description](https://github.com/org/repo/blob/abc1234/path/to/file.md#section-heading)
```
