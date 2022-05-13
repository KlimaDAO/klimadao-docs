# DAO Wallet

The DAO wallet is an address guarded by a simple Gnosis safe implementation. The DAO wallet holds all the DAO funds accumulated over time.

Access to the DAO wallet is controlled by a 3 of 5 multi-sig held by members of the core team.

The DAO wallet's revenue comes from a 30% fee on every bond: [the depository contract mints an additional 10% of the bond payout in KLIMA](https://github.com/KlimaDAO/klimadao-solidity/blob/285cb5590a1fb312e26202027346d5f5c6d21394/contracts/bonds/upgradeable/KlimaBondDepositoryUpgradeable.sol#L278) and deposits it into the DAO wallet.

* &#x20;V1: [0x65a5076c0ba74e5f3e069995dc3dab9d197d995c](https://polygonscan.com/address/0x65a5076c0ba74e5f3e069995dc3dab9d197d995c)
