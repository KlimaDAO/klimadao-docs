# Klima 2.0 Fair Launch - Intro FAQ  

*"Markets are superb at setting prices, but incapable of recognizing the price of their success."*  

## What is Klima 2.0?  

Klima 2.0 is a redesigned decentralized carbon market aimed at enhancing carbon pricing, retirement, and offset mechanisms. Our new model introduces a bond market, an economic governance token $KlimaX, a synthetic pricing model for carbon credits, and an Automated Asset Manager (AAM) that facilitates pricing and liquidity for tokenized carbon assets via $KLIMA. The functionality of Klima 2.0 will live within the Klima Protocol.  

## What is an Automated Asset Manager?  

An Automated Asset Manager (AAM) is a collection of smart contracts that facilitate pricing and trading of assets. Klima is applying this technology to carbon credits. The AAM enables carbon asset issuers to access deep liquidity through synthetic pricing of real-world assets (RWAs) using $KLIMA and $KlimaX. The AAM pays for carbon credits, and resells the credits as offset retirements - all transactions settled onchain via $KLIMA.  

## What is the Fair Launch?  

The Fair Launch is a program to transition the restructuring of the legacy $KLIMA token.

Legacy $KLIMA holders can stake their legacy tokens to receive the new Klima 2.0 tokens ($KLIMA + $KlimaX). New $KLIMA is distributed pro-rata upon relaunch, calculated as a share of $KLIMA staked. $KlimaX is distributed pro-rata upon relaunch, calculated as share of points accrued. 

Stake early and earn more points. Stake longer, earn more points. Unstake, and an increasing share of legacy $KLIMA are burned. Points lost from unstaking are redistributed to the remaining stakes. Any legacy $KLIMA not staked will not be eligible for new $KLIMA on relaunch.  

## What if I don't stake?  

Unstaked legacy $KLIMA tokens will maintain their 1:1 BCT backing, but will not receive any allocation of new $KLIMA or $KlimaX tokens.  

## Why wouldn't I stake?  

To maintain an option on short-term legacy $KLIMA price volatility.  

## What happens to legacy $KLIMA after relaunch?  

Staked tokens are permanently burned and replaced with new token allocations.

Unstaked tokens maintain 1:1 BCT backing and can still be retired or traded.  

## When exactly does staking start?  

Staking details will be announced on the official Discord and Twitter.  

## When exactly does staking end?  

Staking ends when the Klima 2.0 protocol is ready for deployment.  

Current projections are Q3 2025.  

## Can I add more $KLIMA to my stake over time?  

Yes!  

## How are points calculated exactly?  

**Points Calculation**  

Points = Staked Amount × e^(0.00274 × Days) × Entry Bonus

where **Entry Bonus** is:  
- **2.0x** for **Week 1** participants  
- **1.5x** for **Week 2** participants  
- **1.0x** for all subsequent participants  

To illustrate the compounding effect, consider a 10,000 $KLIMA stake:  

| Time Period  | Points |
|-------------|----------------------|
| **Start**   | 20,000  |
| **Day 7** | 20,387.30236  (+1.94%) |
| **Day 14** | 20,782.10487  (+3.91%) |
| **Day 30** | 21,535.70539  (+7.68%) |
| **Day 90** | 25,593.34287 (+27.97%) |

## Burn Calculation  

Total Burn = Base Burn + Time-Based Burn

where:  

- **Base Burn = 25% of staked amount**  
- **Time-Based Burn** = `min((Days Staked / 365) × 75%, 75%)`  
- **Maximum Total Burn = 100%**  

Example Burn Scenarios  

| Exit Time  | Base Burn | Time-Based Burn | Total Burn |
|------------|-----------|-----------------|------------|
| **Day 30**  | 25.0% | 6.2% | 31.2% |
| **Day 180** | 25.0% | 37.0% | 62.0% |
| **Day 365** | 25.0% | 75.0% | 100.0% |

## How is the burn calculated exactly?  

