# Token Bridges

We have two bridges as explained below

1. Yes Coin Bridge:  ****The bridge, based on POA's bridge implementation, is used to transfer Yes Coin tokens between the Yes Coin chain and the Ethereum network.
2. YES20 token bridge: This bridge is used to transfer YES20 tokens into Yes Coin chain and back. Please not that Yes Coin bridge is not supposed to be used to transfer  . 

The bridge, based on POA's bridge implementation, is used to transfer Yes Coin tokens between the Yes Coin chain and the Ethereum network.

Tokens sent to the respective bridge contract on one network \(whether it's Yes Coin or Ethereum\) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender.

The validators of the bridge on both network are the Yes Coin chain validators. This means that validators, as part of their governance responsibilities, also need to validate bridge transactions and therefore hold Yes Coin tokens to "approve" bridge transactions on Yes Coin chain and hold ETH to "approve" transactions on Ethereum.

Each bridge transaction must be approved by a majority \(over 50%\) of the validators in order to be processed successfully.

The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of Yes Coin tokens between the two networks, the bridge is also responsible for network core functionality events:

**Mint block reward distributed on the Yes Coin chain on Ethereum**

Each cycle the total block reward distributed on Yes Coin chain is minted on Ethereum and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on Yes Coin chain, waiting for all bridge validators on Yes Coin chain to sign it, and eventually sending a transaction to mint on Ethereum \(by the last signing validator\).

**Update Yes Coin chain validators on Ethereum**

Each cycle the Yes Coin chain validators are selected from a random snapshot of pending validators.

Those validators, being also the bridge validators, need to be updated on Ethereum as well.

This works by listening to the \`InitiateChange\` event emitted by the Consensus contract on Yes Coin chain, waiting for all bridge validators on Yes Coin chain to sign it, and eventually sending a transaction to set the bridge validators on Ethereum \(by the last signing validator\).

{% hint style="info" %}
Yes Coin chain bridge - [0xd617774b9708F79187Dc7F03D3Bdce0a623F6988](https://yesscan.io/address/0xd617774b9708f79187dc7f03d3bdce0a623f6988)

Ethereum bridge - [0x07C53925485179505e1189021c8f794A2A16da54](https://etherscan.io/address/0x07C53925485179505e1189021c8f794A2A16da54)

Yes Coin token on Ethereum - [0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d](https://etherscan.io/token/0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d)
{% endhint %}

**Using the bridge**

**Transfering from Ethereum mainnet to Fusenet** - Send your erc20 Yes Coin tokens to the Ethereum bridge for them to be released from the Yes Coin chain bridge and be avaliable in your native Yes Coin wallet.

**Transfering from Fusenet to Ethereum mainnet** - Send your Native Yes Coin tokens to the Yes Coin chain bridge for them to be released from the mainnet bridge and be avaliable in your Mainnet wallet. 

