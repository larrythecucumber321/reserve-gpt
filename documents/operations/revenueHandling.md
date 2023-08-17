Link: https://reserve.org/protocol/protocol_operations/#revenue-handling
Title: Revenue Handling

Source of revenue
The revenue that RTokens accrue comes from their collateral baskets including tokenized outputs from DeFi protocols such as cUSDC (Compound USDC), aDAI (Aave DAI), or various AMM LP tokens. These tokens are designed to increase monotonically (ever-increasing) against their base tokens, as they are pegged to the value of the base token + any borrowing/trading fees paid in the relevant pool.

The protocol can track the appreciation of an RToken’s collateral tokens in USD terms, and decrement the redeemability for that RToken accordingly.

The protocol can track the appreciation of an RToken’s collateral tokens in USD terms, and decrement the redeemability for that RToken accordingly.
Revenue distribution
There are several components that are essential to understanding how RToken revenue is distributed to RToken holders or RSR stakers. In this section we will first introduce them one by one, and afterwards consolidate them to present the full picture.

Revenue distribution to RToken holders
After minting RTokens, all collateral tokens provided to the protocol will be stored in the Backing Manager (BM). The BM is responsible for holding on to them, minting more RTokens out of them, or trading them for RTokens or RSR (to later pay out rewards to RToken holders or RSR stakers).

For simplicity reasons, let’s first imagine an RToken X of which the revenue goes entirely to the RToken holders. The BM will periodically mint as many RTokens X as it can from the growing collateral. All the remaining grown collateral that can not be evenly minted into RTokens X will be sent to the RToken Trader, where it will be traded directly for more RTokens X through auctions.

After trading, both the newly minted RTokens X and the newly traded RTokens X will be consolidated in the Furnace. The Furnace is responsible for melting (= slowly burning) these new RTokens, which incrementally increases the exchange rate between the RToken and its collateral basket.

To summarize: the protocol will hold all collateral tokens in the Backing Manager. Whenever it can, it will mint new RTokens or trade excess collateral to RTokens via the RToken Trader. After minting/trading, the RTokens get melted (= slowly burned) via the Furnace—which results in the RToken becoming more valuable (redeemable for more collateral tokens).

The revenue distribution to RToken holders can be visualized as follows:

Revenue distribution to RSR stakers
As mentioned in the previous section, all deposited collateral tokens for an RToken will be stored in the Backing Manager (BM). The BM is responsible for holding on to them, minting more RTokens out of them, or trading them for RTokens or RSR (to later pay out rewards to RToken holders or RSR stakers).

For simplicity, let's now imagine an RToken Y of which the revenue goes entirely to the RSR stakers to compensate them for overcollateralization & governance. In this case, the BM will periodically mint as many RTokens Y as it can from the growing collateral. After this periodical mint, the newly minted RTokens and all the remaining grown collateral that could not be evenly minted into RTokens Y, will be sent to the RSR Trader, where it will be traded directly for more RSR tokens through auctions.

After trading, the protocol will send all the newly acquired RSR to the stRSR pool, where it will slowly be drip out as rewards for the RSR stakers by increasing the stRSR/RSR exchange rate.

To summarize: the protocol will hold all collateral tokens in the Backing Manager. Whenever it can, it will trade excess collateral to RSR via the RSR Trader. After trading, the RSR get slowly handed out via the stRSR pool—which results in stRSR becoming more valuable (redeemable for more RSR tokens).

The revenue distribution to RSR stakers can be visualized as follows:

Summary of revenue distribution
The previous two sections explain how the revenue (growing collateral) of an RToken gets distributed to either RToken holders or RSR stakers via minting/trading (for) RTokens or RSR tokens. In this section we combine the two approaches to present the full picture of revenue distribution.

When deploying an RToken, the deployer defines what portion of the revenue goes to the RToken holders versus RSR stakers. Let’s now imagine an RToken Z where 40% of the revenue goes to RToken holders and 60% goes to the RSR stakers.

In that case, the protocol will periodically take the following actions:

Out of 40% of all the revenue accrued in the Backing Manager at that point, the protocol will mint as many RTokens Z as it can. The remainder of the collateral (out of which no new RTokens Z can be minted) will be sent to the RToken Trader, where it will be traded directly for RTokens Z. Afterwards, all newly minted/traded RTokens Z will consolidate in the Furnace, where they will be melted (= slowly burned)—thereby positively impacting the exchange rate of RToken Z to its collateral.
Out of 60% of all the revenue accrued in the Backing Manager at that point, the protocol will mint as many RTokens Z as it can. The newly minted tokens, as well as the remainder of the collateral (out of which no new RTokens Z could be minted) will be sent to the RSR Trader, where it will be traded directly for RSR tokens. Afterwards, all newly acquired RSR tokens will be sent to the stRSR pool, where they will slowly be handed out to stRSR holders—thereby positively impacting the exchange rate of stRSR to RSR.
The full picture of revenue distribution can be visualized as follows:

💡 Reserve Protocol can be configured to send (part of the) revenue of an RToken to any arbitrary Ethereum address (e.g. to compensate the RToken deployer, to build an RToken treasury, etc). In this configuration, the RToken deployer can decide whether to pay out the third-party address in RTokens or RSR. In either case, the part of the revenue designated to the third-party address can be sent to it directly from the RToken Trader or the RSR Trader—it does not have to go through the Furnace or stRSR pool first.
