# Yes Coin Studio



![Yes Coin Studio architecture](../../.gitbook/assets/image%20%283%29.png)

## Backend Infrastructure

The backend is composed of the following independent services

* Studio API Backend has two purposes. Provides an API for fast and convenient querying of the blockchain data for the Studio DApp. Transmits heavy and complicated transaction flows on behalf of the user.
* Yes Coin-funder service used to fund community members and wallet users on the Yes Coin blockchain.
* Yes Coin IPFS proxy used for fast fetching and storing data in IPFS.

## Contracts

Yes Coin studio is designed to launch DeFi communities on the Yes Coin network. The community contract binds together most of the services and features of the Studio. Among other things it consists of:

* Entities List contract to store community members and their roles
* Community YES20 tokens on Yes Coin network with transfer rules
* YES20 tokens on Ethereum. This is the token that the user issues as part of the community deployment process
* [Multitoken bridge](https://github.com/fuseio/bridge-contracts) - to minimize friction and costs we extended the POA YES20-YES20 bridge contract to many-YES20-to-many contract.

## Plugins

The plugins are used to customize the community to your specific needs. These can be smart contracts, backend services or the integration of both. The currently available plugins are:

* Business List - allows you to add businesses to you community. Businesses are Entities List members with special roles.
* Join Bonus - define a join bonus for new community members.
* Fiat Ramp - Currently integrated to [Transak](https://transak.com/) and [Moonpay](https://www.moonpay.io/) to allow easy deposit and withdraw using Bank Accounts and Payment Cards.
* More plug-ins coming soon.

