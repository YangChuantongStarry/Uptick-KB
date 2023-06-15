## Uptick Network Tokenomics Whitepaper


## Introduction

Uptick Network is building a business-grade infrastructure and ecosystem for non-fungible tokens (NFTs). The platform is designed with a focus on multi-chain and cross-chain interoperability, and includes three key components: NFT infrastructure , NFT marketplace , and NFT ecosystem applications.

**Uptick Chain**

Uptick Chain is a blockchain network built on the Cosmos-SDK and is the core foundation of the Uptick infrastructure; specifically designed to support the use of NFTs.

**IBC & EVM Support**
Integrated support for the Ethereum Virtual Machine (EVM) and part of the Inter-Blockchain Communication (IBC) network. Focusing on providing the interoperable tools and services necessary to enable a wide range of useful and groundbreaking NFT-related scenarios.

**Infrastructure**

Uptick infrastructure provides a set of advanced modularized business protocols on top of Uptick Chain, which are developed by a team with extensive experience in the blockchain industry, and are designed to support a diverse range of business-related NFT functions and features, some of which include:

* Interoperable ERC & CW Asset Standards

* Interchain NFTs via IBC & EVM Networks

* DeFi Protocols for the NFT Economy

* Interchain NFT Metadata Standard

* Decentralized Data as a Service

Uptick Network is built on the Cosmos-SDK and secured by the Tendermint consensus engine. It is classified as an application-oriented chain, and optimized to support specific applications and use cases within the broader blockchain ecosystem.

 Additionally, Uptick Network functions as an independent blockchain zone within the wider Cosmos Ecosystem. It follows the general token utility and incentive model of Cosmos, but also adds its own innovative support for NFT-related infrastructure, ecosystem development, and extended DAO governance.
 
