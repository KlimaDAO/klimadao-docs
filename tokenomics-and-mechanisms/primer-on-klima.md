# Primer on KLIMA

## Purpose of the KLIMA token

KlimaDAO uses the KLIMA token as an algorithmic reserve currency and key liquidity pair. On a high level, the token has 4 axioms:&#x20;

1. **Every KLIMA token has an Intrinsic Value (IV) backing the token.** While there can be more assets backing the token, there is a minimum value associated with the token. Hence, there is a price floor, but no price ceiling of the protocol.  As of today, the Intrinsic value is 1 carbon tonne. In other words, **every KLIMA token is backed by at least 1 Carbon Tonne.**&#x20;
2. **The KLIMA token can only be minted or burned by the protocol.** The protocol serves as the "decentralized, central bank" of the token, with the ability to expand and contract supply.
3. **When KLIMA is trading above the IV, the protocol expands supply, and sells KLIMA to the market.** Because the protocol can create more supply, as long there is the IV backing the token, it generates excess reserves from the spread between IV and market price.&#x20;
4. **When KLIMA is trading below IV, the protocol buys and burns KLIMA, contracting supply.** Because it buys the token under the intrinsic value, the protocol bolsters reserves per KLIMA from the spread.&#x20;

From these market operations, we can see that the protocol gives the user certainty that KLIMA will not be valued under intrinsic value in the long term. This provides a sense of security and confidence for the users that the protocol will step in as the last buyer of resort, because the protocol can and will buy KLIMA below the IV, even if the supply is reduced to 0. In fact, an event like this would be very advantageous for those who didn't sell, as their % supply grows and grows.&#x20;

Whenever the protocol generates excess reserves, the protocol can utilize this in many ways. Today, the protocol distributes excess reserves to stakers via rebase rewards, and to the DAO from fees on bonding. All the rewards are paid in KLIMA, backed by carbon assets. This incentivizes users to keep their KLIMA staked, reducing selling pressure placed on the token. This greatly reduces the pressure for price appreciation for the users, and shifts the emphasis to supply accumulation in order to generate a return.&#x20;

The end goal for the KLIMA token is to have a stable value dictated by the market that tracks the relative value of the environmental assets which comprise the treasury. A great reserve currency requires a large and robust treasury from which to derive value. It also needs a large supply and adequate liquidity in order to facilitate transactions and develop as a unit of account. Additionally, a great currency is nothing without adoption; if no one uses KLIMA, it's not a good currency.&#x20;

