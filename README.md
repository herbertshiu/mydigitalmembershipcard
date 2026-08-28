# mydigitalmembershipcard.hk

Live site for **店家會員指南** — a neutral Hong Kong membership guide for shop owners.

| Item | Value |
|------|--------|
| **Domain** | [mydigitalmembershipcard.hk](https://mydigitalmembershipcard.hk) |
| **GitHub** | `git@github.com:herbertshiu/mydigitalmembershipcard.git` |
| **Branch** | `main` |
| **Hosting** | GitHub Pages (`CNAME` → mydigitalmembershipcard.hk) |

This repo is **separate** from `membershiprewardssystem`. All site files live at the repo root.

## Daily new articles (Zo Computer)

1. `keywords-queue.json` — topic queue (one article per day)
2. `PROMPT_TEMPLATE.md` — AI writing rules
3. `automation/ZO_PROMPTS.md` — copy-paste Zo automation instruction

Set up Zo to clone this repo and run the daily instruction at 8:30 AM HKT. See `automation/ZO_DAILY_SETUP.md`.

## Local preview

```powershell
powershell -ExecutionPolicy Bypass -File .\serve.ps1
# Open http://127.0.0.1:4173/
```
