Link: https://reserve.org/protocol/protocol_operations/#auctions
Title: Auctions

Auctions are employed any time an asset within the RToken system is traded for another asset. Possible scenarios include (1) processing RToken revenue and (2) recollateralization following a basket change or a collateral default. In general, the Reserve Protocol supports any generic trading system, but at present, the protocol provides support for two auction implementations:

1. Dutch Auctions
2. Batch Auctions

It is anticipated that Dutch auctions will be the preferred trading method, with a fallback to batch auctions being available in scenarios where it is suspected that manipulation has occurred and a more manual trading process is warranted.

Dutch Auctions
A Dutch auction is a type of auction where the item on sale starts at a high price, with the price lowering gradually until a buyer accepts the current price. This process continues until either the product is sold or it reaches a preset minimum price. Dutch auctions facilitate quick price discovery without bidding wars.

The expected price is based on a number of different inputs, including oracle price feeds, exchange-rates sourced from smart contracts, and other collateral-specific values.

The Reserve Protocol's implementation of Dutch auctions utilizes a 4-phase price reduction mechanism which safeguards against potential price manipulations and which accommodates natural price fluctuations which might occur during the course of the auction. The auction phases are as follows:

The auctioned asset declines from 1000x of its expected price down to 1.5x. Bids are not expected during this period, and serves as a safeguard against price manipulation
The asset falls from 1.5x its expected price down to 1x the expected price. This stage acknowledges the potential for natural price movements during the auction
The asset declines from its expected price to its worst possible price, accounting for oracle errors and the max trade slippage parameter. This is where most bids are expected to occur
The price remains static at the worst price providing an opportunity for manual human bidding in the absence of bots
A Dutch Auction completes when a user places a bid (full-lot bids are required), or when the auction time runs out and a user chooses to close out the auction with no bids. At this point either a new Dutch Auction or Batch Auction can be run for the same assets.

Batch Auctions
Reserve relies on Gnosis' Easy Auction for its implementation of batch auctions. Batch auctions are a market mechanism for matching limit orders of buyers and sellers of a particular good with one fair clearing price. The auction works by fulfilling the entire "batch" of bids which are above an acceptable minimum price and which satisfies the number of assets they wish to sell. Take for example where 10 tokens X are being sold. Bidder A places an order to buy 5 tokens at $10/token, Bidder B places an order to buy 4 tokens at $9/token, and Bidder C places an order to buy 4 tokens at $5/token. Bidders A and B receive 5 and 4 tokens while Bidder C receives 1 token, and all bids clear at $5/token.
