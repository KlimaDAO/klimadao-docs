# Retirement Bonds

Originally proposed in [KIP-31](https://forum.klimadao.finance/d/138-kip-31-introduce-retirement-bonds), retirement bonds are a form of inverse bonds where the bonder provides KLIMA tokens in exchange for carbon assets from the protocol which are immediately retired.&#x20;

The KLIMA provided to purchase the carbon is burned (minus 30% fee sent to the DAO). Only KLIMA tokens are accepted to execute these bonds.

Retirement bonds are offered with a maximum slippage amount, acting as an extension of current liquidity pools to support larger retirements.

### Motivation

Retirement bonds were conceived of early in the development of KlimaDAO as a complimentary deflationary mechanism to existing protocol mechanisms which expanded the supply of KLIMA and subsequently the total carbon assets held by the protocol. Retirement bonds were designed as a form of inverse bond with an outcome that is aligned with KlimaDAO's mission.

Further motivation came as KlimaDAO found potential partners seeking to retire substantial amounts of digital carbon credits were being impacted by the limitations of liquidity pool sizes and structure often resulting in significant slippage. This dictated the need for a more efficient use of both protocol-owned-liquidity and overall treasury resources to empower organizations to acquire and retire carbon at larger volumes. Retirement bonds were introduced in January 2023.

### Purpose

Retirement bonds serve a variety of purposes within the KlimaDAO ecosystem:

* **Direct Carbon Retirement:** Users can directly contribute to KlimaDAO's core mission by permanently removing carbon credits from circulation.
* **Treasury Expansion without Dilution:** This mechanism allows the treasury to target specific carbon pools without impacting existing KLIMA holder ownership (dilution).
* **Increased Efficiency for Large Retirements:** Retirement bonds address limitations of current liquidity pools, enabling efficient large-scale carbon credit retirements by partner organizations.

### Technical details

**Pricing:** Each bond is offered at the time-weighted average market rate for the specified carbon credit, with slippage capped at 2% and includes a 30% flat DAO fee.

**Max Bond Amount:** The capacity for each Retirement Bond is configurable for each carbon credit pool.

**Duration:** The bonds will be available until all allocated reserve assets are retired **or** until the end of each month. Each month, the Policy Team can allocate more reserves to the Retirement Bond capacity.

