# Glossary

## AKR

Annualized KLIMA Rewards is the annualized reward rate in percentage terms, taking into account autocompounding over one year assuming a constant reward yield and constant epoch length.&#x20;

Note that AKR is quoted as a ballpark estimate and does not guarantee precise future returns. AKR will go down periodically in accordance with [KIP-3](https://snapshot.org/#/klimadao.eth/proposal/0xbe5ba88701e09fad2548ec2aca539b23cc04a5b7bc1961397fc98a0a303c5249) and fluctuates along with [Reward Yield](glossary.md#reward-yield) due to changes in % of KLIMA staked and Polygon blocktime variability.

_NOTE: AKR was previously called APY._

## APR

Annual Percentage Rate, is the annualized reward rate without taking the effect of compounding into account.

## **BCT**

BCT (Base Carbon Tonne) is a carbon pool governed by KlimaDAO, which accepts any TCO2, independent of project type (e.g. forestry carbon offsets, renewable energy carbon offsets or methane capture offsets). BCT was developed for the launch of KlimaDAO, and as of [KIP-57](https://snapshot.org/#/klimadao.eth/proposal/0xcef69824ff641a9a0951e6de77e2eda724efb335372e98f72e2f7d40fc3fb01b) is managed and owned by KlimaDAO. At this time, the only requirements for TCO2s to be eligible for deposit into the BCT pool are: the TCO2 is verified by Verra, and has vintage later than 2008 (there is also one [blacklisted methodology](https://docs.toucan.earth/protocol/bridge/carbon-bridge/blocklist)).

## CC

Carbon Custodied, the total amount of tokenized carbon offsets held by the treasury to back KLIMA supply. Includes all carbon offset reserves (e.g. naked BCT, MCO2), as well as a marked down portion of KLIMA/carbon liquidity pairs.

This metric was formally referred to as "RFV" or "risk-free value" in the context of the Olympus protocol, whose backing is dollar stablecoins. Since carbon offsets are volatile assets whose price can vary over time, this value is not actually "risk free" in the KlimaDAO protocol.&#x20;

The carbon is considered "custodied" because, if incoming reserves were to drop to 0 and the protocol simply paid out all remaining staking rewards, CC would be the final supply of KLIMA, backed at IV of 1 tonne of carbon offsets. So, in this endgame scenario, each 1 KLIMA would end up being a claim on 1 tonne of carbon offsets from the treasury - thus CC/KLIMA is the estimated number of carbon offset tonnes that a holder of 1 KLIMA today would have after all staking rewards are paid out if they remain staked until the end.

## C3 Token

A utility token for the [C3 carbon bridge](https://www.c3.app/). It is distributed as a reward to users of the protocol that stake, bridge or provide liquidity. C3 can be locked for veC3, which is eligible to vote on C3 protocol decisions and gauge weights. See the [C3 docs](https://c3-bridge.gitbook.io/c3-documentation/carbonomics/c3) for more details on the C3 token.

## C3T

C3 Tonne (C3T) is the general term for fungible tokenized carbon offsets bridged via C3. When you fractionalize the C3VCU NFT received after bridging, the resulting C3T ERC20 token will have C3T- as a prefix, followed by an information-rich name that includes the registry of origin, the project, and the vintage.

## DAO

Decentralized Autonomous Organization, is a governance mechanism for making decisions in a more trustless and collaborative way. Voting rights are often bound to a governance token.

## DCV

Deflation Control Variable, is the scaling factor at which protocol defined buy pressure changes. A higher DCV means more buy pressure from the protocol, resulting in a higher deflation. A lower DCV means less buy pressure from the protocol, resulting in a lower deflation.

## EVM

Ethereum Virtual Machine, is a state machine in which all Ethereum accounts and smart contracts live. At any given block in the chain, Ethereum has one and only one canonical state, and the EVM is what defines the rules for computing a new valid state from block to block.

## KIP

Klima Improvement Proposal, the principle mechanism for DAO governance. Most KIPs begin as posts on our [discussion forum](https://forum.klimadao.finance), either proposed by DAO contributors, sourced from the community, or brought forward by a third party (typically to propose a partnership).

All KIPs must pass a vote by token holders on Snapshot prior to implementation - see our [Governance Framework](../dao/governance-framework.md) for more details on the KIP lifecycle.

## KI

Klima Infinity is a set of products and features built on top of the core protocol, geared toward scaling the traditional [VCM](glossary.md#undefined) by empowering organizations and individuals to quickly source and retire tokenized carbon credits, to become “climate positive”.

## **klima**

The word for "climate" (in Greek and German and many other languages).&#x20;

## **KLIMA**

The primary KlimaDAO token. Each KLIMA is backed by at least one tonne of carbon locked in the KlimaDAO treasury. KLIMA has an intrinsic value underpinned by the value of the carbon reserves. KLIMA is an ERC-20 token originally lauched on the Polygon PoS network.  &#x20;

## MC

Market capitalization - total market value of all KLIMA tokens in existence \
\
`KLIMA price * KLIMA supply`

## MCO2

Moss Carbon Credit (MCO2) is a relatively homogenenous, centrally managed pool of tokenized Verra [VCUs](glossary.md#vcu). Moss created it in August 2020, by curating REDD+ projects in the Amazon Rainforest (one in Peru, five in Brazil). \
\
MCO2 was the first tokenized carbon credit to be listed on major centralised exchanges like Gemini and Coinbase, and the reconciliation of its ledger pool is done in real time by crypto auditor Armanino.

More information is available on the [Moss website](https://mco2token.moss.earth/).

## NCT

NCT (Nature-Based Carbon Tonne) is a Toucan Protocol carbon pool, which accepts TCO2 from nature-based methodologies such as avoided deforestation or afforestation. \
\
See [this page from Toucan](https://docs.toucan.earth/protocol/pool/pool-parties/nct-pool-party-report) for the detailed requirements for pooling TCO2 into NCT.

## POL

Protocol Owned Liquidity, is the amount of LP the treasury owns and controls. The more POL the better for the protocol and its users.

## Reward Rate

Reward rate is the configured percentage of KLIMA distributed to all stakers on each rebase relative to the total supply. The reward rate is precisely set by the policy team.

## Reward Yield

Reward yield refers to the actual amount of KLIMA received by each staker on each rebase. The reward yield is a rough target from a policy point of view. It can almost never be maintained precisely due to fluctuating percentage of KLIMA staked and variabilities in Polygon blocktimes.

## RFV

Risk Free Value - this term has been deprecated in favor of [Carbon Custodied (CC)](glossary.md#undefined)

## SLP

Sushiswap Liquidity Provider, is the token received when providing liquidity on Sushiswap.

## **Staking**

Market participants can deposit their KLIMA tokens in the staking contract to receive additional KLIMA as reward in return. These rewards are distributed via rebasing of the staked token (sKLIMA), which can be unstaked at any time to receive an equal amount of KLIMA.

[See the Staking page for more details.](../economics/purpose/)

## TCO2

Toucan Carbon Tokens (TCO2) is the general term for fungible tokenized carbon offsets bridged via Toucan. When you fractionalize a BatchNFT received after bridging, the resulting TCO2 ERC20 token will have TCO2- as a prefix, followed by an information-rich name that includes the registry of origin, the project, the vintage, and so on. More information on the tokenization process can be found in the [Toucan docs](https://docs.toucan.earth/protocol/bridge/tco2-toucan-carbon-tokens).

## Tokenized Carbon Asset

A Tokenized Carbon Asset (TCA) refers to a carbon asset (e.g. voluntary carbon offset) brought onto the blockchain.\
\
TCAs are usually represented as an NFT for bridging purposes, since carbon assets are typically only semi-fungible: each asset has attributes such as vintage, methodology, and country of origin. Tokenized carbon can refer to a single unit (e.g. one carbon offset) or a batch of assets (e.g. a certain number of carbon offsets from a specific project and vintage period). These NFTs can be deposited into Carbon Pools to create fungible ERC-20 tokens representative of that tokenized can that meets those pool's requirements.

## TMV

Treasury Market Value - the current market value in dollars of all assets held in the treasury, including both reserves and all LP tokens.

## TTC

Treasury Total Carbon - total carbon offset tonnage held by the KlimaDAO treasury, including both carbon offset reserves and the full value of the carbon assets in all carbon-paired LP pools (both KLIMA/carbon and stablecoin/carbon pairs).

Note that this value fluctuates up or down as carbon offsets are sold into or bought out of the liquidity pools.

## TWAP

Time Weighted Average Price, is the average price of an asset over a specified time. TWAPs are used to represent the fair value of an asset as defined by the market.

## VCU

Verified Carbon Unit (VCU) is a carbon credit issued under the Verra Carbon Standard (VCS). Under the VCS Program, projects are issued unique carbon credits known as Verified Carbon Units or VCUs. Each VCU represents a reduction or removal of one tonne of carbon dioxide equivalent (CO2e) achieved by a project. VCUs are characterized by a number of [quality assurance principles](https://verra.org/project/vcs-quality-assurance-principles/) which are confirmed through the project [validation and verification](https://verra.org/project/vcs-program/validation-verification/) process. VCUs are ultimately purchased and retired by an end user as a means of offsetting their emissions. All VCU issuance and retirement records are publicly available on the [Verra Registry](https://registry.verra.org/).

## VCM

The Voluntary Carbon Market is a key tool in the fight against catatrophic climate change. The VCM enables consumers and organizations to fund of projects with real-world climate impact via modern financial market.

The VCM has been around for decades, but has long suffered from lack of access, opacity, illiquidity, and high transaction fees. KlimaDAO aims to change that by migrating the VCM on-chain, where all market participants can benefit from the advantages of distributed ledger technology.
