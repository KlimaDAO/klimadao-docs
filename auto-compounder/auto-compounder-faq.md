# Auto Compounder FAQ

## Where does the yield come from?

Aerodrome issues AERO rewards to liquidity pool providers who stake their liquidity pool tokens on the Aerodrome Platform. More information can be found at [https://aerodrome.finance/docs#](https://aerodrome.finance/docs).

## What is the advantage of using the Auto Compounder over Aerodrome’s native offering?

On Aerodrome, you have to manually claim your AERO emissions as they accumulate over time. Depending on your goals, this can be sub-optimal since if you want to grow your position by re-staking your earned AERO tokens, you would have to go through this process manually, which can quickly become a tedious task.

KlimaDAO’s Auto Compounder accesses your accumulated AERO rewards, converts them to the tokens of your position, and re-stakes them automatically. Through compound interest, this can improve the overall yield performance of your position.

## How often is the yield compounded?

Currently, your yield is compounded once every 24 hours.

## The app sometimes mentions vault tokens. What are they?

Vault tokens represent your share of the total vault. This number will increase or decrease (depending on the size of your position relative to the total vault) whenever you stake or unstake.

As soon as you stake the liquidity pool tokens in the Auto Compounder, these tokens get exchanged for vault tokens. Once you unstake, your vault tokens are converted back to liquidity pool tokens again, letting you claim your liquidity token pair.

## The amount of vault tokens I staked is not growing. Why?

You might notice that the amount of vault tokens is always constant. This is working as intended; your vault tokens balance will always remain the same (unless you stake or unstake), while the amount of tokens you see under BALANCE will slowly increase over time as the Auto Compounder uses your AERO tokens to grow your position.

## What is my balance?

The balance of your staked position includes your staked liquidity pool tokens plus the total yield accrued over time, expressed as a US Dollar value.

## Are there any fees attached to using the Auto Compounder?

1% of the accrued yield is used to burn existing KLIMA tokens and retire carbon credits owned by KlimaDAO. However, in contrast to manual compounding, all transaction costs for automatic compounding are paid for by KlimaDAO.

## How does the 1% fee to burn KLIMA work?

When you stake using the Auto Compounder, you will see this message on the form:

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdLo0dJZ1nvDXq5IrlakgkTm02O1d6AZJCDa_zRyFPC_8lTOxMeiiU_AE59gt720nsRaAxJ9rVOfl-9P7vFXi0qhoSfnzGYPIXSom2zL_yKc-wVrWKrV1M-z-02TYW0r1VR-pwbmg?key=l05y3lVzz17UAfirUdl0ULVl" alt=""><figcaption></figcaption></figure>

When the yield is compounded every 24 hours, 1% is automatically redirected to a wallet address on [Base](https://basescan.org/tokenholdings?a=0x5933f2448a01Cdf0421f1ce3B66a86977eB99606).

In regular intervals, this yield is used to perform retirements, which are executed on Base and used to retire carbon tokens on Polygon.&#x20;

All of this is performed by KlimaDAO in the background. As a user, you do not need to take any manual action.

## If I unstake from the Auto Compounder, am I still earning AERO rewards?

If you decide to exit the Auto Compounder, unstake, and do nothing else; you are only earning the trading fees from the pool, not AERO rewards. On the [Aerodrome Dashboard](https://aerodrome.finance/dash?), your unstaked position will show as available for Stake. Stake your deposit again on Aerodrome to start earning AERO rewards; just note that these will not auto compound. See [**What is the advantage of using the Auto Compounder over Aerodrome’s native offering?**](https://docs.klimadao.finance/auto-compounder/auto-compounder-faq#what-is-the-advantage-of-using-the-auto-compounder-over-aerodromes-native-offering) for the benefits of using the KlimaDAO Auto Compounder.
