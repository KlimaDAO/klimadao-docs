---
description: Contracts for consuming on-chain carbon credits
---

# Retirement

## Aggregator

Unified interface for consuming tokenized carbon credits. Allows the user to provide a variety of input tokens (e.g. USDC, KLIMA, sKLIMA, wsKLIMA) and retire from a selection of different carbon credit pools (e.g. BCT, MCO2).

* V1: [0xEde3bd57a04960E6469B70B4863cE1c9d9363Cb8](https://polygonscan.com/address/0xEde3bd57a04960E6469B70B4863cE1c9d9363Cb8)
* V2: [0x8cE54d9625371fb2a068986d32C85De8E6e995f8](https://louper.dev/diamond/0x8cE54d9625371fb2a068986d32C85De8E6e995f8?network=polygon)&#x20;
  * More details can be found [here](v2-diamond/).

## Bridge-Specific Retirements

Helper contracts for consuming credits from a specific carbon bridge or on-chain issuer.

### C3

* V1: [0x933AF8c652c696FB0969Eb85DDd111edb2b4E057](https://polygonscan.com/address/0x933AF8c652c696FB0969Eb85DDd111edb2b4E057)

### Moss

* V1: [0xa35f62dbdb93e4B772784E89B7B35736A4aeaCc5](https://polygonscan.com/address/0xa35f62dbdb93e4B772784E89B7B35736A4aeaCc5)

### Toucan

* V1: [0xCefb61aF5325C0c100cBd77eb4c9F51d17B189Ca](https://polygonscan.com/address/0xCefb61aF5325C0c100cBd77eb4c9F51d17B189Ca)

## Retirement Storage

Simple storage contract for recording how much a given address has retired, as well as tracking reward points for using the KlimaDAO retirement aggregator.

* V1: [0xac298CD34559B9AcfaedeA8344a977eceff1C0Fd](https://polygonscan.com/address/0xac298cd34559b9acfaedea8344a977eceff1c0fd#code)
