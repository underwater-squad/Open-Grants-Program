# Open Grant Proposal

> This document is referenced in the terms and conditions and therefore needs to contain all the required information. Don't remove any of the mandatory parts presented in bold letters or as headlines! See the [Open Grants Program Process](https://github.com/w3f/Open-Grants-Program/blob/master/README_2.md) on how to submit a proposal.

* **Project:** Subswap V1
* **Proposer:** Hyungsuk Kang
* **Payment Address:** bitcoin:18BV6ZBt2P6zZBVpF4C5wQ3KANDoiRzDB9

## Project Overview :page_facing_up: 

### Overview
Subswap V1 will create the first decentralized markets to buy & sell $DOT & other substrate-based tokens. It is a continuation of the [Proof-of-Concept](https://devpost.com/software/subswap-3oe6lm) presented for the 2020 Chainlink hackathon that received the Polkadot Runner-up Prize. 

### Project Details 
Subswap aims to be the next generation of crypto exchange governed by $SUNI, the Subswap Protocol token. The community members will be able to vote on-chain to fund ecosystem developments & public goods. $SUNI will create incentives for Liquidity Providers to passively earn fees on trading volume & be apart of community governance. Our development plan is to start migrating liquidity to Polkadot as soon as possible following the current Polkadot Network standard and then take advantage of Polkadot Network's upgradability and governance to develop the protocol into what the users want and community votes for.

Subswap V1 has four runtime modules and primitives to share data between them: Asset, Exchange, Pool, Governance. Primitives will be a trait and generic type that is the data type across the runtime modules to operate. The type argument for the generic type will be u128 or U256, and its trait will act similarly to [orml_trait](https://github.com/open-web3-stack/open-runtime-module-library/tree/master/traits) from Acala for interoperability. Differences between Subswap primitives and Acala primitives are considered only when both primitives are interoperable. 

- Asset is a registry of crypto assets. Current implementation is in the [subswap repo](https://github.com/underwater-squad/subswap-2.0.0/blob/master/pallets/subswap/src/lib.rs).  

- Exchange is a custodial decentralized exchange platform where $SUNI is used to create a pair between two crypto assets. Subswap team currently has [implemented](https://github.com/underwater-squad/subswap-2.0.0/blob/master/pallets/subswap/src/lib.rs) UniswapV2 (UniswapV2Router.sol, UniswapV2Factory.sol, UniswapV2Pair.sol). More options such as [DodoEX]() and [Curve.fi]() are being researched to reduce the Impermanent loss & port to substrate runtime without making overflow using U256 type on calculation.

- Pool is a pool reward platform where $SUNI is used to create a pool where token holders are rewarded for staking. Current [implementation on Ethereum](https://github.com/yam-finance/yam-protocol/blob/master/contracts/distribution/YAMCOMPPool.sol) are common across defi projects(e.g. yam, based.money, etc). Sending information to a synthetic platform in the Polkadot ecosystem is being considered. Subswap team will support $SUNI pool with Liquidity provider tokens so that liquidity providers can better participate in the community governance. 

- Governance is a mutation of the Democracy module from Parity technologies' [Amir singh](https://github.com/4meta5), and it provides governance for liquidity providers, by liquidity providers, of liquidity providers. The difference from the original module will be `WhiteList` storages. The governance module will be used for whitelisting a pair or an asset registered in Exchange and Asset module respectively. For example, on democracy's white_list() module function request, a proposal is generated for whitelisting an asset in the blockchain network after checking the asset exists in the asset module's storage. The Governance module will keep the whitelisted asset or pair identifiers with passed referendum hash by the community so that token holders or newcomers can verify the legitimacy without having to trust a central party. Subswap is a decentralized exchange with on-chain governance which automatically applies consequences with the proposal. Although there are DAOs that achieve governance with proposals recorded in a blockchain as a request. Subswap has [Democracy](https://github.com/paritytech/substrate/tree/master/frame/democracy) module made by [Amir](https://github.com/4meta5) to provide real automated result.

### Ecosystem Fit 
Subswap is the only Substrate project which [demoed](https://devpost.com/software/subswap-3oe6lm) with an automated market maker with clear reference codes posted on 2020/09/30. Subswap community will support other upcoming legit parachains to make a genuine market with Decentralized governance with the council who shares the value of trustlessness with technical innovation. 


## Team :busts_in_silhouette:

### Team members
* Name of team leader: Hyungsuk Kang 
* Names of team members: Josh Han, Jacob Makarsky, Sanghyun Rhee

### Team Website	
* subswap.exchange

### Legal Structure 
Currently no registered legal entity - considering different jurisdictions 

### Team Code Repos
* https://github.com/orgs/underwater-squad/

### Team members
- Hyungsuk Kang is passionate about building new software based in Rust programming language. He has been working in blockchain field over 3 years as software developer - currently @ Terraform labs in Korea, working on connecting Terra & Polkadot. He has been an Polkadot Ambassador for over an year and attends frequent meetups/events in Seoul. 
- Josh Han is an entrepreneur passionate about Decentralized Finance & DAOs. He has been working in the blockchain industry since 2017 and most recently researched governance models at the United Nations Project Office on Governance. Also a Polkadot Ambassador and Managing Partner @ DWM. 
- Jacob:
- Sanghyun: 

### Team LinkedIn Profiles
* [Hyungsuk Kang](https://www.linkedin.com/in/hyungsukkang/) - Lead developer, Operation & Strategy
* [Jacob Makarsky](https://www.linkedin.com/in/jacobmakarsky/) - Frontend developer
* [Josh Han](https://www.linkedin.com/in/joshglobal/) - Business development, Marketing & focused on Community Governance Development 
* [Rhee Sanghyun](https://www.linkedin.com/in/sang-hyun-rhee-17b5b3142/) - Korean & Chinese business development

## Development Roadmap :nut_and_bolt: 

This section should break out the development roadmap into a number of milestones. Since the milestones will appear in the grant contract, it helps to describe the functionality we should expect, plus how we can check that such functionality exists in the product. Whenever milestones are delivered, we refer to the contract to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions it should be clear how the project is related to Substrate and/or Polkadot. We recommend that the scope of the work can fit within a 3 month period and that teams structure their roadmap as 1 month = 1 milestone. 

For each milestone:
* Please be sure to include a specification of the software. The level of detail must be enough so that we are able to verify that the software meets the specification.
* Please include total amount of funding requested per milestone.
* Please note that we require documentation (e.g. tutorials, API specifications, architecture details) in each milestone. This ensures that the code can be widely used by the community.
* Please provide a test suite, comprising unit and integration tests, along with a guide on how to run these.
* Please commit to providing a dockerfiles for the delivery of your project. 
* Please indicate the milestone duration, as well as number of Full-Time Employees working on each milestone, and include the number of days along with their cost per day.

### Overview
* **Total Estimated Duration:** 3 months
* **Full-time equivalent (FTE):**  6
* **Total Costs:** 3 BTC

### Milestone 1 — Run testnet to raise awareness of defi in Polkadot ecosystem in local communities
* **Estimated Duration:** 3 months
* **FTE:**  3
* **Costs:** 1.5 BTC
 
From the experience of managing Korean Polkadot community, Hyungsuk found out that most korean community newcomers does not even know what defi is. They do not have Ethereum to test out how uniswap works. To introduce defi with faster user experience and governance and onboard future subswap community members and validators, Subswap team will make a dapp based on [substrate-frontend-template](https://github.com/substrate-developer-hub/substrate-front-end-template/find/master) with remote secured websocket connection from subswap local testnet. The testnet will have swap features and governance  

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | A gitbook documentation link on the operation of subswap and its functionality in English or Korean explaining the overall operation and details on each runtime module with references|
| 0c. | Testing Guide | Test codes will be provided in test.rs in each module focusing on overflows | 
| 1. | primitives | We will apply orml_trait in subswap blockchain to share data across modules |  
| 2. | Substrate module: Asset | We will create a Substrate module that will register assets following [PSPs]() for interoperability | 
| 3. | Substrate module: Exchange | We will create a Substrate module that will create automated market makers for two different assets rewarding liquidity providers solving overflows in Time Weighted Average Price(TWAP) calculation |  
| 4. | Substrate chain | Modules Asset and Exchange of our custom chain will interact in such a way that UniswapV1 does with faster speed and integration with Polkadot browser extensions(e.g. Speckle browser extension) |  
| 5. | Discord server | A discord server for supporting questions from overall operations in subswap and future discussion channel for council for subswap |  
| 6. | Docker | We will use a docker-compose.yml file from substrate-node-template to provide container |

### Milestone 2 - Test XCMP module in Rococo testnet
* **Estimated Duration:** 3 months
* **FTE:**  3
* **Costs:** 1.5 BTC

Rococo testnet has been launched and The team expects that Rococo will be opened for other parachain teams in the late december. To test interchain asset transfer and exchange, we expect to collaborate other parachain teams such as Subsocial, Plasm, etc. The project will be built in [substrate-parachain-template]().

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 |
| 0b. | Documentation | A gitbook documentation link on the operation of subswap and its functionality in English or Korean explaining governance and pool module with references|
| 0c. | Testing Guide | Test codes will be provided in test.rs in each module focusing on overflows | 
| 1. | Substrate module: Pool | A module for staking reward platform which acts like [🍠 ](yam.finance), or UNI feature in uniswap |  
| 2. | Substrate module: Governance sets | There are bunch of modules(e.g. collectives, democracy, council, technical) to achieve governance. Subswap team will integrate these modules with additon to whilisting features. Some modules can be mutated due to the council's or community members' decision. |  
| 3. | Substrate module: Contract sets | There may be a contract module to provide addtional features to the registered asset within the subswap chain. If this increases the block finalization time, this module may be removed. |
| 3. | Substrate chain | Pool module is expected to incentivize liquidity providers to earn $SUNI for governance, governance module sets with council will provide governance not only with tokens but also reputations. |  
| 4. | Docker | We will use docker-compose.yml file in the substrate-node-template to provide container.|


### Community engagement

For milestone 1, it is expected to engage with local communities first with telegram [chat](https://t.me/PolkadotKR).

For milestone 2, A medium article will be shared in the publication [here](https://medium.com/underwater-squad), and the progress will be shared in [discord](https://discord.com/channels/761602589585571860/761602590051270656).

## Future Plans
Underwater squad will setup a software development company based in Seoul after the congress passes amendments regarding cryptocurrencies [here](http://likms.assembly.go.kr/bill/billDetail.do?billId=PRC_S1W9V1R1K2Y5J1A5K3V1Z0L4X1H3W9). Subswap will solve the hardest problems to solve liquidity between crypto assets. 

## Additional Information :heavy_plus_sign: 

Possible additional information to include:
* What work has been done so far?
* Are there are any teams who have already contributed (financially) to the project?
* Have you applied for other grants so far?

Current working repo:
[subswap node](https://github.com/underwater-squad/subswap-2.0.0)

Hyungsuk has worked on setting up Prometheus and Grafana for polkadot/substrate with [B-harvest]().

Current costs have come out of the Prize Money from the Chainlink Hackathon 
