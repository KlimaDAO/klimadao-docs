---
description: What does it really mean for KLIMA to be backed by carbon offsets?
---

# Strategies for Defending Backing Value

## Introduction

We say, "KLIMA is backed by carbon offsets" because each KLIMA token has an Intrinsic Value (IV) of 1 BCT - which means the treasury must have at least 1 BCT held in reserves in order to mint 1 KLIMA.  In addition, the treasury contains excess reserves, comprising the [Carbon Custodied (CC)](../references/glossary.md#cc) above 1 BCT which will eventually be [paid out to stakers of KLIMA in the form of rebase rewards](staking.md).&#x20;

However, the actual market price of KLIMA at any given time is dictated by market pressures. The policy team has a variety of levers to ensure that KLIMA will consistently trade above IV, i.e. to defend the backing value.&#x20;

In a typical market, price bounds can be represented broadly as IV < CC/token < KLIMA price. However, this may not always be the case. In order to guarantee a return to backing value, the policy team must have strategies prepared in advance for defending KLIMA’s backing value.

While the policy team always makes decisions for the long-term benefit of the protocol, rapidly shifting market conditions call for a rapid response. As needed, KIPs will be published, proposing to grant the policy team any specific powers required to implement strategies discussed below in response to market conditions.

_NOTE: remember that the treasury prices KLIMA in terms of carbon tonnes - not dollars - so we only discuss the KLIMA price in terms of the tokenized carbon tonnes held by the treasury - primarily BCT at the time of writing._

## KLIMA Trading Below CC But Above IV <a href="#docs-internal-guid-865b0ff4-7fff-1375-a1fa-22f84b1bf4ce" id="docs-internal-guid-865b0ff4-7fff-1375-a1fa-22f84b1bf4ce"></a>

Ultimately, the policy team must maintain the trust and confidence of the community and the market. The best way to do that is by behaving predictably, within the parameters agreed upon by the community.

In such a situation, the policy team would be seeking input from the community about what actions they think are appropriate, as well as clearly communicating any important policy changes prior to implementation.

With that said, in most other Olympus forks, the answer seems straightforward: if the token is trading below the CC per token, the protocol should stop bonding assets, reduce the staking reward rate, and deploy[ inverse bonds](https://forum.olympusdao.finance/d/1020-oip-76-create-inverse-bond-policy-lever). However, [Klima is NOT a typical Olympus fork](https://medium.com/@C\_3/klimadao-an-ohm-clone-on-expert-difficulty-2826a9a412a6).

### Comparison with Vanilla Olympus Mechanics <a href="#docs-internal-guid-2e9c35f7-7fff-f5f5-7008-280e2978a4e7" id="docs-internal-guid-2e9c35f7-7fff-f5f5-7008-280e2978a4e7"></a>

#### Typical Olympus Fork Strategy Below RFV

Bonding assets when the price is below the RFV (called CC in Klima) per token accelerates the reduction of the RFV/token and diminishes the "risk free" nature of the trade (see table below). Thus, the first move for a typical Olympus fork trading below RFV is to disable bonding entirely.

If the RFV/token is $25, for example, and the token is trading at $20, then you ideally want someone who buys 1 token at $20 to feel confident that this is a "risk free" trade for them. Why would it be risk free? Because even if the price per token drops down to $1, the holder still has a claim on a treasury that is equal to $25. Even accounting for staking rewards, which lowers RFV/token assuming no bonding, the holder’s claim remains constant.

However, if the protocol continues selling tokens through bonds to the market at $18, then $16, then $14, and so on, the entire way down, the trade for the original buyer is no longer "risk free": By the end, the holder's claim could be much less than $20 because of these additional tokens on the market.

To illustrate, consider the following simplified scenarios, assuming the above RFV/token of $25:

| <p><br></p>                  | Bonding at $40 | Bonding at $25 | Bonding at $10 |
| ---------------------------- | -------------- | -------------- | -------------- |
| Total Tokens                 | 100            | 100            | 100            |
| Your Tokens                  | 10             | 10             | 10             |
| RFV                          | $2500          | $2500          | $2500          |
| RFV per Token                | $25            | $25            | $25            |
| Your Share of RFV            | $250           | $250           | $250           |
| Total Tokens + 10% (Staking) | 110            | 110            | 110            |
| Your Tokens + 10% (Staking)  | 11             | 11             | 11             |
| RFV per Token                | $22.73         | $22.73         | $22.73         |
| Your Share of RFV            | $250           | $250           | $250           |
| Total Tokens + 10 (Bonding)  | 120            | 120            | 120            |
| RFV After Bonding            | $2900          | $2750          | $2600          |
| RFV per Token                | $24.17         | $22.92         | $21.67         |
| Your Share of RFV            | $265.83        | $252.08        | $238.33        |

### How is KlimaDAO different? <a href="#docs-internal-guid-e33ad20a-7fff-714b-5f30-769e49ed64fd" id="docs-internal-guid-e33ad20a-7fff-714b-5f30-769e49ed64fd"></a>

KlimaDAO is different from most other Olympus forks in that its "risk free" assets are held in non-stable tokens (tokenized carbon offsets). This means that there is an additional reason that KLIMA's price could trade below its CC [(formerly called RFV)](../references/glossary.md#cc) in dollar terms: because the market believes these assets should be worth less in dollar terms than they are currently priced. For example, if the RFV/token is 5 BCT and BCT is currently trading at $5, one would assume the CC/token in dollar terms is $25. However, if the market believes BCT is currently overpriced, this value could very well become $20.

Ultimately, BCT is composed of tokenized Verra carbon offsets, which have inherent use-value to compensate for the emissions of an individual or organization. With BCT trading below off-chain prices for comparable Verra offsets, on-chain offsets like BCT will become increasingly attractive to legacy buyers of offsets. At the same time, as the on-chain offset market matures, tokenized carbon offsets will have many more use-cases and integrations (e.g. user-friendly retirement functionality, additional protocols for borrowing and lending, AMMs built around offsets, automated offsetting through wallet and protocol integrations, and so on). These additional sources of demand will ensure that even if the protocol’s bond facility had to be disabled in a crisis, the on-chain offset market would not collapse.

While disabling bonds entirely is an option for Klima, it would have to be evaluated based on market conditions. If we are in a scenario where KLIMA is trading below RFV but the on-chain carbon market has not yet matured sufficiently to absorb BCT selling, Klima's policy team must be more flexible with the actions it takes. For instance, at the time of writing, bonding is the primary source of demand for on-chain offsets, so disabling bonds entirely could create a negative feedback loop which risks crashing the on-chain carbon offset market.

As such, the protocol prefers to simply reduce bond capacity across the board and adjust the bond minimum prices such that there is no bond discount. This allows the treasury to continue absorbing offsets without excessive dilution. Even then, the bonder still benefits: they don't experience slippage, and they won’t have to pay AMM transaction fees when exchanging bondable assets for KLIMA.

### Available Strategies <a href="#docs-internal-guid-43d976ba-7fff-b7ba-5a04-d39d03c7f852" id="docs-internal-guid-43d976ba-7fff-b7ba-5a04-d39d03c7f852"></a>

#### Adjust Bond Parameters

In order to mitigate the impact of continued bond dilution below CC, bond minimum prices would be adjusted such that the maximum bond discount is 0%. Since adjusting minimum prices is just another mechanism for managing bond capacity, this power falls within the policy team’s existing remit to manage bond capacity without KIP votes.&#x20;

This signal should reassure buyers of KLIMA below CC per token that their claim on the treasury reserves will not be _excessively_ diluted by continued bonding below CC.

_\* NOTE: adjusting bond minimum prices involves deploying a new set of bond contracts which allow minimum price to be adjusted dynamically via a contract function. This change would not be disruptive as existing bonds would continue to vest, and any new bonds would use the new contracts, while the old contracts would be disabled._

#### Reducing Staking Reward Rate

In order to give an irrational market pricing KLIMA below CC the time to correct itself, the policy team may **propose an emergency reduction of the staking reward rate**.

There are some pros and cons: on one hand, this extends the runway, buying time for the DAO to deliver on its vision and demonstrating a long-term commitment to keep the protocol alive. On the other hand, it signals to arbitrageurs buying KLIMA below CC that it may take them longer to actualize their claim on the treasury. This decision will need to be taken very carefully based on market conditions and the current reward rate at the time.

As always, **significant reward rate reductions will be voted on by the community of token holders through the** [**normal governance process**](../dao/governance-framework.md). Any such proposal will be put forward before the runway goes down too far, so the community has the usual period of \~10 days (5 days for informal vote on the forum, 5 days for formal token vote on Snapshot) to provide input and discuss the rationale for the reduction.&#x20;

Assuming an emergency reward rate reduction proposal passes, the reduction would be implemented rapidly to maximize the impact of the emergency change, rather than in the usual gradual manner over the course of a week.

### Seek Yield on Treasury Assets?

In theory the policy could take out debt against its reserve assets to deposit into a yield-generating protocol, like QiDAO’s Green Locker for BCT. But, **this is a big risk for a relatively small reward**. Furthermore, committing reserves to a risky position during a downturn could jeopardize the ability of the community to vote to liquidate the treasury, since those reserves might not be available immediately for distribution. **Security** and **facilitating** a carbon market is magnitudes more important than **yield** for this protocol.&#x20;

While we do plan to eventually put the treasury’s assets to use by investing in offset projects and by incubating new protocols in our ecosystem, **we do not plan to seek out risky investments while the protocol is hurting**, as this jeopardizes trust in the backing value of KLIMA.

## KLIMA Trading Below IV of 1 BCT <a href="#docs-internal-guid-85386cff-7fff-17ba-1eac-16f1dd11b87d" id="docs-internal-guid-85386cff-7fff-17ba-1eac-16f1dd11b87d"></a>

In the case that demand for KLIMA stagnates completely, the protocol's reserves can step in to catch the market. The policy team manages this risk through forward guidance: the fact that the protocol _will_ buy lowers risk the lower we go, which can mean we end up _not having to_ buy. Thus, the protocol serves as the "buyer of last resort" for KLIMA below IV.

### Inverse Bonds

In the event that KLIMA were to trade persistently below IV, as a last resort the policy team plans to launch inverse bonds, which accept KLIMA in return for BCT at a discounted rate, and then the bonded KLIMA is burned, shrinking the supply of KLIMA. This process increases the backing per KLIMA and extends the runway.

The ability to introduce inverse bonds was not initially a part of the protocol, but was [voted](https://snapshot.org/#/klimadao.eth/proposal/0xa72601fcee690c061a8bba6e717ee74db09f782eb3bbbefeaf27ce1e2dad0a35) for by the token holders on Feb 17, 2022 within the framework of KIP-12.

This method has very similar results to manual buyback-and-burn, but does not require manual action by the policy team based on market conditions - rather than the automated market-driven mechanism provided by inverse bonds.

For example, consider the scenario where an inverse bond can buy 1 KLIMA for 0.5 BCT. In that case, for every 1 BCT in the treasury, 2 KLIMA are taken off of the market. Then, given that 1 KLIMA < 1 BCT = IV, CC/token increases from this inverse bonding (that is, while the treasury - and hence the RFV - decreases, the number of circulating tokens decreases faster).&#x20;

While inverse bonds could be launched between CC and IV, they are only effective at boosting CC/KLIMA when KLIMA is trading below IV – while they do take KLIMA tokens out of circulation between CC and IV, RFV/token would decrease faster than supply.

### Endgame: Restart the Flywheel

In the event that KLIMA persistently trades around IV, and inverse bonds or manual buy-backs continuing to burn KLIMA any time it trades below IV, eventually the protocol would be left with a much smaller total supply of KLIMA.&#x20;

Assuming all inverse bonders are selling their BCT for USDC, that BCT would end up in the BCT/USDC liquidity pool owned almost entirely by the Klima treasury. In the most extreme scenario, all of the KLIMA supply would be bought back and burned, and the treasury would end up with more BCT than we had initially (though most of it in the LP pools instead of reserves) - so with just a small amount of bonding we can restart the[ liquidity flywheel](https://klimadao.medium.com/klima-dao-as-a-liquidity-engine-3a806ce5d3d5) with a much higher initial balance of BCT and USDC.&#x20;

**With responsible treasury management, the KlimaDAO protocol can rise like a phoenix from the ashes of even the most dramatic market collapse.**

## The Only Way Out Is Through

In a scenario where KLIMA is persistently trading significantly below CC or IV, the policy team can only do so much to drive additional reserves to the treasury and to reinvigorate the protocol on its own - the rest of the DAO must deliver on our business development goals, including executing marketing campaigns, shipping new reserve-generating products and securing high impact partnerships to allow for a full recovery.

The DAO contributors and core team are all here for the long haul: KlimaDAO has always been a long-term project with a decadal scope. **We have no intention of liquidating the treasury prematurely, nor of letting the protocol stagnate.**
