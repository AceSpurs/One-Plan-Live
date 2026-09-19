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
- Plan balance: **S&S £ = Σ(net sales units × ASP)** across products (Y1 annual), aligned to Account WSSI
- Wizard and AI demo seed full SSP fields
- Exact WSSI↔S&S £ close via 2-dp ASP + residual £ adj on last SKU

Phase 2 (not in this release): R/A/G risk flags, tip rail, ST% UI emphasis, deeper channel logic.

**Note:** `index.html` uses a small gzip bootstrap that expands in-browser to the full single-page app (DecompressionStream).

## Team

| Role | Focus |
|------|--------|
| **Plan Advisor** | Guides the planning cycle and account path |
| **Plan Tech** | Builds and maintains the Live tool |
| **Plan Overseer** | Owns balance and go-live of the plan |

## Run locally

Open `index.html` in a browser, or:

```bash
npx serve .
```

## Deploy

Site: [one-plan-live.netlify.app](https://one-plan-live.netlify.app)

Do **not** deploy over Lab or production showcase Netlify sites.
