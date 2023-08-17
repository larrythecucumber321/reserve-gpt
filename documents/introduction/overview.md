Link: https://reserve.org/protocol/introduction/#overview
Title: Overview of Reserve

Overview
The Reserve Protocol allows anyone to create stablecoins backed by baskets of ERC20 tokens on Ethereum. Stable asset backed currencies launched on the Reserve protocol are called “RTokens”.

Once an RToken configuration has been deployed, RTokens can be minted by depositing the entire basket of collateral backing tokens, and redeemed for the entire basket as well. Thus, an RToken will tend to trade at the market value of the entire basket that backs it, as any lower or higher price could be arbitraged.

RTokens can be overcollateralized, which means that if any of their collateral tokens default, there's a pool of value available to make up for the loss. RToken overcollateralization is provided by Reserve Rights (RSR) holders, who may choose to stake their RSR on any RToken. Staked RSR can be seized in the case of a collateral default, in a process that is entirely mechanistic based on on-chain price-feeds, and does not depend on any governance votes or human choices.

RTokens can generate revenue, and this revenue is the incentive for RSR holders to stake. Revenue can come from yield from lending collateral tokens on-chain or revenue shares with collateral token issuers. Governance can direct any portion of revenue to RSR stakers, to incentivize RSR holders to stake and provide overcollateralization. If an RToken generates no revenue, or if none of it is directed to RSR stakers, it probably won't have any RSR staked on it, and thus won't be protected by overcollateralization.

Each RToken is governed separately, and each can have an entirely different governance system. Initial RTokens will likely have relatively simple governance systems, which will probably evolve over time. That evolution is up to those that hold power in the initial governance systems.

Governance defines not just the basket to back an RToken, but also an ordered list of emergency collateral. So there's a current basket, and a series of assets that can be deployed to the basket in the case of a default. A collateral token is considered to have defaulted if it's gone down in value more than a defined amount for a long enough time, relative to its reference or target unit (described in the Monetary Units section).

For the kinds of RTokens the core team is imagining, default will be an extremely rare "black-swan" situation, not something that occurs regularly. But still, it could happen, and the purpose of the overcollateralization mechanism is to preserve RToken holders’ value if it does.

Governance can update the basket configuration regularly. When the current basket is updated, or in the case of a default, the protocol makes on-chain trades to reach the new basket composition. This trading is modularized so that it can happen in different ways over time as on-chain liquidity evolves. Currently, there is a plugin built for Gnosis Auctions (batch auctions) but in the future, once on-chain protocol trading can be done without danger of front running, then we expect AMMs and other trading methods to be an option.

As with any smart contract application, the actual behavior may vary from the intended behavior, and it's safest to wait for an application to be in use for a long period of time before trusting it to behave as expected. This overview and subsequent documentation describes the intended behavior.
