Link: https://blog.reserve.org/mitigating-counterparty-risk-9db235ade67e
Title: Mitigating Counterparty Risk

River
Reserve
River

·
Follow

Published in
Reserve

·
4 min read
·
Sep 14

This is the fourth installment in Reserve’s safety series. After previous pieces addressed how contributors have worked to mitigate both smart contract and depeg risk, this entry will focus on how Reserve protocol mitigates counterparty risk.

Reserve does this primarily by utilizing transparent and autonomous smart contracts. These contracts remove middlemen and enable users to verify public code, corroborate proof of reserves, and ensure that the protocol is operating as intended at all times. All these features make a case for RTokens to be safer stores of value than traditional assets, validating an RToken’s reduced risk profile.

Transparent smart contracts
Reserve is a fully onchain DeFi protocol. It is immutable and public. Active contracts are open sourced, and all transactions that occur can be verified using a block explorer such as Etherscan. Detailed technical documentation explains how the protocol functions and provides guidance on how to navigate system parameters.

The Reserve team went to great lengths to ensure that everything in the protocol is as transparent as possible, making every function performed fully traceable. This gives interested parties the ability to verify for themselves that the protocol does exactly what it was designed to do, independent of any third party interference. This means that RToken holders know what is going on behind the scenes in Reserve because they can view it onchain themselves.

This is in contrast to traditional financial infrastructure (including centralized exchanges). Let’s consider depositing money into a bank. The existing financial system has a track record for placing the money into where it is saying it is not. For example, a creditor cannot trace where their deposited assets have been loaned, which contributed to the catastrophic consequences of the 2008 financial crises. It also had demonstrably catastrophic consequences during the recent exchange blowup. Exchange leadership would have been unable to misuse customer funds had he been using public and verifiable smart contracts.

If the exchange was operating publicly onchain, alarm bells would have immediately been set off by numerous onchain monitoring organizations. The black box of their centralized exchange allowed the organization to obfuscate fund deployment for many months — obviously not a safe environment for custody of funds.

This man-in-the-middle attack risk is unwelcome and presents a barrier to the development of safe stable currency. It is an avoidable risk that has been accepted by traditional market participants unaccustomed to a more transparent alternative. Given that there are no man-in-the-middle issuers, custodians, or middlemen for RTokens, transparency becomes a critical feature of Reserve Protocol helping mitigate errors, deception and censorship.

Proof of Reserves Availability
RToken backing is always available for both verification and redemption — 24 hours a day. This is possible interacting directly with the Reserve protocol smart contracts or using the Register.app token explorer — for example see ETH+ RToken asset-backing here. With this simple ability, users do not need to hope a 3rd party stores their funds where they are instructed to. This is entirely handled by impartial computer code that acts in the way it is told.

Impartiality for proof of reserves brings considerable benefits. In a time of perceived crisis, should stressed users need to verify what an RToken is backed by, it is easy for them to do so. If they want to exit an RToken position, they can do so. They can even do so during times of actual crisis when the RToken is “frozen” (which is triggered under certain governance-predefined conditions).

All these benefits enabled by impartiality reduce the probability of RToken holders engaging in abrupt withdrawals from their RToken positions. This acts as a countermeasure against situations resembling bank runs — as detailed in Part 2. This system facilitates a system whereby a redemption from one RToken holder does not come at the expense of other RToken holders. Moreover, this mechanism aids in maintaining the stability of RToken prices, as users retain the option to liquidate their RToken positions at their discretion.

This trends to an ecosystem in which user funds are safe, verifiable and accessible at all times — a cornerstone of the RToken value offering.

Compare this to the lived experience of USDC holders during the SVB bank run crisis discussed in Part 2. They were unable to verify if USDC was indeed 1:1 backed by US dollars deposited into banks, and so a market formed with users betting against one another as to whether or not the “stablecoin” would return to peg. Many large positions were exited at discounts as high as 12% because participants were unsure if USDC would ever be backed again. Ultimately it did repeg, but this event is not acceptable for a currency that is supposed to be the backbone of a new financial system. This issue is even more pronounced when considering the notoriously non-transparent USDT. The absence of on-chain, verifiable reserves gives rise to numerous complications, rendering it an insecure choice for storing funds.

As an aside, astute readers will note eUSD’s backing is entirely USDC and USDT linked tokens. This is indeed a cause for concern. Thanks to overcollateralization mechanisms inherent (see the installment discussing this topic here) to RTokens, the market percieves these RToken backing concerns to be sufficiently mitigated — as proven by eUSD’s $20M market cap.

Conclusion
This installment has discussed how verifiable smart contracts & always available proof of Reserves bring RTokens significant benefits and trend to safety. If readers would like to discuss or get clarifications on how the protocol deals with counterparty risk, we invite you to join Reserve’s Discord.

In the next and final installment, we breakdown the different design choices made to mitigate onchain governance attacks other DAOs have unfortunately suffered.
