

# Albubux (BUBX)

**Chain:** BNB Smart Chain (BEP-20)  
**Agreement:** `0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9`  
**Name / Symbol / Decimal places:** Albubux / BUBX / 9  
**Total supply:** see BscScan "Read the contract"

Albubux is a community-run LiquidityGeneratorToken with holder reflections, automatic liquidity (LP → `0xdead`) and an optional charity fee (must be 0 if the charity's address is `0x0`).  
Pre-order: **0%** fees. Policy Purpose Once Listed: **~1% total**, With **public policy limit ≤ 5%**.  
*(The smart contract enforces a hard limit **≤ 25%** all fees.)*

## Cufflinks
- **Official book:** .https://github.com/albubux/Albubux/blob/main/whitepaper/Albubux_Whitepaper.md
- **Investor, README file:** ./whitepaper/Albubux_README.md
- **BscScan (contract):** 0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9
- **Revision** https://blocksafu.com/certificate/0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9
- **Dx Sale** https://www.dx.app/dxsale/view?address=0x3aea24db9214663b4d40E8f2557Fc3B5bF96cBbb&chain=BSC
- **Website / social networking sites:** https://albubux.com
- **dexscreener** https://dexscreener.com/bsc/0x6d9c130a9d7ea7078d16ad35d6907f034487483c
- **dextools**  https://www.dextools.io/app/en/bnb/pair-explorer/0x6d9C130A9D7ea7078D16aD35D6907f034487483C?t=1764121180815
- **pancake** https://pancakeswap.finance/swap?outputCurrency=0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9&chainId=56&chain=bsc
- **geckoterminal** https://www.geckoterminal.com/bsc/pools/0x6d9C130A9D7ea7078D16aD35D6907f034487483C
- **ave** https://ave.ai/token/0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9-bsc

## The most important information about the contract
- Single, unified transfer fee schedule (no separate buy/sell code).
- Fees (basis points over 10,000): `_tax fee` (reflections), `_liquidity fee` (automatic LP), `_charity fee` (Down `_address of the charity`).
- **Hard hat:** `_tax + _liq + _charity ≤ 25%` (constructor + setters).
- **Convert and liquefy threshold:** by default ~0.1% of supply; the owner can set but **≥ 0.05%**.
- Owner tools: `set*Fee percentage`, `setSwapBackSettings`, `exclude from fee`, `exclude from/include in reward`, `transfer of ownership`, `give up ownership`.

## Check/Create notes
- **Compiler:** Solidity `0.8.4` (accurate), **Optimization of 200 runs**.  
- If BscScan shows "Similar Match", this is expected for this template.
- LP tokens are sent to `0xdead` under the liquidity provision agreement.
