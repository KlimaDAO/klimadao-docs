# Staking (🌳,🌳)

Staking is the primary reward distribution mechanism of the protocol. It is intended to be the primary mechanism of value accrual for the majority of users.&#x20;

Whenever the protocol has an excess of reserves per token (i.e when the CC of the treasury is higher than the assets needed to back KLIMA), the protocol will mint and distribute tokens to the stakers. The amount minted and distributed is controlled by a variable named the reward rate. This is the % of supply that is rebased. This massively slows down how fast the protocol expands supply, as doing so is detrimental to the health (rapid expansion without backing causes a price collapse).

KLIMA and sKLIMA always have a 1:1 ratio, meaning that you will always obtain 1 sKLIMA for every 1 KLIMA and vice versa via staking or unstaking on the KlimaDAO Dapp.&#x20;

$$
KLIMA= sKLIMA
$$

When a rebase occurs, the treasury deposits KLIMA into the distributor contract, which deposits it in the staking contract. Since there is now more KLIMA then there is sKLIMA, the sKLIMA is rebased to keep them in parity.&#x20;

$$
Reward Rate=1-KlimaDeposits/sKlimaOutstanding
$$

Because not all KLIMA is staked, the user gains a larger piece of the share of rebases:&#x20;

$$
RewardYield = RewardRate/(\%Staked*\%Circulating)
$$

This translates to [AKR](../references/glossary.md#akr):

$$
(1+RewardYield)^{(365*24/(BlockTimeInHours)}
$$
