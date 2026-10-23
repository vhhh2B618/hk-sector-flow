# 港股板塊資金流 / HK Sector Capital Flow

Interactive Chaikin-style Hang Seng Index sector capital-flow chart (research tool).

**Live page:** https://vhhh2B618.github.io/hk-sector-flow/

- Red = 淨流入 (inflow) · Green = 淨流出 (outflow)
- Play / scrubber over the latest HK RTH session (5-min bars; lunch skipped)
- Yahoo data is delayed; Chaikin is an estimate — **not** tick order-flow; **not** investment advice

## Auto-refresh (GitHub Actions)

Pages updates **hourly on weekdays 09:00–16:00 HKT** via [`.github/workflows/hourly-refresh.yml`](./.github/workflows/hourly-refresh.yml) (`cron: '0 1-8 * * 1-5'` UTC). The workflow runs `pipeline/publish_static.py` (yfinance fetch → rebuild root `index.html` + `sector_flow.json` / `.csv`) and commits only when data changed. Holidays / empty sessions skip the commit.

Optional short: [`sector_flow_short.mp4`](./sector_flow_short.mp4) (not rebuilt in CI).

## Local refresh

The in-page **Refresh** button needs the local pipeline server (`fetch_flow.py` + `server.py` on port **8767**). GitHub Pages serves static files only.
