---
description: >-
  Documentation for automated smart contract function calls and other key pieces
  of automation maintained by KlimaDAO
---

# Automation

## Automated BCT Fee Burn

After taking ownership of the BCT pool via [KIP-57](https://forum.klimadao.finance/d/308-kip-57-bct-transition), KlimaDAO implemented an automated mechanism for burning accumulated selective redemption fees from the BCT pool using Gelato:

* [https://app.gelato.network/functions/task/0x2fdd3f4b9690948246a91c383bce45b50b0cd6637f0b5d420905f82d43dfe3c9:137](https://app.gelato.network/functions/task/0x2fdd3f4b9690948246a91c383bce45b50b0cd6637f0b5d420905f82d43dfe3c9:137)

## Sushi Green Fee Periodic Retirement

To power the [Sushi Green Fee](integration-examples.md#sushiswap-green-fee) functionality, a Chainlink Keeper periodically trigger a carbon credit retirement using accumulated fees.
