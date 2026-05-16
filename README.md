# F90 FPL Dashboard v3

Single-file dashboard for the F90 Fantasy Premier League league (#1204639).

## Features
- Live standings (GW19–38)
- GW Tracker with per-gameweek payment status
- Payments tab grouped by recipient
- Total Debts/Credits tab with net balances
- Add New GW tab for future gameweeks
- Overview tab with season prize pools and bar chart
- Admin PIN (1904) for all edits
- **Export Data** — downloads full league data as JSON
- **Import Data** — restores data from a previously exported JSON file
- Auto-save to localStorage on every edit
- Manual Save (PIN-confirmed) for explicit commits
- Reset Data (admin only) to clear localStorage

## Deployment
Drop `index.html` into any GitHub Pages repo root.
No build step, no dependencies, no server required.

## Data Persistence
- All edits auto-save to `localStorage` immediately.
- Use **Export Data** to download a JSON backup.
- Use **Import Data** to restore from that backup on any device.

## Admin PIN
`1904`
