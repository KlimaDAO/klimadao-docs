# Testing

The recommended way to test Klima protocol contracts or smart contracts utilizing the [Klima Retirement Aggregator](guides/retirement-aggregator-contract-guide.md) is using a forked blockchain testing environment. Popular smart contract development tools such as Foundry or Hardhat allow you to fork the current state of the Polygon blockchain using an RPC. This allows you or your locally deployed contracts to interact with existing contracts as if you were actually on the Polygon mainnet.

* [Foundry Forge Forked Testing docs](https://book.getfoundry.sh/forge/fork-testing)
* [Hardhat Forking docs](https://hardhat.org/hardhat-network/docs/guides/forking-other-networks)

Once you've forked the Polygon mainnet, review existing [contract deployment addresses](deployment-addresses.md).

If you prefer to make use of the Mumbai Testnet, see [this constants file](https://github.com/KlimaDAO/klimadao/blob/441bb1931a937d263829ca831fa157c652330aea/lib/constants/index.ts#L24) in our public frontend repository for a complete listing of the testnet contract addresses.
