Link: https://reserve.org/protocol/security/#reserve-protocol-risks
Title: Reserve Protocol Risks

This section is dedicated to explaining risks associated with using the Reserve Protocol. Whenever you interact with the Reserve Protocol, you as the user assume the risk of doing so. We believe that making best efforts to comprehensively outline risks creates accountability and empowers users. Any time you are uncertain about a particular risk, we invite you to ask on Discord.

We encourage all users to familiarize themselves with these risks and continually stay updated about changes that may affect the protocol.

Reserve Protocol Risks - Smart Contracts
The Reserve Protocol is built using smart contracts. If there were undiscovered bugs or vulnerabilities in these contracts, they could be exploited leading to loss of user funds. Although the protocol's contracts have undergone 6 (soon to be 7) security audits, no audit can guarantee complete security.

Smart contract-related risks can manifest in a variety of ways. A number of pertinent examples and categories are detailed below.

Oracle Risks
Reserve uses oracles to fetch real-time price data. If these oracles fail or deliver incorrect information, or if the usage of oracles on Reserve is otherwise incorrect, it could impact the protocol's ability to maintain accurate accounting and lead to other operational disruptions. For example, if Chainlink misreports the price of USDC, an RToken may consider a collateral asset to have defaulted and attempt to swap to emergency collateral, potentially at a loss.

Sandwich Attacks and MEV
MEV searchers are constantly scanning the Ethereum blockchain to look for profitable opportunities to extract value. When interacting with AMMs (such as Curve Finance for trading RTokens), users should exercise caution and consider the slippage, which dictates the degree to which searchers can extract from users’ transactions. There are other ways for users to independently seek MEV protection, such as through the Flashbots RPC.

Governance Risks
The Reserve Protocol team has deployed a suggested governance system for RTokens (Governor Alexios), which enables fully on-chain governance to RTokens. The scope of the powers are broad, so it is possible for governance attacks to happen. These potential attacks could involve an attacker accumulating enough governance power to enact a malicious upgrade allowing them to steal funds.

This type of attack is mitigated through the existence of special roles; however, these special roles must be wielded effectively and benevolently in order to offer meaningful protection. When using an RToken, it’s a good idea to familiarize yourself with who holds each of these special roles, which you can do on the Details + Roles page and the Governance page on Register (eUSD example: Details + Roles, Governance).

Collateral Asset Risks
Issuer/Custodian
It is possible for stablecoin (and other) issuers to impose restrictions on transferability, through blacklists. Although commonly intended to target sanctioned individuals, it is possible for these powers to extend to DeFi protocols. Additionally, stablecoin issuers are relied on for maintaining healthy reserves of real world assets. The strategies used to maintain these reserves may sometimes fail, or the custodians themselves may not always act in good faith. The best way we are aware of to familiarize yourself with the risks for any given underlying stablecoin is to review the report on that asset published on Bluechip, if they cover that asset.

Price
RTokens inherit the weighted price of all of their backing collateral assets. Where one or more underlying assets deviate in price (even where they are meant to be pegged), the aggregate price of the RToken will be affected. Fluctuations in RToken price should be anticipated where volatile collateral is present.

A slightly distinct price consideration involves that of the RSR overcollateralizing RTokens. Based on the amount of RSR that must be sold to re-collateralize a default, significant market movements may neutralize the effectiveness of the overcollateralization stemming from a weaker mark to market price.

Underlying Protocols
Reserve Protocol RTokens leverage assets from external protocols, like Compound, Aave, Flux, and many more. Users therefore assume all of the risks of these underlying protocols (smart contract, governance, or otherwise) when holding RTokens.

Reserve Protocol Risks - Interfaces
Front-end Operator Risks
The Reserve Protocol can be interacted with directly through its smart contracts, or through third party-created user interfaces. Register, for example, is run by a third party company, and has not yet undergone a technical audit. Users must always be vigilant for malicious or compromised frontends, such as in Badger’s case. Even in normal operation, bugs in front-end code may be responsible for requesting erroneous transactions which result in user losses.
