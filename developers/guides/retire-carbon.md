# Retire Carbon

For an in-depth review of the retirement aggregator smart contract, check out [this page](https://docs.klimadao.finance/developers/guides/retirement-aggregator-contract-guide).

## Retiring Carbon via Solidity

### Requirements <a href="#f52c" id="f52c"></a>

* Get some MATIC to pay for gas fees
* Get some KLIMA tokens to spend to retire carbon
* Get the contract addresses from here:
  * [Retirement Aggregator](https://docs.klimadao.finance/developers/contracts/retirement#aggregator)
  * [KLIMA](https://docs.klimadao.finance/references/contracts/tokens#klima)
  * Address of carbon token to be retired

#### 1. Transfer your source token to your contract

You can transfer KLIMA tokens to your contract via web3.js and JSON RPC (like using Metamask) or choose to implement a deposit function that calls KLIMA's standard ERC20 approve and transfer functions to allow your contract to transfer users' KLIMA tokens to your contract.

#### 2. Approving the Aggregator contract

Your contract's function calls the KLIMA token's standard ERC20 approve function to allow the Aggregator contract to withdraw KLIMA tokens from your contract. In the example below, an interface named IERC20 to interact with the KLIMA token smart contact.

#### 3. Retiring carbon with the Aggregator contract

Your contract's function calls the Aggregator contract's `retireCarbon` function. In the example below, an interface named IKlimaRetirementAggregator is used to interact with the Aggregator contract.

To fully understand the parameters for the Aggregator contract's functions, we recommend reviewing [this page](https://docs.klimadao.finance/developers/guides/retirement-aggregator-contract-guide).

### Example 1

Use KLIMA to retire BCT with one beneficiary address, name, and retirement message

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

interface IKlimaRetirementAggregator {
    function retireCarbon(address _sourceToken,address _poolToken,uint256 _amount,bool _amountInCarbon,address _beneficiaryAddress,string memory _beneficiaryString,string memory _retirementMessage) external;
    function isPoolToken(address poolToken) external view returns ( bool );
}

contract MyContract {
    address public immutable KlimaRetirementAggregator;
    
    address public immutable KLIMA;
    address public immutable BCT;
    
    address public beneficiaryAddress;
    string public beneficiaryName;
    string public retirementMessage;
    
    
    /**
     * @notice This function will attempt to swap KLIMA to the selected carbon token and then retire.
     *
     * @param _amount The total amount of KLIMA you want to use to retire.
     */
    function retire( uint _amount ) public {
        IERC20(KLIMA).approve( KlimaRetirementAggregator, _amount );
        IKlimaRetirementAggregator( KlimaRetirementAggregator ).retireCarbon( KLIMA, BCT, _amount, false, beneficiaryAddress, beneficiaryName, retirementMessage );
    } 
}
```
{% endcode %}

### Example 2

Use USDC to retire a specific amount of your choice of carbon token (BCT, NCT, UBO, NBO, MCO2) allowing the caller to set the beneficiary information

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

interface IKlimaRetirementAggregator {
    function retireCarbon( address _sourceToken, address _poolToken, uint256 _amount, bool _amountInCarbon, address _beneficiaryAddress, string memory _beneficiaryString, string memory _retirementMessage) external;
    function isPoolToken( address poolToken) external view returns ( bool );
    function getSourceAmount( address _sourceToken, address _poolToken, uint256 _amount, bool _amountInCarbon ) external view returns ( uint256, uint256 );
}

contract MyContract {
    address public immutable KlimaRetirementAggregator;
    
    address public immutable USDC;
    
     /**
     * @notice This function will attempt to swap USDC to specified number of the selected carbon token and then retire.
     *
     * @param _amount The total amount of tons you want to retire.
     * @param _poolToken The contract address of the carbon token being retired.
     * @param _beneficiaryAddress Address of the beneficiary of the retirement.
     * @param _beneficiaryString String representing the beneficiary. A name perhaps.
     * @param _retirementMessage Specific message relating to this retirement event.
     */
    function swapAndRetire( uint _amount, address _poolToken, address _beneficiaryAddress, string memory _beneficiaryString, string memory _retirementMessage ) public {
        (uint approvalAmount, ) = IKlimaRetirementAggregator( KlimaRetirementAggregator ).getSourceAmount( USDC, _poolToken, _amount, true );
        IERC20(USDC).approve( KlimaRetirementAggregator, approvalAmount );
        IKlimaRetirementAggregator( KlimaRetirementAggregator ).retireCarbon( USDC, _poolToken, _amount, true, beneficiaryAddress, beneficiaryName, retirementMessage );
    } 
}}
```



