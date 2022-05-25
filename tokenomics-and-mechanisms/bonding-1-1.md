# Bonding (1,1)

### **What is Bonding?**

Bonding is the process of trading assets to the protocol for KLIMA. The protocol will quote you an amount of KLIMA for your asset, and the vesting period for the trade. Today, the protocol takes in:&#x20;

1. Reserve Assets:&#x20;
   * BCT (Base Carbon Tonne; trades on SushiSwap)
   * MCO2 (Moss Carbon Credit Token; trades on Quickswap)
2. Liquidity Assets:&#x20;
   * KLIMA/BCT SushiSwap LP tokens
   * KLIMA/USDC SushiSwap LP tokens
   * KLIMA/MCO2 Quickswap LP tokens

### **Why should I bond?**

Bonding allows you to buy KLIMA at a lower cost basis. Because the protocol can sell at a discount to the market price (as it can mint KLIMA at IV), bonding when there is a positive discount may be advantageous compared to simply buying KLIMA on the market and staking.

### Bonding Dynamics:&#x20;

The protocol quotes the price of a bond based on the intrinsic value of KLIMA, and the premium charged on bonds:&#x20;

$$
Bond Price=1 + Premium
$$

This premium is dependent on 2 factors, the total debt of the system, and a external controllable variable. This ties the price of the bond to the amount of bonds outstanding. The more bonds there are (more demand), the higher the premium and the lower the discount is and vice versa.

$$
Premium = Debt Ratio  * BCV
$$

$$
Debt Ratio = Bonds Outstanding/ KLIMA supply
$$

### Carbon Custodied:&#x20;

Carbon Custodied (CC) refers to the tokenized carbon offsets held in the treasury reserves. For each KLIMA token minted, there is some amount of carbon offsets in the treasury. Any excess reserves above the 1 tonne/KLIMA Intrinsic Value will eventually be paid out to stakers via rebase rewards.

Because an LP share can fluctuate in value in terms of offset tonnage as offsets are bought and sold out of the pool, we mark it down to reflect the fact that not all the carbon will be left in the pool in extreme market conditions This is formularized below:&#x20;

$$
CC_l= (LP/Total LP)*2sqrt(K)
$$

Where K is the constant product of the LP pool.&#x20;

Naked carbon assets that represent one tonne of carbon per 1 token (BCT, MCO2, etc) contribute a carbon custodied value of 1 tonne per token, though the KLIMA token itself ends up backed by a weighted average of the price and quantity of the different carbon assets, which constitute Carbon Custodied.

### Expectations:&#x20;

With the bonding mechanism, not only will we acquire carbon assets into the treasury, it also allows us to acquire liquidity to facilitate market operations as well. This assists in creating a decentralized carbon market, as well as provide passive inflows to the treasury through trading fees which accrue to the LP tokens.
