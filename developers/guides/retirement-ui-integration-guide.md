---
description: Frontend application for retiring tokenized carbon credits
---

# Retirement UI Integration Guide

### Query Params

To facilitate integrations, the KlimaDAO retirement interface supports query parameters to prefill a defined set of arguments.

Every field can be pre-filled, including selective retirement.

```
  quantity, // 1.23
  inputToken, // "bct" | "nct" | "mco2" | "usdc" | "klima" | "sklima" | "wsklima";
  retirementToken, // "bct" | "nct" | "mco2";
  beneficiary, // John Doe
  beneficiaryAddress, // 0x12345678912345678912345678912345678912345
  message, // Hello world
  projectTokens  // 0x12345678912345678912345678912345678912345
```

You can provide multiple arguments for `projectToken` and these will be automatically filled into the selective retirement fields (and the 'Advanced' dropdown will open itself to reveal them automatically).

Example URL with all fields filled, and 2 selective project tokens:

```
https://app.klimadao.finance/#/offset
  ?quantity=123
  &inputToken=klima
  &retirementToken=mco2
  &projectTokens=0x1234
  &projectTokens=0x5678
  &beneficiary=The%20Devs
  &beneficiaryAddress=0x123
  &message=Thanks%20devs!
```

[Original pull request implementing this feature for reference.](https://github.com/KlimaDAO/klimadao/pull/318)
