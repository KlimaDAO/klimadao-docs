# Wrap sKLIMA

## Why would you wrap sKLIMA?

wsKLIMA is an index-adjusted wrapper for sKLIMA. Some people may find this useful for accounting purposes. Unlike an sKLIMA balance, a wsKLIMA balance will not increase over time.

When wsKLIMA is unwrapped, holders receive sKLIMA based on the latest (ever-increasing) index, so the total yield is the same.

## What is the index?

The Index refers to the amount of KLIMA tokens accumulated if a staker had staked 1 KLIMA token from the first rebasing epoch.

The index can be used to track or check an sKLIMA position by marking down the index number at the point that KLIMA is staked, and that sKLIMA is unstaked.

Similarly, the index can be used to define a wsKLIMA position. This is achieved by dividing the index number when wsKLIMA is unwrapped by the index at the time of wrapping.

{% hint style="info" %}
The wsKLIMA smart contract also has handy functions `wKLIMATosKLIMA(uint256 _amount)`  and `sKLIMATowKLIMA(uint256 _amount)` to calculate the conversion of sKLIMA to wsKLIMA and vice versa.
{% endhint %}

## Wrapping sKLIMA via Solidity

#### Requirements <a href="#f52c" id="f52c"></a>

* Get some MATIC to pay for gas fees
* Get some sKLIMA tokens to wrap
* Get the contract addresses from here:
  * [StakingHelper](https://docs.klimadao.finance/references/contracts/staking#stakinghelper)
  * [Staking](https://docs.klimadao.finance/references/contracts/staking#staking)
  * [wsKLIMA](https://docs.klimadao.finance/references/contracts/tokens#wsklima)
  * [sKLIMA](https://docs.klimadao.finance/references/contracts/tokens#sklima)

#### 1. Transfer sKLIMA to your contract

You can transfer sKLIMA tokens to your contract via web3.js and JSON RPC (like using Metamask) or choose to implement a deposit and stake function that calls KLIMA's standard ERC20 approve and transfer functions to allow your contract to transfer users' KLIMA tokens to your contract and stake it.

#### 2. Approving the wsKLIMA contract

Your contract's function calls the sKLIMA token's standard ERC20 approve function to allow the wsKLIMA contract to withdraw sKLIMA tokens from your contract. In the example below, an interface named IERC20 to interact with the sKLIMA token smart contact.

#### 3. Wrapping sKLIMA tokens

Your contract's function calls the wsKLIMA contract's wrap function. In the example below, an interface named IwsKLIMA is used to interact with the wsKLIMA contract.

Once wrapped, you will receive wsKLIMA tokens proportional to the amount of sKLIMA divided by the current index. to represent the staked KLIMA. sKLIMA is an ERC20 and can transferred using the IERC20 interface.

{% code lineNumbers="true" %}
```solidity
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.0;

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

interface IwsKLIMA {
    function wrap(uint256 _amount) external returns (uint256);

    function unwrap(uint256 _amount) external returns (uint256);

    function wKLIMATosKLIMA(uint256 _amount) external view returns (uint256);

    function sKLIMATowKLIMA(uint256 _amount) external view returns (uint256);
}

contract MyContract {
    address public immutable wsKLIMA;
    address public immutable sKLIMA;
    
    function wrap( uint _amount ) public {
        IERC20( sKLIMA ).approve( wsKLIMA , _amount );
        IwsKLIMA( stakingHelper ).wrap( _amount );
    } 
}
```
{% endcode %}

## Unwrapping wsKLIMA via Solidity

#### Requirements <a href="#f52c" id="f52c"></a>

* Get some MATIC to pay for gas fees
* Get some wsKLIMA tokens to unwrap
* Get the contract addresses from here:
  * [Staking](https://docs.klimadao.finance/references/contracts/staking#staking)
  * [KLIMA](https://docs.klimadao.finance/references/contracts/tokens#klima)
  * [sKLIMA](https://docs.klimadao.finance/references/contracts/tokens#sklima)

_The following assumes your contract already holds wsKLIMA. You can follow the same steps above to transfer wsKLIMA to your contract if necessary._

{% hint style="info" %}
_There is no need to approve wsKLIMA to be unwrapped because it is a function of the wsKLIMA contract._
{% endhint %}

#### 1. Unwrapping wsKLIMA tokens

Your contract's function calls the wsKLIMA contract's unwrap function. In the example below, an interface named IwsKLIMA is used to interact with the wsKLIMA contract.

Once unwrapped, you will receive a proportional amount of sKLIMA multiplied by the current index. sKLIMA is an ERC20 and can transferred using the IERC20 interface.

```solidity
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.0;

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

interface IwsKLIMA {
    function wrap(uint256 _amount) external returns (uint256);

    function unwrap(uint256 _amount) external returns (uint256);

    function wKLIMATosKLIMA(uint256 _amount) external view returns (uint256);

    function sKLIMATowKLIMA(uint256 _amount) external view returns (uint256);
}

contract MyContract {
    address public immutable wsKLIMA;
    address public immutable sKLIMA;
    
    function unwrap( uint _amount ) public {
        IwsKLIMA( wsKLIMA ).unwrap( _amount );
    } 
}
```