As such, [KIP-8](https://forum.klimadao.finance/d/12-kip-8-introduce-klimausdc-bonds) established KLIMA as the key liquidity pair with which the treasury pairs each carbon credit pool for which it provides [POL](the-importance-of-pol.md). Through this mechanism, the KLIMA price is coupled to the price of each carbon credit pool.

## Initial Supply

**Our initial goal is not to find a stable carbon price.** It is to provide an intuitive way for Web3 users to engage with the carbon markets, vote on governance proposals that shape the Digital Carbon Market, and be rewarded for participation in the protocol. Through policy and voting, the protocol will be tuned to track developing trends in carbon markets over time.&#x20;

In the early days, the main tradeoff is volatility versus stability and consistency. With volatility comes growth; this is what drives the protocol early on. Towards the middle of the century, we anticipate more stability as KLIMA approaches equilibrium with supply and demand in the carbon markets.&#x20;

At protocol launch, the initial supply was \~251k KLIMA.&#x20;

* \~57k came from the IDO
* 133k came from the LBP
* \~81k came from the alchemist reward program. &#x20;

## Emission Mechanisms  <a href="#docs-internal-guid-f3fe644f-7fff-70f7-8297-63e971faf518" id="docs-internal-guid-f3fe644f-7fff-70f7-8297-63e971faf518"></a>

### Staking Rewards <a href="#docs-internal-guid-f3fe644f-7fff-70f7-8297-63e971faf518" id="docs-internal-guid-f3fe644f-7fff-70f7-8297-63e971faf518"></a>

Additional KLIMA is distributed every epoch through KlimaDAO’s staking rewards. These staking rewards are generated from the excess reserves the KlimaDAO treasury accumulates from selling bonds. A portion of these excess reserves are distributed back to stakers as sKLIMA staking rewards. 1 sKLIMA is redeemable for 1 KLIMA.

KlimaDAO’s staking rewards rate is set by KlimaDAO governance, which can be seen [here](https://dune.xyz/Cujowolf/Klima-Policy). Note that the staking reward rate that a user receives for their staked KLIMA is equal to the KlimaDAO reward rate / % of circulating supply staked.

The framework for KilmaDAO’s staking rewards was ratified by the community in [KIP-](https://snapshot.org/#/klimadao.eth/proposal/0xbe5ba88701e09fad2548ec2aca539b23cc04a5b7bc1961397fc98a0a303c5249)3. KIP-3 was later amended by [KIP-5](https://snapshot.org/#/klimadao.eth/proposal/0x23ad83944ace8d3676cb44a8dadefe845c2db8a78ba7dd008eaa8d2a0bfb50e5) because block times on Polygon were shorter than expected: average rebases have been trending closer to \~7.2 hours instead of the expected 8 hours.&#x20;

### Bonding

KLIMA is also minted and distributed when users [bond](https://dapp.klimadao.finance/#/bonds) assets to KlimaDAO. An explanation of KlimaDAO’s bonding mechanism can be found [here](https://docs.klimadao.finance/bonding-staking-and-game-theory), and the amount of KLIMA minted for bonds can be seen on this [dashboard](https://dune.xyz/Cujowolf/KLIMA-Minting-and-Runway-Metrics).&#x20;

In addition to the amount of KLIMA minted for the bonder, an extra 30% of the bond value is minted for the DAO wallet to fund operations. For example, if a user bonds assets valued at 10 KLIMA, 10 KLIMA will be minted for the bonder and 3 KLIMA will be minted for the DAO.

### pKLIMA Redemption

KlimaDAO distributed [pKLIMA](https://klimadao.medium.com/?p=6bf78981d1a) to individuals and organizations committed to helping KlimaDAO become a long-term success. pKLIMA is vested based on supply share. For example, the team’s supply share is vested at 7.8%, meaning when the protocol has a supply of 1 million KLIMA, 78,000 pKLIMA can be redeemed by the team.

* Team: 330m pKLIMA, and 7.8% supply share
* Project stakeholders: 70m pKLIMA, and 3.5% supply share
* Advisors: 50m pKLIMA, and 1% supply share
* OlympusDAO: 70m pKLIMA, and 3.5% supply share
* KlimaDAO community: 480m pKLIMA (no supply share)

Cumulatively, all of the stakeholder groups can never own more than 15.8% of total KLIMA supply.&#x20;

pKLIMA is not the same as KLIMA, aKLIMA or alKLIMA. KLIMA, aKLIMA, and alKLIMA are all backed by 1 BCT. In order to mint any of these tokens, 1 BCT must be locked in the treasury. There are no underlying BCTs locked in the treasury to underpin the distributed pKLIMA supply. To redeem pKLIMA, holders will be responsible for delivering BCTs to the treasury themselves, 1 BCT for each claimed pKLIMA. By limiting pKLIMA to a % supply share and requiring holders to deliver BCTs to the treasury themselves, pKLIMA ensures that stakeholders, partners, core-members, and community contributors are all focused on the same goal: growing our carbon-backed treasury for long-term success.

#### Post-Launch Excess pKLIMA Redemption

Until the launch of the wsKLIMA token several weeks after launch, there was a minor implementation issue in the pKLIMA contract that allowed for pKLIMA holders to redeem pKLIMA even though they had a greater % supply share than should be allowed. The original contract could not account for the fact that pKLIMA holders may have staked and earned rebase rewards on previously claimed tokens until the wsKLIMA contract was deployed, providing a way to calculate the index-adjusted value of KLIMA.&#x20;

The fix was deployed on November 24, 2021 and will gradually automatically correct the issue by preventing further pKLIMA redemption until supply grows sufficiently to bring all pKLIMA allocations in line with vesting limits.&#x20;

![](https://lh5.googleusercontent.com/ZyuXKRQB9JwJR8VWhgQBV-vpOUdIPkRWWcvQkh52phnEjcIlFRPhIpb9v6ykQakgLGeQ5Z16a\_l33DZ3dJRnacbxJlvAzbsEMV0G2Ev3MtbtA-l3FlKwtuVsqi7x5dUx9YM1vTTf)

## Maximum Supply? <a href="#docs-internal-guid-27aa7fcb-7fff-06d7-6edc-84d64f3ade5a" id="docs-internal-guid-27aa7fcb-7fff-06d7-6edc-84d64f3ade5a"></a>

Since each KLIMA must be backed by at least 1 tonne of tokenized carbon offsets held in reserves by the treasury, the maximum supply of KLIMA at any given time is limited to the number of tokenized carbon tonnes held in the treasury’s reserves (see Dune for up-to-date metrics).

However, this total can grow over time as more offsets are delivered to the treasury via bonds or pKLIMA redemption. So, the practical limit on the number of tonnes that can be brought into the Klima treasury at any point in time is the total offset tonnage that has been bridged on-chain thus far.&#x20;

That said, assuming no further bridging, a larger and larger percentage of on-chain offsets would eventually be absorbed into the Klima treasury, which would push up on-chain offset prices and incentivize more offsets to be bridged to capture any price difference with the off-chain offset market.

The true limit on the total supply of KLIMA is the total number of outstanding verified carbon offsets in existence - as of the time of writing this is about 500 million tonnes, but more offsets can be issued by registries like Verra as new offsetting projects complete their verification and issuance process.

Thus, there is no fixed upper bound on the total supply of KLIMA - as long as more offsets are being generated, bridged, and bonded to the treasury, KLIMA supply can continue to grow.
