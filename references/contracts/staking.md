# Staking

## **Staking**

The Staking contract accepts KLIMA for staking and returns sKLIMA, and accepts sKLIMA for unstaking, returning KLIMA. It also manages the warmup period to ensure stakers only receive rewards after their warmup period has expired (if the warmup period is longer than 0 epochs).&#x20;

* V1: [0x25d28a24Ceb6F81015bB0b2007D795ACAc411b4d](https://polygonscan.com/address/0x25d28a24Ceb6F81015bB0b2007D795ACAc411b4d)

## StakingHelper

Utility contract that wraps functionality form the Staking contract for ease-of-use.

* V1: [0x4D70a031Fc76DA6a9bC0C922101A05FA95c3A227](https://polygonscan.com/address/0x4D70a031Fc76DA6a9bC0C922101A05FA95c3A227#code)

## Distributor

The distributor contract receives minted KLIMA from the treasury in order to drip-feed rewards to stakers. Note that the reward rate determines the rebase rate and that the rebase rate determines the [AKR](../glossary.md#akr). Below are listed distributor contracts by version, where the latest version represents the currently active contract.

* V1:  [0x4cC7584C3f8FAABf734374ef129dF17c3517e9cB](https://polygonscan.com/address/0x4cC7584C3f8FAABf734374ef129dF17c3517e9cB)
