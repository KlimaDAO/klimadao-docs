# Generalized Retirement

## Common Retirement Parameters

While there are multiple functions available to call based on a user's needs, the base information needed to carry out these transactions is similar among them. The common parameters used by both the exact carbon and exact source functions are as follows:

| Field                  | Type               | Description                                                                                                                                                                                 |
| ---------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `sourceToken`          | `address`          | Source token to use for the retirement. If non-carbon pool, will be swapped to the designated carbon pool.                                                                                  |
| `poolToken`            | `address`          | Carbon pool token to use for the retirement.                                                                                                                                                |
| `projectToken`         | `address`          | The token address for the specific carbon project token being redeemed and retired, if applicable.                                                                                          |
| `maxAmountIn`          | `uint256`          | Maximum amount of the source token to spend. To find the exact amount needed, please refer to the view functions `getSourceAmountSpecificRetirement` and `getSourceAmountDefaultRetirement` |
| `retiringEntityString` | `string`           | String representation of the retiring entity calling the transaction.                                                                                                                       |
| `beneficiaryAddress`   | `address`          | Address for the beneficiary of the retirement. Any NFT certificates created during the retirement will be sent to this address.                                                             |
| `beneficiaryString`    | `string`           | String representation of the beneficiary.                                                                                                                                                   |
| `retirementMessage`    | `string`           | Specific message related to this transaction.                                                                                                                                               |
| `fromMode`             | `LibTransfer.From` | Currently only `EXTERNAL` transactions are supported with this version. The value provided should be 0.                                                                                     |

All retirement functions return the latest retirement index for the transaction just completed.

## Retire Exact Carbon

Additional parameter definitions:

| Field          | Type      | Description                                                                                                       |
| -------------- | --------- | ----------------------------------------------------------------------------------------------------------------- |
| `retireAmount` | `uint256` | The amount of carbon to retire. This uses the same number of decimals as the underlying carbon tokens being used. |

```solidity
function retireExactCarbonDefault(
        address sourceToken,
        address poolToken,
        uint256 maxAmountIn,
        uint256 retireAmount,
        string memory retiringEntityString,
        address beneficiaryAddress,
        string memory beneficiaryString,
        string memory retirementMessage,
        LibTransfer.From fromMode
    ) external payable nonReentrant returns (uint256 retirementIndex) 
```

```solidity
function retireExactCarbonSpecific(
        address sourceToken,
        address poolToken,
        address projectToken,
        uint256 maxAmountIn,
        uint256 retireAmount,
        string memory retiringEntityString,
        address beneficiaryAddress,
        string memory beneficiaryString,
        string memory retirementMessage,
        LibTransfer.From fromMode
    ) external payable nonReentrant returns (uint256 retirementIndex)
```

## Retire Exact Source

There are no additional parameters for these functions. They simply transfer in the amount of the source token, and then use all of it to swap (if needed) and retire the specified carbon.

```solidity
function retireExactSourceDefault(
        address sourceToken,
        address poolToken,
        uint256 maxAmountIn,
        string memory retiringEntityString,
        address beneficiaryAddress,
        string memory beneficiaryString,
        string memory retirementMessage,
        LibTransfer.From fromMode
    ) external payable nonReentrant returns (uint256 retirementIndex)
```

```solidity
function retireExactSourceSpecific(
        address sourceToken,
        address poolToken,
        address projectToken,
        uint256 maxAmountIn,
        string memory retiringEntityString,
        address beneficiaryAddress,
        string memory beneficiaryString,
        string memory retirementMessage,
        LibTransfer.From fromMode
    ) external payable nonReentrant returns (uint256 retirementIndex)
```

## View Functions

```solidity
function getTotalRetirements(address account) external view returns (uint256 totalRetirements) 

function getTotalCarbonRetired(address account) external view returns (uint256 totalCarbonRetired)

function getTotalPoolRetired(address account, address poolToken) external view returns (uint256 totalPoolRetired) 

function getTotalProjectRetired(address account, address projectToken) external view returns (uint256 totalRetired) 

function getTotalRewardsClaimed(address account) external view returns (uint256 totalClaimed)

function getRetirementDetails(address account, uint256 retirementIndex)
    external
    view
    returns (
        address poolTokenAddress,
        address projectTokenAddress,
        address beneficiaryAddress,
        string memory beneficiary,
        string memory retirementMessage,
        uint256 amount
    )
    
function getSourceAmountSpecificRetirement(
        address sourceToken,
        address carbonToken,
        uint256 retireAmount
    ) external view returns (uint256 amountIn)
    
function getSourceAmountDefaultRetirement(
        address sourceToken,
        address carbonToken,
        uint256 retireAmount
    ) public view returns (uint256 amountIn)
    
function getSourceAmountDefaultRedeem(
        address sourceToken,
        address carbonToken, // Pool token being redeemed
        uint256 redeemAmount
    ) public view returns (uint256 amountIn)

function getSourceAmountSpecificRedeem(
        address sourceToken,
        address carbonToken, // Pool token being redeemed
        uint256[] memory redeemAmounts
    ) public view returns (uint256 amountIn)
```
