---
description: Processes and tooling used to govern the KlimaDAO protocol
---

# Governance Framework

## Current Governance Process

KlimaDAO and the ecosystem it operates in is maturing rapidly. Talent is being onboarded to contribute to, and influence the direction of the protocol's growth. The community is expanding, and bringing a range of perspectives, from DeFi natives and carbon market experts, to people who are getting involved with their first DAO. The markets that KlimaDAO operate in (DeFi, Digital Carbon Markets (DCM) and the Voluntary Carbon Markets (VCM)) are also evolving at breakneck speed.

To properly leverage the knowledge at the DAO's disposal, and build out the protocol for long-term success in the interest of all those who have a stake in its growth, KlimaDAO has established a more formal approach to governance decisions which is being used today, discussed below.&#x20;

<figure><img src="https://i.imgur.com/6Zh5S3Q.png" alt=""><figcaption><p>Flow of Governance Proposals from Idea to Hard Consensus</p></figcaption></figure>

### Discord Community

[https://discord.com/invite/klimadao](https://discord.com/invite/klimadao)

Discord serves as the primary informal medium for community discussion. There are a wide variety of channels where you can discuss everything from governance proposals to the technicalities of the protocol.

KlimaDAO’s Discord server is regularly trafficked by the KlimaDAO Foundation Directors, Protocol team members and other DAO contributors where you can seek information and share your thoughts directly in conversation.

#### Hosted Events

KlimaDAO hosts regular office hours, policy chats, and AMA (“Ask Me Anything”) sessions via Twitter spaces and voice chat in Discord.\
\
During office hours (check the events section in the Discord), the Protocol team delivers high-level updates on the DAO’s progress, and anyone is free to ask questions either via voice or in text chat for as long as time allows.&#x20;

### Formal Discussion Forum

[https://forum.klimadao.finance](https://forum.klimadao.finance)

The KlimaDAO Forum is the hub for more formal discussion and debate.  Request for Comment (RFC) periods begin here, where people can make their thoughts heard on the latest KlimaDAO Improvement Proposals (KIPs).  An RFC can originate internally, from a community member, or from third parties such as carbon project developers seeking funding or new carbon bridges who wish to integrate into the KlimaDAO ecosystem.&#x20;

After the RFC, if the community is on-board with the proposal, a formal KIP will be drafted by the policy team, which will be posted on the forum with an informal poll - acting as a temperature check to suggest if the proposal may need alterations or further discussion.&#x20;

Proposals can also originate directly from the DAO without an RFC, including for:\
\- major reward rate adjustments\
\- frameworks for DAO operations such as contributor compensation\
\- introduction of new bond types not associated with a partnership (for instance, KIP-8 adding KLIMA/USDC LP bonds)

_**Note: only the policy team can post KIP temperature check votes in the “Proposals” section of the forum, but anyone can open a general discussion topic or post an RFC in the “General” section.**_

#### The Guarantee Committee

The Guarantee Committee is an office held within the Klima Foundation, with the intention of ensuring robustness and integrity around KlimaDAO’s ongoing interactions with the carbon markets. Specifically, the Guarantee Committee is tasked with the thorough examination of RFCs brought forth from the market with regards to KlimaDAO’s carbon financing agreements.

The Guarantee Committee members are therefore expected to have significant knowledge and experience within the climate finance and environmental market domains. This Committee will be positioned to shepherd the DAO’s initiatives within the climate finance space, and mitigate risks associated with these activities, considering factors such as technical, economic and reputational risks, and conflicts of interests that may arise within the market. The Community will have the opportunity to affirm new appointments to the Guarantee Committee, via a KIP.

The Committee's authority is exercised with the sole intention of advancing the DAO's interests, ensuring that its operations are not only efficient but also reflective of its core mission. Members of the Guarantee Committee are appointed for a tenure of three years, with the possibility of reappointment, signifying a long-term commitment to the DAO's vision and stability.

Therefore, the Guarantee Committee will have the ability to make recommendations to the community regarding carbon financing initiatives – however, it will not have the ability to make decisions on behalf of the community (i.e. a KIP will still be required to ratify financing agreements).

It is anticipated that the Guarantee Committee will at times work with the Klimate Review Committee [(defined in KIP-35)](https://snapshot.org/#/klimadao.eth/proposal/0x2cedb818786730e1ecf1a703ccc6ddd1ec3b5d97b3fd05bc178169fe2f094979) to progress or raise concerns around RFCs and KIPs specifically pertaining to climate finance.

### Snapshot Voting

[https://snapshot.org/#/klimadao.eth/](https://snapshot.org/#/klimadao.eth/)

After passing the informal poll on the forum, official KIPs will be published on Snapshot by the Protocol Team for a formal, on-chain vote by KLIMA token holders.&#x20;

Originally, voting power on Snapshot was determined by the amount of KLIMA owned in a one-to-one ratio. All forms of KLIMA (such as staked and wrapped) are eligible to vote, except if it is deposited into another DeFi platform or smart contract.

#### KIP-40: Trial - Progressing KlimaDAO's Governance Framework

KlimaDAO launched a 6-month governance trial of anti-plutocratic voting measures to increase stakeholder influence and engagement as established in [KIP-40](https://snapshot.org/#/klimadao.eth/proposal/0x1e0ddb862433c186478f8ef930c2c4d74f03f9c5ffed99fcf527479c877ff97d). This trial consisted of an integration of [Gitcoin Passports](https://passport.gitcoin.co/) to increase Sybil Resistance of the Protocol, as well as Snapshot’s [Quadratic Voting](https://www.gitcoin.co/blog/quadratic-voting-a-how-to-guide) feature, to explore solutions that can increase the project’s resilience, levels of decentralization and community ownership. For more information, see the [KIP-40 forum discussion](https://forum.klimadao.finance/d/243-rfc-trial-progressing-klimadaos-governance-framework).

**Gitcoin Passports**: Gitcoin Passports serves as an innovative solution to identify unique individuals without violating privacy. It leverages third-party services to offer verified credentials or "stamps", which are collectively utilized to verify an individual's identity, without revealing personal information.

Integrating Gitcoin Passport into our governance system will provide a robust mechanism for [sybil resistant](https://docs.snapshot.org/space-handbook/sybil-resistance-scam-and-spam-prevention) unique user verification, significantly reducing the risk of vote manipulation. It prevents the same individual from casting multiple votes via different wallets, therefore maintaining a true representation of the individual's voting power.

**At this time, Snapshot is configured to utilize quadratic voting and you must have your Gitcoin Passport configured and stamped with at least 2 of 7 accounts before a Snapshot vote is started.** Users may link or "stamp their passport" with the following accounts:

* Coinbase
* Discord
* Facebook
* Github
* Google
* Linkedin
* Twitter

**At this time, you must have 2 of 7 associated accounts linked to cast your vote in a Snapshot vote.**

Note that not all actions are subject to a KIP vote. These include smaller-scale maintenance changes, such as Bond Control Variable (BCV) adjustments, as well as established protocol functions that require manual action, such as acting as “buyer of last resort” should KLIMA ever trade below 1 BCT.&#x20;

For comparison, larger and less urgent changes, such as significant reward rate adjustments, or adding new assets to the treasury, will require KIP votes.

In the event that the policy team or Protocol Team wishes to reserve a new power, such that a KIP vote is not required for a specific action, this change will itself be subject to a vote.

## Promises and Perils of Decentralized Governance <a href="#docs-internal-guid-ae4a6fe9-7fff-7aba-b99a-9e0626c1dac9" id="docs-internal-guid-ae4a6fe9-7fff-7aba-b99a-9e0626c1dac9"></a>

It’s in the name, KlimaDAO is a _DAO_, so it’s fully decentralized, right?

Well, while full decentralization is the long-term goal that KlimaDAO will strive towards, launching a new protocol and immediately decentralizing everything is a recipe for disaster. At launch, complex protocols like ours must be able to react swiftly and decisively to changing market conditions in order to ensure long term success, and as such are vulnerable to poor management, fumbled execution and delayed decision-making.

In mid-2021, a small team of carbon market professionals and blockchain entrepreneurs conceived of the KlimaDAO protocol as a mechanism to create transparent, liquid carbon markets, while making it more expensive to pollute and enabling new methods of carbon capture to become economically viable.&#x20;

When laying the foundations of the protocol, the original Core Team made informed decisions based on their professional experience and expert knowledge of both the Olympus protocol, which inspired KlimaDAO, as well as the legacy carbon markets that we aim to bring on-chain. The shared mental model they developed is encapsulated in the KlimaDAO manifesto, and they shepherded the protocol to launch.&#x20;

As the protocol began to take shape, the Core Team brought in early contributors to advise on policy decisions, help manage the community, and set up the DAO’s structure and organization. At this early stage, KIPs were formulated by the Core Team and posted directly on [Snapshot](https://snapshot.org/#/klimadao.eth) since there was not yet a forum for discussion (only Discord).

By December of 2021, the DAO formally opened up and began accepting outside applications for contribution across all departments. At the time of writing, there are approximately 100 contributors, with more being onboarded regularly. It has expanded the KIP process to further emphasize community input by adding a Request for Comment period on the KlimaDAO [forum](https://forum.klimadao.finance/t/proposals) where everyone can question, criticize, or recommend proposals that are less time-sensitive.

As any new protocol with ambitions of decentralization gets off the ground, the community must take on more responsibility. Gradually the vision of the founding team and the shared mental model of the protocol are internalized by the community, which diminishes the risk of uninformed token votes or a poorly worded proposal throwing the protocol off the rails.

## Initial State

Since the protocol launched, the Core Team has retained access to contracts and wallets behind 3-of-5 Gnosis Safe multisig wallets - meaning at least 3 Core members must agree to approve a transaction out of 5 total signers. With the [adoption of the Klima Foundation](https://forum.klimadao.finance/d/290-kip-53-klima-foundation), these multisigs are now controlled by legally obligated representatives of Klima Foundation.&#x20;

These multisig wallets are used to execute adjustments to policy variables such as bond capacities and reward rate, as well as to distribute funds from the DAO wallet to pay contributors and fund DAO initiatives.

The initial system required a great deal of trust in the Core Team to shepherd the protocol to maturity. Thus, it is important to have a transparent governance process to guide the Core Team’s decisions with ample community input, as well as prepare the community to eventually govern more aspects of the protocol as it is gradually decentralized. Over time, the governance process has continued to mature and promote further decentralization.

_**Per the passage of KIP-19, a formal Decentralization Working Group (DWG) was established as of Q2 2022. Made up of representatives from every level of DAO participation, from Core Team to community members, this group**_ [_**delivered a report on best practices and common antipatterns in decentraized governance**_](https://forum.klimadao.finance/d/206-rfc-decentralization-working-group-interim-report)_**, as well as a set of**_ [_**specific recommendations for KlimaDAO's decentralization roadmap**_](https://docs.google.com/document/d/e/2PACX-1vQCTZgBCOvT2Xc3f53bIagJO1OQr57mDTZHubJAjWxkmo29tUAOjH4BpE86Nq204Uo4YMxBpzZySmxi/pub) _**in March 2023. These recommendations led to many KIPs including**_ [_**KIP-40**_ ](../)_**and**_ [_**KIP-53: Klima Foundation**_](https://forum.klimadao.finance/d/290-kip-53-klima-foundation)_**.**_

## Future Vision for Decentralized Governance

Decentralization is a spectrum rather than a binary. Few, if any, DAOs begin fully decentralized, and KlimaDAO is no exception. Decentralization is a journey, an ideal that DAOs must strive toward. KlimaDAO has made great progress on this journey, but it is still early days.&#x20;

One potential issue with limiting KIP publication to the Protocol team and DAO contributors is that the voting process can turn into a “rubber stamp” of changes planned centrally. Over time, our goal is to decentralize as many governance functions as possible, to minimize any dictatorial power exerted by the DAO contributors or Protocol Team and ensure that votes are meaningful.&#x20;

However, not all governance functions are amenable to the same systems - for instance, one-to-one token voting can be gamed via bribes or exploited by whales to benefit themselves at the expense of the protocol thus the trial established in KIP-40. Likewise, opening up publication of KIPs on Snapshot to any holder of KLIMA could turn Snapshot into a sprawling mess of poorly structured proposals.&#x20;

As we work to decentralize more aspects of the protocol, we will research best practices and seek community input on the optimal governance system for each function.&#x20;

A potential solution to responsibly decentralize KIP publication rights is a "stewardship" model, where representatives are elected by token holders to a committee that has publication rights to Snapshot, controlled by a dedicated multisig that requires some level of consensus among the elected representatives before the proposal is published.

One example of a governance function that we already plan to decentralize (eventually) is the reward rate parameter that contributes to setting the staking [AKR](../references/glossary.md#akr). At this time, the Policy team actively manages the reward rate and proposes individual changes via KIPs within a framework laid out in KIP-3. Once the protocol matures and the AKR stabilizes at a more sustainable level, we can turn control over the reward rate over to an on-chain “gauge” that the community votes to change, with changes automatically implemented via a smart contract.

## Further Reading

* [Vitalik's blog post on governance beyond token voting](https://vitalik.ca/general/2021/08/16/voting3.html)
* [a16z blog post on the history and principles of DAO governance](https://future.a16z.com/building-and-running-a-dao-why-governance-matters/)
* [Vitalik's blog post on bulldozer vs. vetocracy](https://vitalik.eth.limo/general/2021/12/19/bullveto.html)
