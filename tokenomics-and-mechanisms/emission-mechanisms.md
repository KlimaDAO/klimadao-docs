---
description: Mechanisms that mint KLIMA, increasing total supply
---

# Emission Mechanisms

## Staking Rewards <a href="#docs-internal-guid-f3fe644f-7fff-70f7-8297-63e971faf518" id="docs-internal-guid-f3fe644f-7fff-70f7-8297-63e971faf518"></a>

Additional KLIMA is distributed every epoch through KlimaDAO’s staking rewards. These staking rewards are generated from the excess reserves the KlimaDAO treasury accumulates from selling bonds. A portion of these excess reserves are distributed back to stakers as sKLIMA staking rewards. 1 sKLIMA is redeemable for 1 KLIMA.

KlimaDAO’s staking rewards rate is set by KlimaDAO governance, which can be seen [here](https://dune.xyz/Cujowolf/Klima-Policy). Note that the staking reward rate that a user receives for their staked KLIMA is equal to the KlimaDAO reward rate / % of circulating supply staked.

The framework for KilmaDAO’s staking rewards was ratified by the community in [KIP-](https://snapshot.org/#/klimadao.eth/proposal/0xbe5ba88701e09fad2548ec2aca539b23cc04a5b7bc1961397fc98a0a303c5249)3. KIP-3 was later amended by [KIP-5](https://snapshot.org/#/klimadao.eth/proposal/0x23ad83944ace8d3676cb44a8dadefe845c2db8a78ba7dd008eaa8d2a0bfb50e5) because block times on Polygon were shorter than expected: average rebases have been trending closer to \~7.2 hours instead of the expected 8 hours.&#x20;

## Bonding

KLIMA is also minted and distributed when users [bond](https://dapp.klimadao.finance/#/bonds) assets to KlimaDAO. An explanation of KlimaDAO’s bonding mechanism can be found [here](https://docs.klimadao.finance/bonding-staking-and-game-theory), and the amount of KLIMA minted for bonds can be seen on this [dashboard](https://dune.xyz/Cujowolf/KLIMA-Minting-and-Runway-Metrics).&#x20;

In addition to the amount of KLIMA minted for the bonder, an extra 30% of the bond value is minted for the DAO wallet to fund operations. For example, if a user bonds assets valued at 10 KLIMA, 10 KLIMA will be minted for the bonder and 3 KLIMA will be minted for the DAO.

## pKLIMA Redemption

KlimaDAO distributed [pKLIMA](https://klimadao.medium.com/?p=6bf78981d1a) to individuals and organizations committed to helping KlimaDAO become a long-term success. pKLIMA is vested based on supply share. For example, the team’s supply share is vested at 7.8%, meaning when the protocol has a supply of 1 million KLIMA, 78,000 pKLIMA can be redeemed by the team.

* Team: 330m pKLIMA, and 7.8% supply share
* Project stakeholders: 70m pKLIMA, and 3.5% supply share
* Advisors: 50m pKLIMA, and 1% supply share
* OlympusDAO: 70m pKLIMA, and 3.5% supply share
* KlimaDAO community: 480m pKLIMA (no supply share)

Cumulatively, all of the stakeholder groups can never own more than 15.8% of total KLIMA supply.&#x20;

pKLIMA is not the same as KLIMA, aKLIMA or alKLIMA. KLIMA, aKLIMA, and alKLIMA are all backed by 1 BCT. In order to mint any of these tokens, 1 BCT must be locked in the treasury. There are no underlying BCTs locked in the treasury to underpin the distributed pKLIMA supply. To redeem pKLIMA, holders will be responsible for delivering BCTs to the treasury themselves, 1 BCT for each claimed pKLIMA. By limiting pKLIMA to a % supply share and requiring holders to deliver BCTs to the treasury themselves, pKLIMA ensures that stakeholders, partners, core-members, and community contributors are all focused on the same goal: growing our carbon-backed treasury for long-term success.

### Post-Launch Excess pKLIMA Redemption

Until the launch of the wsKLIMA token several weeks after launch, there was a minor implementation issue in the pKLIMA contract that allowed for pKLIMA holders to redeem pKLIMA even though they had a greater % supply share than should be allowed. The original contract could not account for the fact that pKLIMA holders may have staked and earned rebase rewards on previously claimed tokens until the wsKLIMA contract was deployed, providing a way to calculate the index-adjusted value of KLIMA.&#x20;

The fix was deployed on November 24, 2021 and will gradually automatically correct the issue by preventing further pKLIMA redemption until supply grows sufficiently to bring all pKLIMA allocations in line with vesting limits.&#x20;

![](https://lh5.googleusercontent.com/ZyuXKRQB9JwJR8VWhgQBV-vpOUdIPkRWWcvQkh52phnEjcIlFRPhIpb9v6ykQakgLGeQ5Z16a\_l33DZ3dJRnacbxJlvAzbsEMV0G2Ev3MtbtA-l3FlKwtuVsqi7x5dUx9YM1vTTf)

## Maximum Supply? <a href="#docs-internal-guid-27aa7fcb-7fff-06d7-6edc-84d64f3ade5a" id="docs-internal-guid-27aa7fcb-7fff-06d7-6edc-84d64f3ade5a"></a>

Since each KLIMA must be backed by at least 1 tonne of tokenized carbon offsets held in reserves by the treasury, the maximum supply of KLIMA at any given time is limited to the number of tokenized carbon tonnes held in the treasury’s reserves (see Dune for up-to-date metrics).

However, this total can grow over time as more offsets are delivered to the treasury via bonds or pKLIMA redemption. So, the practical limit on the number of tonnes that can be brought into the Klima treasury at any point in time is the total offset tonnage that has been bridged on-chain thus far.&#x20;

That said, assuming no further bridging, a larger and larger percentage of on-chain offsets would eventually be absorbed into the Klima treasury, which would push up on-chain offset prices and incentivize more offsets to be bridged to capture any price difference with the off-chain offset market.

The true limit on the total supply of KLIMA is the total number of outstanding verified carbon offsets in existence - as of the time of writing this is about 500 million tonnes, but more offsets can be issued by registries like Verra as new offsetting projects complete their verification and issuance process.

Thus, there is no fixed upper bound on the total supply of KLIMA - as long as more offsets are being generated, bridged, and bonded to the treasury, KLIMA supply can continue to grow.

\
