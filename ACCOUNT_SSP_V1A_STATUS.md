# Account SSP v1a status

Branch: `feat/account-ssp-v1a`  
Repo: AceSpurs/One-Plan-Live only (does not touch One-Plan or One-Plan-Lab).

## Shipped

- Account picker on Product S&S; chips/list filtered to selected account (plus Unassigned when needed)
- `primaryAccount` + closed `category` on every SKU (editable in SSP meta)
- Filtered KPI/banner = account Product S&S £ vs **that account’s WSSI only**
- Unassigned products force amber balance messaging — blocks green until assigned
- Derived category rollup pills (Footwear / Apparel / Accessories / Equipment) — not a keying grid
- Wizard + AI seeds: 8 SKUs, 2 per account, all with primaryAccount + category; per-account GAP 0 verified
- Advisor tips scoped to account WSSI gap / filtered product (no new category concentration tips)
- Phase 1–2 math, stores, gate, cascade/WSSI structure preserved; cascade still shows all accounts

## Transport

`index.html` assembler unchanged (n=4) + re-gzipped `ssp-payload/p0..p3.txt`.

## Do not

- Do **not** merge until Netlify/preview confirmed  
- Do **not** deploy to production  
- Do **not** touch AceSpurs/One-Plan or AceSpurs/One-Plan-Lab  
