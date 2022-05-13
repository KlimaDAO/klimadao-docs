# Developers

Source code for all retirement based contracts can be found here: [https://github.com/KlimaDAO/klimadao-solidity/tree/main/contracts/retirement](https://github.com/KlimaDAO/klimadao-solidity/tree/main/contracts/retirement)

## KlimaRetirementAggregator

### State Variables

Addresses common across the product are stored in the master contract:

* [KLIMA](../tokens.md#klima)
* [sKLIMA](../tokens.md#sklima)
* [wsKLIMA](../tokens.md#wsklima)
* [USDC](https://polygonscan.com/token/0x2791bca1f2de4661ed88a30c99a7a9449aa84174)
* [Staking](../staking.md)
* [Staking Helper](../staking.md#stakinghelper)
* [Treasury](../treasury.md)
* [Klima Retirement Storage](./#retirement-storage)

Mappings used to flag and track different tokens and addresses:

* isPoolToken: address => bool returning whether a pool token address has been added to the master contract.
* poolBridge: address => uint returning which index number related to the bridge that a pool uses.
* bridgeHelper: uint => address returning the address of the specific helper contract for the given bridge index.

### Events

AddressUpdated(uint, address, address)

* **uint** addressIndex (found in `setAddress`)
* **address** oldAddress
* **address** newAddress

PoolAdded(address,uint)

* **address** poolToken
* **uint** bridge

PoolRemoved(address)

* **address** poolToken

BridgeHelperUpdated(uint, address)

* **uint** bridgeID
* **address** helper

### Functions

Common parameters for `retireCarbon` functions:

| Name                  | Type    | Description                                                                                                                                                                |
| --------------------- | ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `_sourceToken`        | address | The contract address of the source token being used to retire.                                                                                                             |
| `_poolToken`          | address | The contract address of the pool token being used to retire.                                                                                                               |
| `_amount`             | uint256 | Either the amount of pool tokens to retire or the amount of source tokens to use. See `_amountInCarbon`. Expected values are in the number of decimals for the used token. |
| `_amountInCarbon`     | bool    | This flags whether the amount being passed is in carbon to retire (`true`) or total source tokens to spend (`false`).                                                      |
| `_beneficiaryAddress` | address | The address of the account receiving the benefit of retirement.                                                                                                            |
| `_beneficiaryString`  | string  | A string representation of the beneficiary. Useful for specifying a company or protocol name in a readable format.                                                         |
| `_retirementMessage`  | string  | Represents a specific message related to this retirement transaction. Example being "Retirement for 2022 Q1 travel."                                                       |

### retireCarbon

Transfers and uses tokens from caller's wallet to swap to the pool if needed and then retire the pool tokens.

```solidity
function retireCarbon(
        address _sourceToken,
        address _poolToken,
        uint256 _amount,
        bool _amountInCarbon,
        address _beneficiaryAddress,
        string memory _beneficiaryString,
        string memory _retirementMessage
    ) publicid
```

### retireCarbonFrom

Same function as `retireCarbon`, but does not initiate the transfer of the source tokens to the aggregator. Source tokens must be transferred prior to calling `retireCarbonFrom`.&#x20;

* Additional parameter:&#x20;
  * address `_initiator`: Address where any trade dust should be returned.

```solidity
function retireCarbonFrom(
        address _initiator,
        address _sourceToken,
        address _poolToken,
        uint256 _amount,
        bool _amountInCarbon,
        address _beneficiaryAddress,
        string memory _beneficiaryString,
        string memory _retirementMessage
    ) public
```

### retireCarbonSpecific

Allows a user to specify the underlying offset they choose to retire. This action is subject to any fees imposed by a bridge for the selective redemption of a pool token.

* Additional parameter:
  * address\[] `_carbonList`: Array of addresses used to redeem pool tokens in order.

```solidity
function retireCarbonSpecific(
        address _sourceToken,
        address _poolToken,
        uint256 _amount,
        bool _amountInCarbon,
        address _beneficiaryAddress,
        string memory _beneficiaryString,
        string memory _retirementMessage,
        address[] memory _carbonList
    ) public
```

### retireCarbonSpecificFrom

Similar to `retireCarbonFrom`, this operates the same way and allows a caller to transfer the needed source tokens to the aggregator prior to calling for specific retirement.

* Additional parameters:
  * address\[] `_carbonList`: Array of addresses used to redeem pool tokens in order.
  * address `_initiator`: Address where any trade dust should be returned.

```solidity
function retireCarbonSpecificFrom(
        address _initiator,
        address _sourceToken,
        address _poolToken,
        uint256 _amount,
        bool _amountInCarbon,
        address _beneficiaryAddress,
        string memory _beneficiaryString,
        string memory _retirementMessage,
        address[] memory _carbonList
    ) public
```

### getSourceAmount

This function calls the specific bridge helper for the supplied pool token and returns both the source and carbon amounts. Parameters are the same as if you were going to use a `retireCarbon` function call.

```solidity
function getSourceAmount(
        address _sourceToken,
        address _poolToken,
        uint256 _amount,
        bool _amountInCarbon
    ) public view returns (uint256, uint256)i
```

Return Values:

* uint256 `sourceAmount`: The total amount of source tokens needed.
* uint256 `carbonAmount`: The total amount of carbon tokens needed or used.

### getSourceAmountSpecific

This function does the same thing as `getSourceAmount`, but also factors in any pool redemption fees incurred by performing a selective retirement.

```solidity
function getSourceAmountSpecific(
        address _sourceToken,
        address _poolToken,
        uint256 _amount,
        bool _amountInCarbon
    ) public view returns (uint256, uint256)
```

Return Values:

* uint256 `sourceAmount`: The total amount of source tokens needed.
* uint256 `carbonAmount`: The total amount of carbon tokens needed or used.
