Link: https://docs.google.com/document/d/1FKP4xJbYuPnxDCzCUp45ce20DhISPpdhvV7o6ocfsx0/edit
Title: Reserve FAQ

FAQ

What is Reserve’s mission?
Increase adoption of, and expand access to sustainable, inflation proof, stable currency.

What is the Reserve protocol?
Reserve is a free, permissionless platform to build, deploy and govern asset-backed currencies - we call them “RTokens.”

What is the asset-backed currency revolution?
100 years ago US Dollars were backed and redeemable for gold. In the 1970s the US shifted from the gold to the fiat standard, “backed by full faith and credit of the US government.” Since that time the US has printed $30 Trillion in new debt, and the USD lost 87% of its purchasing power, which is unsustainable. US inflation is a major export and as of Nov 2022, there were 5 countries worldwide with an inflation rate higher than 100%, and 23 countries exceeding 20%. Blockchains enable a new kind of money, backed 1:1 with any mix of crypto, yield-bearing DeFi primitives, or tokenized commodities like gold, loans, equities, bonds, and real estate.

What is the Reserve App (“RPay”)?
In 2021 Reserve launched the RPay App utilizing the RSV stablecoin to help people in Latin America protect their livelihood from hyperinflation. There are over 670,000 registered users, 25,000 merchants, and over $5 billion in cumulative transactional volume. As of March 2023, RSV has been replaced in the Reserve app with the new RToken eUSD.

What is the difference between the Reserve Protocol and the Reserve App?
The decentralized Reserve Protocol is a DeFi protocol allowing anyone to create an RToken. The centralized RPay app allows anyone in Latin America to receive, save and spend in the eUSD stablecoin across 18 countries.

Who will create RTokens?
Anyone can create an RToken at Register.app - no-code experience required. Defi entrepreneurs, protocols and apps are likely to lead RTokens launches but we are also seeing interest from hedge funds, TradFi, and even rewards programs and video game/metaverse developers.

How do RTokens provide proof of reserves?
Proof of reserves for RTokens are on-chain, verifiable 24/7. An effortless token explorer UI, the Register.app has been developed allowing users to view on-chain collateral and monetary policy parameters for RTokens. Also, anyone will be able to verify an RToken’s details on Etherscan, by simply inputting its address. Here’s a eUSD’s page, for example. Lastly, software developers can query the chain themselves, involving the use of code or blockchain indexing services such as Dune.

Are RTokens algorithmic?
No, RTokens are not algorithmic. RTokens are fully backed 1:1 with exogenous collateral (aka external, unrelated assets) that, via smart contracts, are able to be redeemed at any time for the underlying assets.

How are RTokens decentralized?
Collateral baskets are tokenized on-chain, with the smart contract risk diversified over multiple protocols and assets. Each RToken is governed separately by RSR stakers and each can have an entirely different governance system.

What RTokens are available to mint?
As of April 2023, eUSD, ETH+ and hyUSD are available at Register.app, use the dropdown box to select from a number of RTokens and learn about their mandate, asset backing, staking and governance

Where can I stake RSR and what are the benefits and risks?
Access Register.app and select an RToken for staking. RSR staking is necessary in order to participate in governance, and to earn rewards. Stakers are also providing first loss capital in the event a collateral asset fails in the RToken or some other type of black swan. Learn more about staking here.

What is the RSR token?
RSR is the governance token for the Reserve Protocol ecosystem and can be staked on any RToken. Staked RSR holders can participate in RToken governance, earn staking fees, and provide over-collateralization.

What are collateral plugins and why are they important?
The protocol needs to know how to price an ERC20 (oracle configuration), how to identify revenue against some baseline measure (definition of the reference unit), and auxiliary things like how to claim rewards/emissions that the protocol might earn by holding the ERC20. None of this can be straightforwardly inferred from just the ERC20 contract, hence the need for collateral plugins. Learn more about collateral plugins here.

What is the Eli5 relationship between the “unit of account”, the “target unit” and the “reference unit” of RTokens?
The protocol compares a collateral asset’s (e.g. cUSDC) value relative to a Reference Unit (e.g. USDC), and again with a Target Unit (e.g. USD) to determine whether the collateral asset is in default (in the example of cUSDC and USDC, the Reference Unit generally shouldn’t deviate from the Target Unit). The Unit of Account is solely used for internal protocol operations–it does not have a direct relationship with the Target Unit or Reference Unit. Learn more here.

Where does RToken yield (revenue sharing) come from?
Deposits in DeFi protocols such as Aave, Compound, Uniswap and Convex provide the depositor a receipt token that accrues yield. When these receipt tokens are used in collateral baskets for RTokens, the Reserve Protocol’s on-chain operations harvest this yield to distribute to RToken stakeholders. This is 100% on-chain.

