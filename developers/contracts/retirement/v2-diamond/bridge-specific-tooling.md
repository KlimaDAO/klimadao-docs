# Bridge-Specific Tooling

Some of the following functions allow for direct retirement of bridge-specific project tokens. Others are simply wrappers for common functions found within their protocols such as redeeming tokens from a pool. Note that the Moss bridge is absemt because it does not currently support specific retirement or redemption.

### Toucan

```solidity
function toucanRetireExactTCO2WithEntity(
        address carbonToken,
        uint256 amount,
        string memory retiringEntityString,
        address beneficiaryAddress,
        string memory beneficiaryString,
        string memory retirementMessage,
        LibTransfer.From fromMode
    ) external nonReentrant returns (uint256 retirementIndex)
```

```solidity
function toucanRedeemPoolDefault(
        address poolToken,
        uint256 amount,
        LibTransfer.From fromMode,
        LibTransfer.To toMode
    ) external nonReentrant returns (address[] memory projectTokens, uint256[] memory amounts) 
```

```solidity
function toucanRedeemPoolSpecific(
        address poolToken,
        address[] memory projectTokens,
        uint256[] memory amounts,
        LibTransfer.From fromMode,
        LibTransfer.To toMode
    ) external nonReentrant returns (uint256[] memory redeemedAmounts)
```

### C3

```solidity
function c3RetireExactC3TWithEntity(
        address carbonToken,
        uint256 amount,
        string memory retiringEntityString,
        address beneficiaryAddress,
        string memory beneficiaryString,
        string memory retirementMessage,
        LibTransfer.From fromMode
    ) external nonReentrant returns (uint256 retirementIndex)
```

```solidity
function c3RedeemPoolDefault(
        address poolToken,
        uint256 amount,
        LibTransfer.From fromMode,
        LibTransfer.To toMode
    ) external nonReentrant returns (address[] memory projectTokens, uint256[] memory amounts)
```

```solidity
function c3RedeemPoolSpecific(
        address poolToken,
        address[] memory projectTokens,
        uint256[] memory amounts,
        LibTransfer.From fromMode,
        LibTransfer.To toMode
    ) external nonReentrant returns (uint256[] memory redeemedAmounts)
```
