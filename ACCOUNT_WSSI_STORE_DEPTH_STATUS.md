# Account WSSI — store-depth rebuild (draft)

Branch: `feat/account-wssi-v1a`  
Repo: AceSpurs/One-Plan-Live only (does not touch One-Plan or One-Plan-Lab).

## Shipped in this tip

1. **Named account planner owner** (required) on each account — seeded + editable; amber tip if missing
2. **≥1 store** under each account (seeded 3–5); soft-block tip if none
3. **Soft-flag** when Σ(store £) ≠ account WSSI; **green only** when they match (hard identity)
4. **Top-down:** edit account WSSI → pro-rata by unlocked store share; locked stores stay fixed; unlocked absorb residual
5. **Bottom-up:** edit store £ → account does **not** auto-inflate; gap until explicit **Reconcile-up → account**
6. Product S&S still balances to **account WSSI only** (no store→product cascade); no WSSI→SSP auto-rebalance
7. Tabs on Account WSSI: **Account frame** | **Store plan**
8. Thin v1a UX kept: intention Grow/Maintain/Reduce/Exit, share %, concentration amber >40% / red >50%, en-GB £, light tips
9. Stores nav picker fixed (class=`sel`, shared `storePlanAccount` with Store plan tab)

## Explicitly out of scope

- Merge / production promote
- Store→product cascade
- WSSI→SSP auto-rebalance
- Category break (v1b)
- Changes to AceSpurs/One-Plan or One-Plan-Lab

## Do not

- Do **not** merge until Andrew confirms after BPE/Viz  
- Do **not** deploy to production  
- Draft Netlify preview only  
