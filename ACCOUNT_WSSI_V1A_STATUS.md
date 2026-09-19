# Account WSSI v1a status

Branch: `feat/account-wssi-v1a`  
Repo: AceSpurs/One-Plan-Live only (does not touch One-Plan or One-Plan-Lab).

## Shipped

- **Intention** per account — required closed list: Grow / Maintain / Reduce / Exit (editable select on Account WSSI)
- **Share %** display improved (one decimal) with concentration colouring
- **Concentration flags**: amber when account share of total WSSI **>40%**, red when **>50%** (row + Flag column)
- **Currency Viz #5**: Sales £ displays with en-GB thousands separators (`£4,200,000`); on focus edits as plain number; blur commits
- **Light hardcoded tips** on Account WSSI: concentration + missing intention (Product Advisor tip rail unchanged)
- **Wizard + AI seeds**: every account gets an intention (wizard fixed map; AI random from closed list, then normalized)

## Explicitly untouched

- SSP Phase 1–2 math (forecast/cancel/net/buy/rollforward/WOH/Unit Risk/R-A-G)
- Product S&S grid, account picker, category rollups
- WSSI→SSP auto-rebalance (out of scope)
- Stores picker, cascade structure, gate

## Transport

`index.html` assembler unchanged (`n = 4`) + re-gzipped `ssp-payload/p0..p3.txt`.

## Do not

- Do **not** merge until Netlify/preview confirmed  
- Do **not** deploy to production  
- Do **not** touch AceSpurs/One-Plan or AceSpurs/One-Plan-Lab  