How do RTokens harvest and reflect yield in price?
As the value of collateral tokens appreciate more RTokens are created, then sent to the Furnace and melted. The initial RToken supply is now redeemable for more collateral tokens so the exchange ratio is >1 target unit (usually a dollar). Related: Once the RToken reaches some level of maturity, any difference in price between the protocol and a CEX/DEX can be arbitraged. RTokens that share revenue to RToken holders do not rebase, which means that they're not really stablecoins - their price will continue to go up over time ($1.00, $1.10, $1.20, and so on).

How do RTokens share revenue with RSR Stakers?
Accrued revenue is used to buy RSR. This increases the redemption ratio of the staked RSR token (e.g. eusdRSR) relative to plain RSR. Therefore, RToken revenue creates demand for RSR.

Are the Reserve Protocol smart contracts decentralized?
Yes. The core contracts are only upgradable through governance proposals that get voted on by RSR stakers, and these proposals can either be to change a single parameter or upgrade a contract. Technically a new contract is deployed, and there's a proxy contract sitting in front that changes to point from the old implementation contract to the new implementation contract.

Why would aToken or cToken holders give up a % of yield by depositing in collateral basket to mint RTokens?
Minting would primarily be driven by (a) market makers that have calculated the net of RToken holder yield + Curve LP yield, being greater than the original receipt token yield or (b) arbitrageurs capturing the difference between mint price and trading price. There are other users of the RTokens seeking passive yield with overcollateralization which may most easily satisfy their need through trading on a DEX or CEX.

How is the peg maintained and what anti-bank run mechanisms are native to RTokens?
The RToken peg is maintained by always allowing a full minting and redemption for the underlying collateral on-chain. This enables market participants to take advantage of an arbitrage opportunity if the price of the RToken in the secondary market deviates from the net asset value of the underlying collateral.
RToken anti-bank run mechanisms include 1:1 exogenous asset backing, proof of reserves on chain, verifiably predictable recovery with on-chain overcollateralization and proportional funds distribution.
RTokens do not have the same recursive, negative feedback loops that UST/LUNA had since RTokens are not minted from any governance token. RTokens are 1:1 backed with exogenous assets with proof of reserves on-chain.
In the event one of the exogenous assets in the RToken basket drops by 10%, 20% or even 100%, the protocol would slash RSR stakers of the affected RToken and sell the failing collateral to buy the pre-programmed emergency collateral basket. Briefly the RToken would be below peg, yet the 100% redemption outcome would be verifiably predictable given the on-chain overcollateralization. RTokens were battle-tested during the Silicon Valley Bank run that played a role in the March 9, 2023 depeg of USDC - learn more here about how the protocol autonomously self healed.
Should there be a case where RToken collateral defaults and the RSR overcollateralization pool is spent with net collateral at <100% of target price, the affected RToken holders receive proportional distribution rather than first come first served exit - this eliminates the bad debt without a hyperinflation event.

How do RTokens use volatile tokens like wBTC or ETH as collateral yet still maintain stability?
The portion of the basket that is wBTC or ETH or derivatives of them, will not be pegged to the dollar, and the RToken will inherit the respective volatility. This could be appealing for a small portion of a basket, maybe 2-5%. The downside is capped while the upside could be significant.

How can an RToken Deployer earn revenue?
Revenue distribution for RTokens is entirely flexible. From the revenue that is being accrued, any portion can be sent to any number of arbitrary Ethereum addresses, including the RToken deployer. Revenue share percentages are set when deploying the RToken and can only be changed by community governance.

What are the tokenomics of RSR?
RSR has a fixed total supply of 100 billion tokens, out of which there are currently 50.6b in circulation. The remaining 49.4b tokens belong to the Slow Wallet used to fund RToken adoption initiatives. To assure ample visibility, the community is alerted and the slow wallet has a hard-coded 4-week delay after initiating each withdrawal transaction on the blockchain.

What are the Reserve Protocol and RToken risks?
Reserve-specific risks include governance risk by RSR stakers, which can be mitigated by staking RSR, and smart contract risk on the Reserve Protocol.
Core DeFi risks include smart contract risks on reserve assets derived from other DeFi protocols such as Convex, Compound, and Aave. There may also be operational and custodian risks associated with centralized stakeholders such as Circle, Tether, and Ondo Finance. Finally, there is a collateral backing risk on underlying assets such as USDC, USDT, eUSD, MIM, stETH, rETH, ETH, and others.

What Reserve Protocol audits are available?
Trail of Bits: Report date: Aug 2022, review report: (link)
Solidified: Report date: Oct 2022, review report: (link)
Ackee: Report date: Oct 2022, review report: (link)
Halborn: Report date: Nov 2022, review report: (link)
Code4rena: Report date: Mar 2023, review report: (link)
