---
description: Processes and tooling used to govern the Klima protocol
---

# Governance Framework

## Promises and Perils of Decentralized Governance <a href="#docs-internal-guid-ae4a6fe9-7fff-7aba-b99a-9e0626c1dac9" id="docs-internal-guid-ae4a6fe9-7fff-7aba-b99a-9e0626c1dac9"></a>

It’s in the name, Klima is a _DAO_, so it’s fully decentralized, right?

Well, while full decentralization is the long-term goal that KlimaDAO will strive towards, launching a new protocol and immediately decentralizing everything is a recipe for disaster. At launch, complex protocols like ours must be able to react swiftly and decisively to changing market conditions in order to ensure long term success, and as such are vulnerable to poor management, fumbled execution and delayed decision-making.

In mid-2021, a small team of carbon market professionals and blockchain entrepreneurs conceived of the KlimaDAO protocol as a mechanism to create transparent, liquid carbon markets, while making it more expensive to pollute and enabling new methods of carbon capture to become economically viable.&#x20;

When laying the foundations of the protocol, the original Core Team made informed decisions based on their professional experience and expert knowledge of both the Olympus protocol, which inspired KlimaDAO, as well as the legacy carbon markets that we aim to bring on-chain. The shared mental model they developed is encapsulated in the KlimaDAO manifesto, and they shepherded the protocol to launch.&#x20;

