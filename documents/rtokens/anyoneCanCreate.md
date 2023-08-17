Link: https://reserve.org/protocol/rtokens/#anyone-can-create-an-rtoken
Title: Anyone can create an RToken

In a similar way as how anyone can create a new trading pair on Uniswap, anyone can permissionlessly create a new Reserve stablecoin (RToken) by interacting with Reserve Protocol’s smart contracts. The protocol applies a system of factory smart contracts that allows anyone to deploy their own smart contract instance.

Creating an RToken can be done either by interacting directly with the Reserve Protocol’s smart contracts or any user interface that gets built on top of it. The first user interface for these smart contracts is register.app released by LC Labs, a company connected to the Reserve core team that's helping with protocol development. Besides the creation of RTokens, this user interface will also support exploring usage and stats related to RTokens, RToken minting & redeeming, and [RSR staking](https://reserve.org/protocol/reserve_rights_rsr/#reserve-rights-staking).

The Reserve Protocol applies a system of factory smart contracts that allows anyone to deploy their own smart contract instance.

When someone decides to create an RToken, they will have to define exactly what the initial configuration of that RToken will look like. This includes choosing which ERC-20 assets & back-up assets the RToken will be backed by, what weight each of these assets will have in the basket, but also how and by whom the RToken will be governed. There are also many more nuanced parameters that the RToken creator will have to consider.
