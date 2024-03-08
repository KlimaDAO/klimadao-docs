# History

## Launch and early history

### Initial Supply

**The initial goal was not to find a stable carbon price.** It is to provide an intuitive way for Web3 users to engage with the carbon markets, vote on governance proposals that shape the Digital Carbon Market, and be rewarded for participation in the protocol. Through policy and voting, the protocol was continually tuned to track developing trends in carbon markets over time.&#x20;

In the early days, the main tradeoff was volatility versus stability and consistency. With volatility comes growth; this is what drove the protocol early on. Towards the middle of the century, the original core team anticipated more stability as KLIMA approaches equilibrium with supply and demand in the carbon markets.&#x20;

At protocol launch, the initial supply was \~251k KLIMA.&#x20;

* \~57k came from the IDO
* 133k came from the LBP
* \~81k came from the alchemist reward program. &#x20;

### Post-Launch Excess pKLIMA Redemption

Until the launch of the wsKLIMA token several weeks after launch, there was a minor implementation issue in the pKLIMA contract that allowed for pKLIMA holders to redeem pKLIMA even though they had a greater % supply share than should be allowed. The original contract could not account for the fact that pKLIMA holders may have staked and earned rebase rewards on previously claimed tokens until the wsKLIMA contract was deployed, providing a way to calculate the index-adjusted value of KLIMA.&#x20;

The fix was deployed on November 24, 2021 and will gradually automatically correct the issue by preventing further pKLIMA redemption until supply grows sufficiently to bring all pKLIMA allocations in line with vesting limits.&#x20;

![](https://lh5.googleusercontent.com/ZyuXKRQB9JwJR8VWhgQBV-vpOUdIPkRWWcvQkh52phnEjcIlFRPhIpb9v6ykQakgLGeQ5Z16a\_l33DZ3dJRnacbxJlvAzbsEMV0G2Ev3MtbtA-l3FlKwtuVsqi7x5dUx9YM1vTTf)
