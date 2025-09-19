# Albubux (BUBX) — Investor README

**Chain:** BNB Smart Chain (BEP-20)  
**Contract:** `0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9`  
**Name / Symbol / Decimals:** Albubux / BUBX / 9  
**Max Supply:** as deployed on BscScan (see “Read Contract”)

## Quick Facts
- Template: **LiquidityGeneratorToken** (reflections + auto-liquidity + optional charity)
- Fees: single transfer fee (no buy/sell separation)  
  Sum of `tax + liquidity + charity` **≤ 25% (hard cap in code)**  
  Project policy: **0% during presale**, then **~1% target**, **≤ 5% policy cap**
- Swap & liquify threshold: default ~**0.1%** of supply; min **0.05%** (owner setting)
- LP tokens sent to **`0xdead`**

## Compile / Verify
- Compiler: **Solidity 0.8.4**, optimization **200 runs**
- Source file: `contract/Albubux.sol`
- Constructor args (PinkSale template):  
  `name_ (string), symbol_ (string), totalSupply_ (uint256), router_ (address), charityAddress_ (address), taxFeeBps_ (uint16), liquidityFeeBps_ (uint16), charityFeeBps_ (uint16), serviceFeeReceiver_ (address), serviceFee_ (uint256 payable)`

## Owner Functions (reference)
- `setTaxFeePercent`, `setLiquidityFeePercent`, `setCharityFeePercent`  
  *(sum must stay ≤ 25%; charity must be 0 if charity address is 0x0)*
- `setSwapBackSettings(amount)` *(≥ 0.05% of total supply)*
- `excludeFromFee`, `excludeFromReward`, `includeInReward`
- `transferOwnership`, `renounceOwnership`

## Links
- BscScan: https://bscscan.com/address/0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9  
- PinkSale: (add your launchpad URL)  
- Whitepaper: `./Albubux_Whitepaper.md`

## License
MIT © 2025 Albubux Project Developers
