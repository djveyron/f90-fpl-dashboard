# F90 FPL Dashboard — Overview Final

## Overview
Interactive FPL league dashboard for the F90 Super90 Classic league (#1204639).
Tracks GW19–38 payments, season prize pools, and net positions for all managers.

## Features
- **Standings** — Live FPL standings (GW19–38)
- **Overview** — Full season financial overview including GW + season prize pools
  - Correct net position graph (GW debts + season fees + season prize winnings)
  - Season Prize Pools with Paid/Unpaid toggles per manager
- **GW Tracker** — Master control panel for all gameweek payment statuses
- **Payments** — Grouped by recipient, showing paid/outstanding per manager
- **Total Dt/Cr** — GW-only net balances per manager
- **Add New GW** — Enter future GW results (GW37, GW38)

## Net Position Logic (Overview Graph)
Net = (GW winnings owed to manager + season prize share owed) − (GW debts unpaid + season entry fees unpaid)

Example — Poom: owes 2800 GW + 2000 season fees = 4800 total → net = −4800

## Admin
- PIN: 1904
- Unlock → make edits → Save Changes (requires PIN re-entry) → Lock

## Data Persistence
- All edits saved to browser localStorage
- Export/Import JSON for backup and GitHub deployment

## Deployment
Upload `index.html` to any static host (GitHub Pages, Netlify, etc.)
No server required — fully client-side.

## League Rules (GW19–38)
- Normal GW: 3rd–7th pay 200 to 1st; 8th–9th (bottom 2) pay 200 to 2nd
- Tie GW: all others pay 100 each to both tied 1st-place managers
- GW22 & GW23: cancelled, no payments
- Kim & Arm: bad debts, excluded from all totals

## Season Prizes (1st Half, 13 managers)
- H2H: Note 6000, Tung 3000, DJ 1000 (10000 pot)
- Classic: Pladon 6000, Note 3000, Tung 1000 (10000 pot)
- GW Prize: DJ 50%, Phai 50% (via Note)
- 2nd Half Classic: 8000 pot (TBD — season in progress)