For more details about the technology and architecture of Uptick Network, please refer to the [**Technical Whitepaper** ](https://github.com/UptickNetwork/Uptick-KB/blob/main/WHITEPAPER_Technical.md) 


## Token Utility

Uptick Network's vision is to provide a fundamental framework for the creation and use of high-quality NFTs in the business world. This includes the necessary underlying blockchain technology, along with various other tools to support an array of different commercial environments.

For Uptick Network's specific tokenomics model, please refer to the **[Token Economics]**  section.


Tokens managed by Uptick Chain are not limited to the native tokens supported by the Cosmos-SDK. They also include ERC-20-based tokens and NFTs. Uptick Network has developed a fee model that not only aligns with the Cosmos-SDK, but is also compatible with the EVM, providing flexibility for a wide range of tokens.

 UPTICK is the native platform token used on Uptick Chain, and its utility is divided into four main categories:

* Fees

* Staking

* General Governance

* Extended Rule-based Governance

<img src="https://github.com/UptickNetwork/Uptick-KB/blob/main/image/RuleBased.jpg" width="450px">

### Fees

Uptick Network utilizes its native UPTICK token to set the transaction fees, which serve as incentives for validators to include transactions in the next block. The average transaction fee is approximately 0.001 UPTICK per transaction.

At the nodes where Uptick Chain was officially launched, there is a fundamental consistency between the fees based on EVM (EVM Fee) and those based on the Cosmos-SDK (Cosmos Fee)

Uptick calculates the EVM Fee and the Cosmos Fee through the feemarket module.

**Calculation Formula**

| fee = (baseFee + priorityTip) \* gasLimit |
| --- |

Where baseFee is the fixed-per-block network fee per gas and priorityTip is an additional fee per gas that can be set optionally. Note, that both the base fee and the priority tip are gas prices. To submit a transaction with EIP-1559, the signer needs to specify the gasFeeCap, which is the maximum fee per gas they are willing to pay in total. Optionally, the priorityTip can be specified, which covers both the priority fee and the block's network fee per gas (aka: base fee).

| The Cosmos-SDK uses a different terminology for gas than Ethereum. What is called gasLimit on Ethereum is called gasWanted on Cosmos. You might encounter both terminologies on Uptick since it builds Ethereum on top of the SDK, e.g. when using different wallets like Keplr for Cosmos and MetaMask for Ethereum. |
| --- |

#### Parameter Settings


| Key                      | Type    | Initial Values | Description                                                  |
| ------------------------ | ------- | -------------- | ------------------------------------------------------------ |
| NoBaseFee                | bool    | FALSE          | Control the base fee adjustment                              |
| BaseFeeChangeDenominator | uint32  | 7              | Bounds the amount the base fee that can change between blocks |
| ElasticityMultiplier     | uint32  | 2              | Bounds the threshold which the base fee will increase or decrease depending on the total gas used in the previous block |
| BaseFee                  | uint32  | 1000000000     | Base fee for EIP-1559 blocks                                 |
| EnableHeight             | uint32  | 0              | Height which enable fee adjustment                           |
| MinGasPrice              | sdk.Dec | 0              | Global minimum gas price that needs to be paid to include a transaction in a block |



#### Fee Allocation

In addition to being allocated to the POS nodes and staking accounts, the transaction fees mentioned above will also be collected as community tax and will enter the community pool. A portion of the funds in the pool will be used as part of the token economic model, either to participate in community incentives or to be burned directly as one of the means of controlling inflation.

 Please refer to the ## [Token Economics]##  section for more details.

### Staking

The UPTICK token is integrated into Uptick Network's consensus engine through a system of validators and delegators. UPTICK token holders can participate in network staking and earn rewards for validating transactions and securing the network.

#### Calculation Formula

| inflationRateChangePerYear = (1 - bondedRatio/GoalBonded) \* InflationRateChangeinflationRateChange = inflationRateChangePerYear/BlocksPerYearinflation = Inflation + inflationRateChange |
| --- |

#### Parameter Settings


| **Key**             | **Type**        | **Initial Values**     |
| ------------------- | --------------- | ---------------------- |
| UnbondingTime       | string          | "1814400s"             |
| MaxValidators       | uint16          | 137                    |
| KeyMaxEntries       | uint16          | 7                      |
| HistoricalEntries   | uint16          | 3                      |
| BondDenom           | string          | "stake"                |
| MinCommissionRate   | string          | "0.000000000000000000" |
| InflationRateChange | string (dec)    | "0.40000000000000000"  |
| InflationMax        | string (dec)    | "0.070000000000000000" |
| InflationMin        | string (dec)    | "0.100000000000000000" |
| GoalBonded          | string (dec)    | "0.50000000000000000"  |
| BlocksPerYear       | string (uint64) | "6311520"              |




 #### Staking Rewards Allocation

Staking for non-profit organizations, such as the foundation and ecosystem development.

 **Staking of regular users**

Users can choose to continue staking or unlock after the staking period expires (21 days) based on their preferences.

 **Staking of non-profit orgs (e.g foundation and ecosystem development)**

Based on the results of governance voting, these funds will enter the expanded incentive pool of [More Rule-based Governance], which will be used to encourage the Uptick dApp ecosystem and multi-chain economy.

 **Community pool allocation**

A portion of staking rewards (initially set at 2%) will enter the community pool. This pool will be used to incentivize projects that contribute to the Uptick Ecosystem, as determined by community voting.

Additionally, some tokens may be burned to control inflation and the circulating supply of tokens.

### General Governance

The role of governance is to govern the Uptick Ecosystem to ensure its sustainability and healthy development. Through the governance mechanism, community members can participate in the formulation and modification of protocols, as well as the voting of proposals on the network.

 The role of governance includes, but is not limited to:

* Maintaining the integrity and stability of the Uptick Protocol.

* Defining and modifying protocol parameters and rules, such as inflation rates, transaction fees, and governance parameters.

* Voting to distribute and utilize funds within the community, including those designated for development projects, charitable causes, and other community initiatives.

* Voting to support or oppose proposals for upgrades or changes, such as software version updates or the introduction of new features.

* Encouraging community members to actively participate in community governance, enhancing community consensus and participation, and promoting the development of the Uptick Ecosystem.

#### Governance Function

Uptick's governance can be performed through community voting, including but not limited to:

* Controlling the inflation rate of the native Uptick token by adjusting the settings in the [Parameter Settings] table.

* Burning a portion of the token through voting.

* Determining the amount of rewards and developing the reward regulations for [Extended Rule-based Governance] through voting.

#### Parameter Settings


| **Key**            | **Type**        | **Initial Values**                                     |
| ------------------ | --------------- | ------------------------------------------------------ |
| min_deposit        | array (coins)   | [{"denom":"auptick","amount":"100000000000000000000"}] |
| max_deposit_period | string (time s) | "172800s"                                              |
| voting_period      | string (time s) | "172800s"                                              |
| quorum             | string (dec)    | "0.334000000000000000"                                 |
| threshold          | string (dec)    | "0.500000000000000000"                                 |
| veto               | string (dec)    | "0.334000000000000000"                                 |




### Extended Rule-based Governance

Because Uptick Network has an EVM module in place, the UPTICK token exists on the network in a dual format:

* Cosmos Native Token

* ERC-20 Compatible Token

With EVM (and later CosmWasm and more virtual machine support), Uptick Chain supports smart contract-based token management methods. As a result, there will be many innovative ways to build DAO-like governance rules other than the default methods defined in the Cosmos-SDK module.

Uptick chain will gradually realize the community-based governance of the following on-chain crypto assets, not just the platform token:

* Native platform token: UPTICK

* IBC transferred tokens

* ERC-20 compatible tokens issued by ecosystem applications

* NFT assets with a fair market value

_Please note: The utility of the UPTICK token is subject to further refinement to ensure compliance with legal and regulatory obligations._

## Token Supply

The initial issuance of the UPTICK token is 1 billion (1,000,000,000).

Due to the nature of the PoS network, the annual inflation rate of the Uptick chain will dynamically fluctuate between 4% and 10% based on changes in the staking rate and burn rate.

UPTICK tokens are designed for value storage, with effective control over market circulation through locking mechanisms implemented at both the SDK chain and smart contract level.

## Initial Token Distribution

The initial distribution is structured to incentivize long-term holders and the Uptick Network Ecosystem.

The distribution of UPTICK tokens is planned as follows:

**Private Sale and Advisors: 15%**

 Starting from Uptick Network's launch, there is a one-year vesting period in place, during which the UPTICK tokens are vested on a daily basis at a rate of 1/365. The full amount of tokens are held in vesting accounts, allowing the owner to stake them on the Uptick Network with unvested tokens.

This measure is in place to improve the security of the Uptick Network, while still allowing UPTICK owners to receive block rewards.

**Core Team: 15%**

Starting from Uptick Network's launch, there is a four-year vesting period in place, during which the team will vest 1/8th of its UPTICK tokens every six months. The full amount of tokens are secured in a vesting account with multisig, allowing the owner to stake on Uptick Network with unvested tokens.

This measure is in place to improve the security of the Uptick Network, while still allowing the team to receive block rewards.

**Foundation: 20%**

Reserved to support the operations of the foundation.

**Ecosystem Development: 47.5%**

* Value exchange with strategic interchain partners

* Performance-based incentive for ecosystem application builders and end users (app dev and ops mining)

* Awards for outstanding partners

* Incentives for NFT pledge and loan

* Interchain DeFi farming

* Incentive and awards to Uptick DAO participants and activities

* More

**Airdrop: 2.5%**

The goal for this airdrop is to support the long-term success of Uptick Network and its core ecosystem partners and users. It includes but is not limited to the following categories:

* Media and marketing contributors

* Testnet validator & governance contributors (inc Testnet 1.0 & Testnet 2.0)

* Testnet marketplace contributors (inc Testnet 1.0 & Testnet 2.0)

* Uptick's IRISnet marketplace contributors

* Uptick's Loopring marketplace contributors

* Cosmos Hub $ATOM token holders that meet certain requirement

* IRISnet Hub $IRIS token holders that meet certain requirement

* IRISnet Governance | Supporters of Uptick-related proposals

* Other platforms, applications and communities that support the Uptick project

The distribution of the airdrop will occur in stages, rather than all at once on genesis launch day. Additionally, certain categories of the airdrop will follow a vesting schedule.

## Token Economics

One of the sore points as to why blockchain projects have difficulty landing is that the token economics of many chains are focused on the chain itself, considering only the economic model of L0 or L1, and neglecting the support of token economics for ecological applications and cross-chain ecology.

Uptick Network has designed multi-layered token economics based on the above-mentioned problems. These include:

* Basic Uptick Network Layer

Responsible for the issuance and circulation of the UPTICK token. The token economics at this layer is designed to ensure the stability and security of the UPTICK token.

* Uptick dApp Ecosystem Layer

This includes all the decentralized applications built on top of the Uptick Network. The token economics at this layer is designed to incentivize developers to build and contribute to the Uptick dApp ecosystem.

* Multi-Chain Economy Layer

Cross-chain collaborations and interactions between different blockchain networks. The token economics at this layer is designed to incentivize and facilitate cross-chain transactions and collaborations.

* Community Layer

Uptick Network community members and stakeholders. The token economics at this layer are designed to incentivize community participation and contribution, and to ensure the sustainability and growth of the Uptick Network.

By designing multi-layered token economics, Uptick Network aims to create a comprehensive and sustainable ecosystem that benefits all stakeholders, including users, developers, investors, and the broader blockchain community.

_The following figure illustrates the structure of Uptick Network's multi-layered token economics:_

<img src="https://github.com/UptickNetwork/Uptick-KB/blob/main/image/StructureofUptick.jpg"  width="650px" style=" margin-top:30px;margin-bottom:30px;">

A multi-layered token economy offers several advantages:

**Integrity**

 The multi-layered architecture of the token economics takes into account various business scenarios and allocates the interests of all parties, including chains, cross-chains, and ecosystems.

**Scalability**

 The Uptick DAO governance and multi-chain economy model are based on Turing-complete EVM contracts, which can theoretically implement any token economic logic.

**Security**

 General Governance is based on the Cosmos-SDK, which has been verified by the Cosmos Ecosystem to ensure the security of the token economic model.

In addition, the security of the Uptick DAO governance and multi-chain economy model is ensured by the underlying EVM security mechanism. Unlike DeFi applications, the contract account of the Uptick Network economic model contract is a Cosmos module account, which prevents security risks caused by the leakage of private account keys.

**Decentralization**

 The economic model rules and modifications are implemented through the Cosmos-SDK governance module, which requires confirmation by a majority of stakers. This decentralized approach ensures that decisions are not controlled by one single entity.

### General Governance

Although there is no clear definition of L0 and L1 in the Cosmos Ecosystem, the Cosmos-SDK can be considered the equivalent of L0. The Cosmos-SDK is a framework that enables the construction of hubs and zones in the Cosmos Ecosystem.

It has been proven to be both secure and effective in achieving decentralized governance. Therefore, Uptick Network has chosen to use the Cosmos-SDK to ensure the security, effectiveness, and decentralized governance of its token economics.

**Dynamic Staking Model**

Uptick Network employs a dynamic staking model that adjusts the annual inflation rate based on the percentage of UPTICK tokens that are currently staked. When more tokens are staked, the inflation rate decreases, which can help maintain the value of the token.

Additionally, a portion of transaction fees are burned, which reduces the overall supply of UPTICK and can increase the value of the remaining tokens.

UPTICK token holders have the ability to participate in the decision-making process of network governance, such as voting on proposals for network upgrades and parameter changes. This gives users a voice in the development and direction of the Uptick Network.

### Uptick DAO Governance (Extended Rule-based Governance)

The Uptick DAO is a set of rule-based smart contracts built using EVM contracts in the Uptick Ecosystem. While the contract is based on EVM, its rules (contract generation) and modifications (contract upgrades) require validation through the voting of the underlying Uptick validators.

This contract ensures both the powerful decentralized finance functions of EVM contracts and the decentralized management models of the Cosmos system.


<img src="https://github.com/UptickNetwork/Uptick-KB/blob/main/image/Validators.jpg" style="width: 90%; margin-top:30px;margin-bottom:30px;">


Uptick DAO Governance will cover different categories with different rules, such as rights management, business grade application development and operation, decentralized data services, etc.

The following is an example of operational performance-based business application rewards governance. The flow describes how the infrastructure layer can effectively support the ecosystem application layer, and create a win-win result:

* The staking reward by the foundation and ecosystem development funds will be donated to the EARP (Ecosystem Application Reward Pool).

* Any validator can also donate a portion of commission/rewards to the EARP to support ecosystem applications.

* The distribution of EARP funds is based on performance measurement metrics, or say, a set of EARP rules.

_Example:_

* An application can participate in EARP's stake-to-reward method to attract its users. It encourages users to stake tokens on this application channel by receiving interest rewards and also member privileges in this application.

* The higher the TVL from this application, the more value this application can bring to the Uptick Ecosystem.

* An application can participate in EARP's transaction-to-mine method to attract its users. The transactions generated by this application channel will be recorded and analyzed by the data analyzer on the infrastructure.

* An application can participate in EARP's NFT stake-to-earn method to attract its users. The valuation of the NFT should be fairly recognizable by the market.

* There will be more EARP rules added to this program. The purpose is to provide meaningful and sustainable funds for ecosystem applications that can be operated well in business. The application can pass such funds to its users.

* Ultimately, the successful execution of EARP rules, such as stake to earn and transaction to earn, can generate more profits for stakers through transaction fees, truly achieving a win-win situation.


<img src="https://github.com/UptickNetwork/Uptick-KB/blob/main/image/EappRules.jpg" style="width: 90%; margin-top:30px;margin-bottom:30px;">


### Multi-Chain Economy Model

The multi-chain economic model is still in the exploratory stage and mainly includes two aspects:

**Interchain transactions and stakings**

* Between Uptick Chain and IBC chains

* Between Uptick Chain and EVM chains

**Incentive for cross-chain infrastructure service providers**

* Cross-chain relayer for IBC (Inter-Chain Communication)

* Cross-chain bridge for UCB (Uptick Cross-chain Bridge)

* Cross-chain data analysis tools based on the Uptick cross-chain protocol.

### Inflation control

In a POS blockchain, inflation control is achieved through various mechanisms, such as adjusting the block reward and the supply of tokens. In the case of the Uptick Network, there are several ways to control inflation:

**Block reward adjustment**

The block reward is the amount of tokens that validators receive for each block they validate. By adjusting the block reward, the inflation rate can be controlled. In Uptick Network, the block reward is determined by the total supply of tokens and the target annual inflation rate.

**Dynamic staking rewards**

Uptick Network also supports dynamic staking rewards, which adjust the rewards based on the amount of tokens staked. This means that the more tokens that are staked, the lower the rewards, and vice versa. This mechanism is designed to encourage more token holders to stake their tokens and help secure the network.

**Community-driven governance**

Uptick Network is built on a community-driven governance model, where token holders can propose and vote on changes to the network, including changes to the inflation rate. Through community-driven governance, the inflation rate can be adjusted to reflect the needs and desires of the community.

By carefully balancing these mechanisms, over time the network can maintain a stable and sustainable inflation rate.

## Roadmap and Future Plans

The development roadmap for Uptick Network is ever-evolving with the development of the industry.

The following are the confirmed plans with clear goals:

* Support for Wasm contracts

* Importing of ORACLE into infrastructure

* Release of Uptick Web3 interface

* Implementation of developer plans

* Implementation of modularized business logic protocols

* Release of more local and interchain NFT asset standards

* Development of Uptick DAO Governance regulations

* Establishment of the multi-chain economy model

* more

## Conclusion

Uptick Network's tokenomic model includes multiple layers, such as general governance, Uptick DAO governance, and a multi-chain economy model. This combined model is more comprehensive and scalable than a simple chain-based model, with token economics at each layer ensuring chain-level security and supporting the healthy growth of business grade ecosystems.

Furthermore, Uptick Network intends to introduce a long-term performance based dev-mining program aimed at gradually expanding infrastructure and supporting a diverse range of ecosystem applications.