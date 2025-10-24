## Quantum-Secure (DEMO)

- **Public PQ key:** `ALBUBUX_PQ_PUB_V1`
- **Verifier:** https://albubux.github.io/albubux-verify/
- **1-click verify (this announcement):** https://albubux.github.io/albubux-verify/?u=https%3A%2F%2Falbubux.github.io%2Falbubux-verify%2Fannouncement.json

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
- **DxSale** https://www.dx.app/dxsale/view?address=0x3aea24db9214663b4d40E8f2557Fc3B5bF96cBbb&chain=BSC
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
