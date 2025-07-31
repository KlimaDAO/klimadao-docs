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

<table><thead><tr><th>Field</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>carbonBridge</td><td>LibRetire.CarbonBridge</td><td><p>This enum is used for the source of the carbon retired.</p><pre class="language-solidity"><code class="lang-solidity">0 = TOUCAN
1 = MOSS
2 = C3
</code></pre></td></tr><tr><td>retiringAddress</td><td>Address</td><td>Address calling the retirement. Currently the <code>msg.sender</code> value for the retiring transaction.</td></tr><tr><td>retiringEntityString</td><td>String</td><td>String representation of the retiring entity calling the transaction.</td></tr><tr><td>beneficiaryAddress</td><td>Address</td><td>Address for the beneficiary of the retirement. Any NFT certificates created during the retirement will be sent to this address.</td></tr><tr><td>beneficiaryString</td><td>string</td><td>String representation of the beneficiary.</td></tr><tr><td>retirementMessage</td><td>string</td><td>Specific message related to this retirement.</td></tr><tr><td>carbonPool</td><td>address</td><td>Carbon pool token used to retire. If none, the zero address is used.</td></tr><tr><td>carbonToken</td><td>address</td><td>The token address for the specific carbon project token being retired. If none, the zero address is used.</td></tr><tr><td>retiredAmount</td><td>uint256</td><td>Amount of carbon retired. This uses the token's native decimals.</td></tr></tbody></table>

