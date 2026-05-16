# F90 FPL Dashboard — Fixed Build

A self-contained, mobile-friendly Fantasy Premier League payment tracker for the F90 league (#1204639).

## What Was Fixed in This Build

### Critical Bug: Deletions Not Persisting After Refresh
**Root cause:** The old `loadFromStorage` used a *merge* strategy — it started from the full hardcoded default data and only patched/added entries. This meant deleted entries were always restored from defaults on page reload.

**Fix:** `loadFromStorage` now uses a **full replace** strategy:
- On load, `PAYS` and `SEASON_PAYS` arrays are completely cleared (`length = 0`)
- They are then rebuilt entirely from the saved localStorage data
- Deletions are now permanent — if an entry isn't in the saved data, it stays gone
- Two snapshot arrays (`DEFAULT_PAYS`, `DEFAULT_SEASON_PAYS`) are kept for field-filling only (to recover any missing fields from defaults without restoring deleted entries)

### Save System Unified
All edits across all tabs (GW Tracker, Payments, Debts, Season entries) write to the same `manualSave()` function which saves the complete state to localStorage under key `f90_fpl_v4`.

## Files

| File | Description |
|------|-------------|
| `index.html` | Complete dashboard — all CSS, JS, and data in one file |
| `README.md` | This setup guide |

## GitHub Pages Deployment

1. Create a new GitHub repository (e.g. `f90-fpl-dashboard`)
2. Upload `index.html` and `README.md` to the root
3. Go to **Settings → Pages → Source → Deploy from branch → main / (root)**
4. Your dashboard will be live at:
   `https://[your-username].github.io/f90-fpl-dashboard/`

## Features

- 📊 Live standings (GW19–38)
- 📅 GW Tracker — expand each gameweek, toggle paid/unpaid
- 💳 Payments tab — GW + Season payments per manager (excludes Ta, Kim, Arm)
- 📈 Overview — season prize pools + net position chart
- 📉 Total Dt/Cr — net balances per manager
- 🔐 Admin PIN: **1904** — gates all edits
- 💾 localStorage persistence — deletions and all edits survive page refresh
- 📱 Mobile-friendly / PWA-lite (Add to Home Screen)

## Admin Usage

1. Click **Unlock** → enter PIN `1904`
2. Make edits (toggle payments, delete/add debts, edit owes-to)
3. Click **💾 Save Changes** → re-enter PIN to confirm
4. Click **Lock** when done
5. Refresh the page — all changes (including deletions) will persist

## Data Included

- GW19–36 fully populated with correct payment records
- Season payments: Classic + H2H (→ Bank), GW Prize (→ DJ/Phai)
- Bad debts: Kim & Arm (flagged, excluded from totals)
- LIVE standings from screenshot data (GW36 totals)