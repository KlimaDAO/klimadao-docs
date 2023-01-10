# V2 - Diamond

The second version of the KlimaDAO retirement tooling is an implementation of an [EIP-2535](https://eips.ethereum.org/EIPS/eip-2535) multi-facet proxy that allows for a unified experience against one contract address while utilizing logic from multiple other contracts. In addition, the [Generalized Retirement](generalized-retirement.md) developer experience is made more intuitive as certain parameters were abstracted away.

All facets and internal libraries share a common storage space using the `AppStorage` pattern.

Main diamond contract is deployed to 0x8cE54d9625371fb2a068986d32C85De8E6e995f8 on Polygon.

* View on [Louper](https://louper.dev/diamond/0x8cE54d9625371fb2a068986d32C85De8E6e995f8?network=polygon)
* View on [Polygonscan](https://polygonscan.com/address/0x8ce54d9625371fb2a068986d32c85de8e6e995f8)

There are currently two main types of facets within the Diamond.

* Generalized Retirement
* Bridge Specific Tooling

The General Retirement functions should be sufficient for all retirement calls. However, Bridge Specific Tooling becomes useful for Redeem functions and allows for explicit specification of the `retiringEntityString` , set by default to "KlimaDAO Retirement Aggregator".

All retirement transactions initiated through this contract emit the following event.&#x20;



```solidity
event CarbonRetired(
    LibRetire.CarbonBridge carbonBridge,
    address indexed retiringAddress,
    string retiringEntityString,
    address indexed beneficiaryAddress,
    string beneficiaryString,
    string retirementMessage,
    address indexed carbonPool,
    address carbonToken,
    uint256 retiredAmount
);
```

| Field                | Type                   | Description                                                                                                                                                       |
| -------------------- | ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| carbonBridge         | LibRetire.CarbonBridge | <p>This enum is used for the source of the carbon retired.</p><pre class="language-solidity"><code class="lang-solidity">0 = TOUCAN
1 = MOSS
2 = C3
</code></pre> |
| retiringAddress      | Address                | Address calling the retirement. Currently the `msg.sender` value for the retiring transaction.                                                                    |
| retiringEntityString | String                 | String representation of the retiring entity calling the transaction.                                                                                             |
| beneficiaryAddress   | Address                | Address for the beneficiary of the retirement. Any NFT certificates created during the retirement will be sent to this address.                                   |
| beneficiaryString    | string                 | String representation of the beneficiary.                                                                                                                         |
| retirementMessage    | string                 | Specific message related to this retirement.                                                                                                                      |
| carbonPool           | address                | Carbon pool token used to retire. If none, the zero address is used.                                                                                              |
| carbonToken          | address                | The token address for the specific carbon project token being retired. If none, the zero address is used.                                                         |
| retiredAmount        | uint256                | Amount of carbon retired. This uses the token's native decimals.                                                                                                  |

