# 港股板塊資金流 / HK Sector Capital Flow

Interactive Chaikin-style Hang Seng Index sector capital-flow chart (research tool).

**Live page:** https://vhhh2B618.github.io/hk-sector-flow/

- Red = 淨流入 (inflow) · Green = 淨流出 (outflow)
- Play / scrubber over the last complete HK RTH session (5-min bars; lunch skipped)
- Yahoo data is delayed; Chaikin is an estimate — **not** tick order-flow; **not** investment advice

Optional short: [`sector_flow_short.mp4`](./sector_flow_short.mp4)

To refresh data locally, use the pipeline on your machine (`fetch_flow.py` + `server.py` on port 8767). GitHub Pages cannot run the Python refresh.
