# 港股板塊資金流 / HK Sector Capital Flow

Interactive Chaikin-style Hang Seng Index sector capital-flow chart (research tool).

**Live page:** https://vhhh2B618.github.io/hk-sector-flow/

- Red = 淨流入 (inflow) · Green = 淨流出 (outflow)
- Play / scrubber over the latest HK RTH session (5-min bars; lunch skipped)
- Yahoo data is delayed; Chaikin is an estimate — **not** tick order-flow; **not** investment advice

## Auto-refresh (GitHub Actions)

Pages is meant to update **hourly on weekdays 09:00–16:00 HKT** via GitHub Actions
(`cron: '0 1-8 * * 1-5'` UTC → 01:00–08:00 UTC).

The runnable workflow source lives at [`pipeline/hourly-refresh.yml`](./pipeline/hourly-refresh.yml).
Copy it to `.github/workflows/hourly-refresh.yml` on `main` (GitHub UI → Add file, or a token with the `workflow` scope) to enable the schedule. The job runs `pipeline/publish_static.py` (yfinance fetch → rebuild root `index.html` + `sector_flow.json` / `.csv`) and commits only when data changed. Holidays / empty sessions skip the commit (exit 78).

Optional short: [`sector_flow_short.mp4`](./sector_flow_short.mp4) (not rebuilt in CI).

## Local refresh

The in-page **Refresh** button needs the local pipeline server (`fetch_flow.py` + `server.py` on port **8767**). GitHub Pages serves static files only.
