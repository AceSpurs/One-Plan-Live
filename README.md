# One Plan Live

**Live business planning tool** — not the Lab playground, not the production showcase.

| Surface | Repo | Role |
|---------|------|------|
| **Live** (this) | [AceSpurs/One-Plan-Live](https://github.com/AceSpurs/One-Plan-Live) | Day-to-day business planning |
| Lab | AceSpurs/One-Plan-Lab | Experiment / playground |
| Production showcase | AceSpurs/One-Plan | Production showcase site |

## Purpose

Plan the business in one place: **account plans** and **product stock & sales**, kept honest with matching totals.

## v0 focus — Account path

**Stores → account WSSI → product stock & sales**, with matching totals.

1. Store plans roll into accounts  
2. Account WSSI frames the marketplace (business planner)  
3. Product stock & sales must balance to that frame (retail planners)

## SSP Phase 1 (Product S&S)

Product Stock & Sales Plan replaces the thin sales£ / stock-units table:

- Per product × Y1 Q1–Q4: forecast, cancel% planned/actual, net sales, buy, open/close inventory, RTV%, target WOH13
- Computed WOH13 and Unit Risk (Nike formulas)
- Channel tag (Lifestyle vs Sporting goods) stored for Phase 2
- Plan balance: **S&S £ = Σ(net sales units × ASP) + residual adj** across products (Y1 annual), aligned to Account WSSI
- Wizard and AI demo seed full SSP fields
- Exact WSSI↔S&S £ close via 2-dp ASP + residual `gbpAdj` on last SKU (cleared when ASP is edited)

### Cancel rule (Phase 1)

- Effective cancel% = planned if planned > actual/current, else actual/current
- Net sales = forecast × (1 − effective_cancel/100)
- Extra cancel (planned > actual) reduces net units and therefore inventory via rollforward

### Rollforward

`close = open + buy + RTV − net_sales`  
Q2 open = Q1 close, etc. Q1 open from seeded opening stock.  
RTV units = forecast × (RTV%/100), default RTV% = 4.

### WOH13 / Unit Risk (Y1-only)

For quarter q, RSU_3m ≈ that quarter's net sales units.  
`WOH13 = EOP / (RSU_3m / 13)`  
`Unit Risk = (WOH13 − Target_WOH13) × (RSU_3m / 13)`

### SSP Phase 2 (this PR branch)

- R/A/G risk on closing inventory / WOH: stockout (close &lt; 0) Red; overstock (close &gt; 2× quarterly net) Amber, &gt; 3× Red; WOH outside channel band Amber
- Channel WOH bands: Lifestyle/specialty 7–13, Sporting goods 18–22 (default Lifestyle); flags compare band vs computed WOH13 (target WOH remains editable)
- Plan Advisor tip rail (ruleset v1): commercial tips for stockout, overstock, WOH out-of-band, gap vs WSSI, lifecycle
- ST% surfaced: STD_RSU / (STD_RSU + Inventory_EOP) per quarter (inputs already in Phase 1 compute)

Phase 1 math, plan-balance, wizard seeds, gate/cascade/WSSI/stores unchanged.

### Transport note

`index.html` is a small gzip assembler. Payload chunks live under `ssp-payload/p0.txt`…`p3.txt` (base64 gzip of the full SPA). Serve the repo root (e.g. Netlify / `npx serve .`) so relative fetches resolve. Do not open as a lone `file://` page.

## Team

| Role | Focus |
|------|--------|
| **Plan Advisor** | Guides the planning cycle and account path |
| **Plan Tech** | Builds and maintains the Live tool |
| **Plan Overseer** | Owns balance and go-live of the plan |

## Run locally

```bash
npx serve .
```

Then open the served URL (not raw file://).

## Deploy

Site: [one-plan-live.netlify.app](https://one-plan-live.netlify.app)

Do **not** deploy over Lab or production showcase Netlify sites.