As the protocol began to take shape, the Core Team brought in early contributors to advise on policy decisions, help manage the community, and set up the DAO’s structure and organization. At this early stage, KIPs were formulated by the Core Team and posted directly on [Snapshot](https://snapshot.org/#/klimadao.eth) since there was not yet a forum for discussion (only Discord).

By December of 2021, the DAO formally opened up and began accepting outside applications for contribution across all departments. At the time of writing, there are approximately 100 contributors, with more being onboarded regularly. It has expanded the KIP process to further emphasize community input by adding a Request for Comment period on the KlimaDAO [forum](https://forum.klimadao.finance/t/proposals) where everyone can question, criticize, or recommend proposals that are less time-sensitive.

As any new protocol with ambitions of decentralization gets off the ground, the community must take on more responsibility. Gradually the vision of the founding team and the shared mental model of the protocol are internalized by the community, which diminishes the risk of uninformed token votes or a poorly worded proposal throwing the protocol off the rails.

## Initial State

Since the protocol launched, the Core Team has retained access to contracts and wallets behind 3-of-5 Gnosis Safe multisig wallets - meaning at least 3 Core members must agree to approve a transaction out of 5 total signers. With the [adoption of the Klima Foundation](https://forum.klimadao.finance/d/290-kip-53-klima-foundation), these multisigs are now controlled by legally obligated representatives of  Foundation.&#x20;

These multisig wallets are used to execute adjustments to policy variables such as bond capacities and reward rate, as well as to distribute funds from the DAO wallet to pay contributors and fund DAO initiatives.

This initial system requires a great deal of trust in the Core Team to shepherd the protocol to maturity. Thus it is important that we have a transparent governance process to guide the Core Team’s decisions with ample community input, as well as prepare the community to eventually govern more aspects of the protocol as it is gradually decentralized.

## Current Governance Process

KlimaDAO is maturing rapidly. Talent is being onboarded to contribute to, and influence the direction of the protocol's growth. The community is expanding, and bringing a range of perspectives, from DeFi natives and carbon market experts, to people who are getting involved with their first DAO. The markets that KlimaDAO operate in (DeFi, ReFi and the Voluntary Carbon Markets) are also evolving at breakneck speed.

To properly leverage the knowledge at the DAO's disposal, and build out the protocol for long-term success in the interest of all those who have a stake in its growth, KlimaDAO has established a more formal approach to governance decisions which is being used today, discussed below.&#x20;

![Flow of Governance Proposals from Idea to Hard Consensus](../.gitbook/assets/KlimaDAO\_governance\_v2.png)

### Discord Community

[https://discord.com/invite/klimadao](https://discord.com/invite/klimadao)

Discord serves as the primary informal medium for community discussion. There are a wide variety of standing text channels, covering everything from detailed technical discussion in #policy-forum to sharing beautiful #nature-photography or just shooting the breeze in the #klimate-clubhouse.

KlimaDAO’s Discord server is regularly trafficked by Core Team members and DAO contributors, who relay messages from the community to the relevant departments or other Core Team members as necessary. There is even a dedicated channel for feedback and suggestions that is monitored by DAO contributors.&#x20;

#### Hosted Events

KlimaDAO hosts regular office hours, policy chats, and AMA (“Ask Me Anything”) sessions via Twitter spaces and voice chat in Discord.\
\
During office hours (as of this writing, hosted bi-weekly on Thursdays at 9 am Pacific time in #office-hours), the Core Team delivers high-level updates on the DAO’s progress, and anyone is free to ask questions either via voice or in text chat for as long as time allows.&#x20;

### Formal Discussion Forum

[https://forum.klimadao.finance](https://forum.klimadao.finance)

The KlimaDAO Forum is the hub for more formal discussion and debate.  Request for Comment (RFC) periods begin here, where people can make their thoughts heard on the latest Klima Improvement Proposals (KIPs).  An RFC can originate internally, from a community member, or from third parties such as new carbon bridges who wish to integrate into the Klima ecosystem.&#x20;

After the RFC, if the community is on-board with the proposal, a formal KIP will be drafted by the policy team, which will be posted on the forum with an informal poll - acting as a temperature check to suggest if the proposal may need alterations or further discussion.&#x20;

Proposals can also originate directly from the DAO without an RFC, including for:\
\- major reward rate adjustments\
\- frameworks for DAO operations such as contributor compensation\
\- introduction of new bond types not associated with a partnership (for instance, KIP-8 adding KLIMA/USDC LP bonds)

_**Note: only the policy team can post KIP temperature check votes in the “Proposals” section of the forum, but anyone can open a general discussion topic or post an RFC in the “General” section.**_

### Snapshot Voting

[https://snapshot.org/#/klimadao.eth/](https://snapshot.org/#/klimadao.eth/)

After passing the informal poll on the forum, official KIPs will be published on Snapshot by the Core Team for a formal, on-chain vote by KLIMA token holders.&#x20;

At the time of writing, voting power on Snapshot is determined by the amount of KLIMA owned in a one-to-one ratio. All forms of KLIMA (such as staked and wrapped) are eligible to vote, except for leveraged KLIMA (fsKLIMA).

Note that not all actions are subject to a KIP vote. These include smaller-scale maintenance changes, such as Bond Control Variable (BCV) adjustments, as well as established protocol functions that require manual action, such as acting as “buyer of last resort” should KLIMA ever trade below 1 BCT.&#x20;

For comparison, larger and less urgent changes, such as significant reward rate adjustments, or adding new assets to the treasury, will require KIP votes.

In the event that the policy team or Core Team wishes to reserve a new power, such that a KIP vote is not required for a specific action, this change will itself be subject to a vote.

## Future Vision for Decentralized Governance

Decentralization is a spectrum rather than a binary. Few, if any, DAOs begin fully decentralized, and KlimaDAO is no exception. Decentralization is a journey, an ideal that DAOs must strive toward. KlimaDAO has made great progress on this journey, but it is still early days.&#x20;

One potential issue with limiting KIP publication to the Core team and DAO departments is that the voting process can turn into a “rubber stamp” of changes planned centrally. Over time, our goal is to decentralize as many governance functions as possible, to minimize any dictatorial power exerted by the DAO contributors or Core Team and ensure that votes are meaningful.&#x20;

However, not all governance functions are amenable to the same systems - for instance, one-to-one token voting can be gamed via bribes or exploited by whales to benefit themselves at the expense of the protocol. Likewise, opening up publication of KIPs on Snapshot to any holder of KLIMA could turn Snapshot into a sprawling mess of poorly structured proposals.&#x20;

As we work to decentralize more aspects of the protocol, we will research best practices and seek community input on the optimal governance system for each function.&#x20;

A potential solution to responsibly decentralize KIP publication rights is a "stewardship" model, where representatives are elected by token holders to a committee that has publication rights to Snapshot, controlled by a dedicated multisig that requires some level of consensus among the elected representatives before the proposal is published.

One example of a governance function that we already plan to decentralize (eventually) is the reward rate parameter that contributes to setting the staking [AKR](../references/glossary.md#akr). At this time, the Policy team actively manages the reward rate and proposes individual changes via KIPs within a framework laid out in KIP-3. Once the protocol matures and the AKR stabilizes at a more sustainable level, we can turn control over the reward rate over to an on-chain “gauge” that the community votes to change, with changes automatically implemented via a smart contract.

_**Per the passage of KIP-19, a formal Decentralization Working Group (DWG) has been established as of Q2 2022. Made up of representatives from every level of DAO participation, from Protocol Team to community members, this group will deliver a report on best practices and common antipatterns in decentraized governance, as well as a set of specific recommendations for KlimaDAO's decentralization roadmap. After discussion and review by the community, this roadmap would be implemented by future KIPs when and as appropriate.**_

## Further Reading

* [Vitalik's blog post on governance beyond token voting](https://vitalik.ca/general/2021/08/16/voting3.html)
* [a16z blog post on the history and principles of DAO governance](https://future.a16z.com/building-and-running-a-dao-why-governance-matters/)
* [Vitalik's blog post on bulldozer vs. vetocracy](https://vitalik.eth.limo/general/2021/12/19/bullveto.html)
