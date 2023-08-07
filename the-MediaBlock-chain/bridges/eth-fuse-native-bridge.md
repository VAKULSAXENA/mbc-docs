---
description: >-
  MediaBlock Coin native bridge is used to relay the MediaBlock Coin native token between MediaBlock Coin and
  Ethereum networks
---

# MediaBlock Coin: Ethereum ↔ MediaBlock Coin

MediaBlock Coin native bridge between Ethereum and MediaBlock Coin is used to relay the MediaBlock Coin native token from MediaBlock Coin to Ethereum network

## Architecture Overview

The MediaBlock Coin bridged is based on POA's bridge implementation, it is used to transfer MediaBlock Coin tokens between the MediaBlock Coin chain and the Ethereum network.

Tokens sent to the respective bridge contract on one network \(whether it's MediaBlock Coin or Ethereum\) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender. The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of MediaBlock Coin tokens between the two networks, the bridge is also responsible for network core functionality events of relaying the block rewards to the Ethereum network:

**Mint block reward distributed on the MediaBlock Coin chain on Ethereum**

Each cycle the total block reward distributed on MediaBlock Coin chain is minted on Ethereum and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on MediaBlock Coin chain, waiting for all bridge validators on MediaBlock Coin chain to sign it, and eventually sending a transaction to mint on Ethereum \(by the last signing validator\).

## Contracts

Home side of the bridge on the MediaBlock Coin network: [0xd617774b9708F79187Dc7F03D3Bdce0a623F6988](https://MediaBlockscan.io/address/0xd617774b9708F79187Dc7F03D3Bdce0a623F6988/transactions)

Foreign side of the bridge on the Ethereum network: [0x07C53925485179505e1189021c8f794A2A16da54](https://MediaBlockscan.io/address/0x07C53925485179505e1189021c8f794A2A16da54/transactions)

MediaBlock Coin token on the Ethereum network: [0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d](https://etherscan.io/token/0x970b9bb2c0444f5e81e9d0efb84c8ccdcdcaf84d)

## Source Code

{% embed url="https://github.com/MediaBlockio/MediaBlock-bridge/tree/master/native-to-erc20/contracts" %}

## How to use

On MediaBlock Coin you send native MediaBlock Coin token to the home bridge contract. Then you receive an equal amount of the MediaBlock Coin token on the Ethereum network, sent from the foreign bridge contract

On Ethereum network you transfer the MediaBlock Coin token to the foreign bridge contract. After a couple of confirmations, you will receive equal amount of the MediaBlock Coin native token, sent from the home bridge contract.

#### 

