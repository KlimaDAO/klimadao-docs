# Stake KLIMA

## Staking KLIMA via Solidity

### Requirements <a href="#f52c" id="f52c"></a>

* Get some MATIC to pay for gas fees
* Get some KLIMA tokens to stake
* Get the contract addresses from here:
  * [StakingHelper](https://docs.klimadao.finance/references/contracts/staking#stakinghelper)
  * [Staking](https://docs.klimadao.finance/references/contracts/staking#staking)
  * [KLIMA](https://docs.klimadao.finance/references/contracts/tokens#klima)
  * [sKLIMA](https://docs.klimadao.finance/references/contracts/tokens#sklima)

#### 1. Transfer KLIMA to your contract

You can transfer KLIMA tokens to your contract via web3.js and JSON RPC (like using Metamask) or choose to implement a deposit function that calls KLIMA's standard ERC20 approve and transfer functions to allow your contract to transfer users' KLIMA tokens to your contract.

#### 2. Approving the StakingHelper contract

Your contract's function calls the KLIMA token's standard ERC20 approve function to allow the StakingHelper contract to withdraw KLIMA tokens from your contract. In the example below, an interface named IERC20 to interact with the KLIMA token smart contact.

#### 3. Staking KLIMA tokens

Your contract's function calls the StakingHelper contract's stake function. In the example below, an interface named IStakingHelper is used to interact with the StakingHelper contract.

Once staked, you will receive a proportional amount of sKLIMA to represent the staked KLIMA. sKLIMA is an ERC20 and can transferred using the IERC20 interface.

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

interface IStakingHelper {
    function stake(uint256 _amount) external;
}

contract MyContract {
    address public immutable stakingHelper;
    address public immutable KLIMA;
    
    function stake( uint _amount ) public {
        IERC20( KLIMA ).approve( stakingHelper, _amount );
        IStakingHelper( stakingHelper ).stake( _amount );
    } 
}
```
{% endcode %}

## Unstaking KLIMA via Solidity

### Requirements <a href="#f52c" id="f52c"></a>

* Get some MATIC to pay for gas fees
* Get some sKLIMA tokens to unstake
* Get the contract addresses from here:
  * [Staking](https://docs.klimadao.finance/references/contracts/staking#staking)
  * [KLIMA](https://docs.klimadao.finance/references/contracts/tokens#klima)
  * [sKLIMA](https://docs.klimadao.finance/references/contracts/tokens#sklima)

_The following assumes your contract already holds sKLIMA. You can follow the same steps above to transfer sKLIMA to your contract if necessary._

#### 1. Approving the Staking contract

Your contract's function calls the sKLIMA token's standard ERC20 approve function to allow the Staking contract to withdraw sKLIMA tokens from your contract. In the example below, an interface named IERC20 to interact with the sKLIMA token smart contact.

#### 2. Unstaking sKLIMA tokens

Your contract's function calls the Staking contract's unstake function. In the example below, an interface named IStaking is used to interact with the Staking contract. The default value for `bool _trigger` is false unless you wish to trigger the rebase.&#x20;

Once unstaked, you will receive a proportional amount of KLIMA. KLIMA is an ERC20 and can transferred using the IERC20 interface.

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

interface IStaking {
    function unstake(uint256 _amount, bool _trigger) external;
}

contract MyContract {
    address public immutable staking;
    address public immutable sKLIMA;
    
    function unstake( uint _amount ) public {
        IERC20( sKLIMA ).approve( staking, _amount );
        IStaking( staking ).unstake( _amount, false );
    } 
}
```

