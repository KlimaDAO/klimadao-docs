# Bond Carbon or LP tokens

## Bonding via Solidity

### Requirements <a href="#f52c" id="f52c"></a>

* Get some MATIC to pay for gas fees
* Get some carbon or LP tokens to bond
* Get the contract addresses from here:
  * [Bond depository address](https://docs.klimadao.finance/developers/contracts/bonds) for desired bond
  * Address of token to be bonded

#### 1. Transfer bondable token to your contract

You can transfer ERC20 tokens (like LP tokens) to your contract via web3.js and JSON RPC (like using Metamask) or choose to implement a function that calls ERC20 token's standard approve and transfer functions to allow your contract to transfer users' tokens to your contract.

#### 2. Approving the bond depository

Your contract's function calls the bondable token's standard ERC20 approve function to allow the bond depository contract to transfer tokens from your contract. In the example below, an interface named IERC20 to interact with the BCT token smart contact.

{% hint style="info" %}
Require can be used to ensure that a bond has a sufficient discount otherwise the transaction reverts. Provided below is an example of how to implement a `require` conditional and `getDiscount` function.
{% endhint %}

#### 3. Bonding your tokens

First, get the current price of the bond from the bond depository. In the example below, an interface named `IKlimaBondDepository` is used to read the bond depository contract's `bondPriceInUSD`. (This bond price is actually denominated in BCT instead of USD as KLIMA is fork of OlympusDAO denominated in carbon.)

Then, your contract's function calls the bond depository contract's `deposit` function with the token balance to bond, the bond price we fetched, and the recipient of the bond.

### Example&#x20;

{% code lineNumbers="true" %}
```solidity
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.9;

interface IERC20 {
    function decimals() external view returns (uint8);
    /**
     * @dev Returns the amount of tokens in existence.
     */
    function totalSupply() external view returns (uint256);

    /**
     * @dev Returns the amount of tokens owned by `account`.
     */
    function balanceOf(address account) external view returns (uint256);

    /**
     * @dev Moves `amount` tokens from the caller's account to `recipient`.
     *
     * Returns a boolean value indicating whether the operation succeeded.
     *
     * Emits a {Transfer} event.
     */
    function transfer(address recipient, uint256 amount) external returns (bool);

    /**
     * @dev Returns the remaining number of tokens that `spender` will be
     * allowed to spend on behalf of `owner` through {transferFrom}. This is
     * zero by default.
     *
     * This value changes when {approve} or {transferFrom} are called.
     */
    function allowance(address owner, address spender) external view returns (uint256);

    /**
     * @dev Sets `amount` as the allowance of `spender` over the caller's tokens.
     *
     * Returns a boolean value indicating whether the operation succeeded.
     *
     * IMPORTANT: Beware that changing an allowance with this method brings the risk
     * that someone may use both the old and the new allowance by unfortunate
     * transaction ordering. One possible solution to mitigate this race
     * condition is to first reduce the spender's allowance to 0 and set the
     * desired value afterwards:
     * https://github.com/ethereum/EIPs/issues/20#issuecomment-263524729
     *
     * Emits an {Approval} event.
     */
    function approve(address spender, uint256 amount) external returns (bool);

    /**
     * @dev Moves `amount` tokens from `sender` to `recipient` using the
     * allowance mechanism. `amount` is then deducted from the caller's
     * allowance.
     *
     * Returns a boolean value indicating whether the operation succeeded.
     *
     * Emits a {Transfer} event.
     */
    function transferFrom(address sender, address recipient, uint256 amount) external returns (bool);

    /**
     * @dev Emitted when `value` tokens are moved from one account (`from`) to
     * another (`to`).
     *
     * Note that `value` may be zero.
     */
    event Transfer(address indexed from, address indexed to, uint256 value);

    /**
     * @dev Emitted when the allowance of a `spender` for an `owner` is set by
     * a call to {approve}. `value` is the new allowance.
     */
    event Approval(address indexed owner, address indexed spender, uint256 value);
}

interface IKlimaBondDepository {
    function bondPriceInUSD() external view returns (uint256 price_);

    function deposit(
        uint256 _amount,
        uint256 _maxPrice,
        address _depositor
    ) external returns (uint256);

    function pendingPayoutFor(address _depositor)
        external
        view
        returns (uint256 pendingPayout_);
}


contract MyContract {
    address public immutable BCT;
    address public immutable bondDepository;
    
    function bondBCT(uint _amount) public {
        IERC20(BCT).approve(bondDepository, _amount);
        uint256 bondPrice = IKlimaBondDepository(bondDepository).bondPriceInUSD();
        IKlimaBondDepository(bondDepository).deposit(_amount, bondPrice, msg.sender);
    }
    
}

```
{% endcode %}
