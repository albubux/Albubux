# Albubux (BUBX) - Whitepaper

**Network:** BNB Smart Chain (BEP-20)  
**Contract:** `0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9` (see BscScan for deployment and verification)  
**Name / Symbol / Decimals:** Albubux / BUBX / 9  
**Total Supply:** refer to BscScan "Read Contract"

---

## 1. Overview

Albubux is a community-driven token for transparent tokenomics and real-world utility (payments, charitable impact, partner programs). The smart contract is a **LiquidityGeneratorToken** that implements:
- **Reflection ("tax fee")** distributed to holders.
- **Automatic liquidity** via swap-and-liquify. LP tokens are sent to **`0xdead`**.
- **Optional charity fee** forwarded to a configured `_charityAddress`. If the charity address is `0x0`, the effective charity fee is 0.

**Presale/Fair-launch:** fees at **0%**.  
**Post-listing policy:** small total fee (initial target ~**1%**), with a **public policy cap <= 5%**.  
**On-chain limit:** sum of fees cannot exceed **25%**.

---

## 2. What the Code Enforces

- **Single fee schedule** for transfers. No encoded buy-only or sell-only fees.
- **Fee components** (basis points, per 10,000):
  - `_taxFee` (holder reflections),
  - `_liquidityFee` (accumulated and auto-added to liquidity; half swap to BNB, half pair; LP sent to `0xdead`),
  - `_charityFee` (forwarded to `_charityAddress`; if `_charityAddress == 0x0`, calculation yields 0).
- **Hard cap on total fees:** `_taxFee + _liquidityFee + _charityFee <= 25%` (constructor and setters enforce).
- **Swap-and-liquify threshold:** initialized at about **0.1%** of total supply; owner can adjust via `setSwapBackSettings(amount)` but **not below 0.05%** of supply.
- **Ownership & exclusions:** standard `Ownable`; `excludeFromFee`, `excludeFromReward`, `includeInReward`.
- **Router/Pair:** router is provided at deploy; pair is created against `WETH()` (WBNB on BSC).

Live parameters (current fees, threshold, router, charity address) should be read from BscScan.

---

## 3. Tokenomics Policy (Off-chain Governance)

- **Presale:** 0% fees.  
- **After listing:** small total fee (target ~1%) to sustain liquidity operations and impact programs.  
- **Policy cap:** public commitment not to exceed 5% total fee unless re-approved; on-chain limit remains 25%.

If specific allocations (presale %, liquidity %, marketing %, team %, airdrop %) are published, they must be accompanied by wallet addresses and lock/vesting proofs.

---

## 4. Utilities and Roadmap (No base contract migration)

Utilities are delivered via companion contracts or off-chain services; the base token contract remains unchanged.

- **Gaming / NFTs:** micro-transactions, perk NFTs, events; SDK for indie partners first, then mid-size studios.  
- **E-commerce & promo codes:** partner pilots with token-gated discounts; affiliate dashboards; evaluate payment acceptance in selected jurisdictions.  
- **Payments:** selective merchant acceptance post-compliance; wallet UX bridges.

**Roadmap (high level):**
- **Post-presale:** DEX listing with locked LP; publish addresses and lock proofs; community governance for charity targets.  
- **H1–H2:** pilots (promo codes), indie SDK, first integrations; quarterly KPI reporting; expand utilities.  
- **Ongoing:** reduce fees as liquidity deepens (subject to community process).

Third-party brand names, if mentioned, are targets for exploration only unless explicitly announced.

---

## 5. Governance and Transparency

- **Open reporting:** treasury flows, charity disbursements with tx hashes, and any fee changes.  
- **Community input:** token-weighted signalling/votes for charity destinations and optional fee reductions.  
- **Security posture:** audits/KYC (if commissioned) published; multi-sig for key wallets; incident playbook for companion modules.

---

## 6. Risk and Compliance

- Crypto assets are volatile; this is not investment advice.  
- Features may vary by jurisdiction.  
- This document reflects what the **deployed code** does and the **project policy**; for exact live parameters check BscScan.

---

## 7. Owner Functions (Reference)

- `setTaxFeePercent(uint256)`  
- `setLiquidityFeePercent(uint256)`  
- `setCharityFeePercent(uint256)`  
- `setSwapBackSettings(uint256)` (must be >= 0.05% of total supply)  
- `excludeFromFee(address)`  
- `excludeFromReward(address)` / `includeInReward(address)`  
- `transferOwnership(address)` / `renounceOwnership()`

---

## 8. Links

- BscScan: https://bscscan.com/address/0x4843588e66700eD5E2C4F8BC6f9b61E686d9cDa9  
- PinkSale: (insert live URL)  
- Repository: https://github.com/albubux/albubux-token

---

## 9. License

MIT © Albubux Project Developers
