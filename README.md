# Albubux (BUBX)

**Chain:** BNB Smart Chain (BEP-20)  
**Contract:** `0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9`  
**Name / Symbol / Decimals:** Albubux / BUBX / 9  
**Total Supply:** see BscScan “Read Contract”

Albubux is a community-driven LiquidityGeneratorToken with holder reflections, auto-liquidity (LP → `0xdead`), and an optional charity fee (must be 0 if charity address is `0x0`).  
Presale: **0%** fees. Post-listing policy target: **~1% total**, with a **public policy cap ≤ 5%**.  
*(The smart contract enforces a hard cap of **≤ 25%** across all fees.)*

## Links
- **Whitepaper:** .https://github.com/albubux/Albubux/blob/main/whitepaper/Albubux_Whitepaper.md
- **Investor README:** ./whitepaper/Albubux_README.md
- **BscScan (contract):** 0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9
- **Audit** https://blocksafu.com/certificate/0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9
- **PinkSale:** https://www.pinksale.finance/launchpad/bsc/0x902ef0De221AdD21452Ee94750DCD8036EcD519e
- **Website / Socials:** https://albubux.com

## Contract Highlights
- Single uniform transfer-fee schedule (no separate buy/sell in code).
- Fees (basis points over 10,000): `_taxFee` (reflections), `_liquidityFee` (auto-LP), `_charityFee` (to `_charityAddress`).
- **Hard cap:** `_tax + _liq + _charity ≤ 25%` (constructor + setters).
- **Swap & liquify threshold:** default ~0.1% of supply; owner can set but **≥ 0.05%**.
- Owner tools: `set*FeePercent`, `setSwapBackSettings`, `excludeFromFee`, `excludeFromReward/includeInReward`, `transferOwnership`, `renounceOwnership`.

## Verify / Build Notes
- **Compiler:** Solidity `0.8.4` (exact), **Optimization 200 runs**.  
- If BscScan shows “Similar Match”, that’s expected for this template.
- LP tokens are sent to `0xdead` by the contract on add-liquidity.