The burn mechanism creates increasing exit costs over time, reinforcing a "last man standing" dynamic. When a participant unstakes early, the system calculates and executes a burn that grows with time staked.  

## What’s the minimum stake amount?  

1 legacy $KLIMA.  

## Will there be a UI for tracking points/allocations?  

Yes.

## What are the new tokens in Klima 2.0?  

- **$KLIMA**:  Represents a claim on the underlying carbon portfolio. Can be minted in exchange for carbon, and can be burned to obtain carbon retirement certificates.  

- **$KlimaX**: Economic governance token for carbon portfolio management, influencing $KLIMA issuance and retirement rates.  

## What does staking do in Klima 2.0?  

Both sets of token stakers must answer one ‘simple’ question: “Which environmental assets should $KLIMA buy more of?”    

- **$KLIMA staking**: Determines the base pricing of carbon assets.  
- **$KlimaX staking**: Modulates trading capacity and risk management.  

## What does Klima 2.0 do with fees?  

The protocol redistributes fees along a ‘Yield Waterfall’, which allocates 100% of the protocol’s fees and emissions to users, including:  

- Liquidity Providers (LPs) 
- $KLIMA Stakes
- $KlimaX Stakes
- $KlimaX Burns

## How is Klima 2.0 sustainable?  

Klima 2.0 is designed to generate protocol fees by enabling spot carbon swaps and synthetically settling carbon liquidity in $KLIMA pools. All of the collected fees are distributed to stakeholders as emissions via the Yield Waterfall.  

## How are incentives structured in Klima 2.0?

$KLIMA is perpetually mintable, providing evergreen incentives across Klima 2.0.

There are three cohorts across which incentives dynamically allocate:

1. Base yields for $KLIMA stakers (System “risk-free” rate)
2. Liquidity rewards for market-makers (System “risky” yield)
3. Emissions for $KlimaX stakers (System “risky” yield)

“Risk-free” is not meant literally, but as a reference of comparative risk to other cohorts in the system.

## What is the purpose of the bond market in Klima 2.0?

$KLIMA stakers must lock tokens to receive yield.

The bond market generates floating rate returns, awarded to principle and compounded daily, in a zero-coupon instrument. Floating rates derived from the bond market inform the system Discount Rates for forward carbon purchase.

## How does Klima 2.0 manage risk?

Risk is managed through rational system design and properly weighted incentives.

Marginal carbon allocation decisions are based on collective staking, meaning $KLIMA minting is directed towards impact assets in proportion to the desires of those who own the asset.

## How does Klima 2.0 standardize carbon assets?

Our model introduces an on-chain framework that:

1. Standardizes carbon credit classification by “class”.
2. “Class” includes: methodology, region, vintage, and issuer stratification.
3. The AAM dynamically prices and procures spot credits (already issued) and forward credits (those with future delivery dates).
4. Carbon credits within classes are represented as fungible carbon tokens.
5. Fungible carbon tokens allow for automation of issuance and retirement.

## How will Klima transition to 2.0?  

The transition will be executed incrementally:  

1. Fair launch begins.  
2. Migration of existing carbon assets.  
3. Introduction of new market mechanisms.  
4. Immediate decentralization of governance post 2.0 deployment.  
5. Gradual rollout of carbon market integrations.  

## What is the end-game of Klima 2.0?  

Klima 2.0 is designed to become the primary venue for environmental asset liquidity—an essential piece of infrastructure in a global market still constrained by fragmentation and opacity.

Currently, $KLIMA represents under 1% of the total voluntary carbon market in terms of TVL. However, with our synthetic pricing model, bond-driven incentives, and dynamic liquidity rails, Klima Protocol is uniquely positioned to scale. Our vision is for the broader carbon market to increasingly reference Klima prices as a benchmark—driving a feedback loop where activity within the protocol becomes a central signal for market structure and carbon pricing.

In this way, Klima transitions from a participant in the market to one of its most important sources of price discovery and liquidity provisioning.
