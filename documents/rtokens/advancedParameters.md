Link: https://reserve.org/protocol/rtokens/#advanced-rtoken-parameters
Title: Advanced RToken parameters

When deploying an RToken, the deployer has the ability to configure many different advanced parameters. The following list goes into detail about what these parameters do and some of the factors the deployer should keep in mind to set them.

As many of these parameters concern the Protocol Operations, we advise reading through that section of the documentation first—as it will give the deployer the necessary context to fully understand all parameters.

Trading delay(s)
The trading delay defines how many seconds should pass after the basket has been changed before a trade can be opened.

A collateral asset can instantly default if one of the invariants of the underlying DeFi protocol breaks. If that would happen, and we would not apply a trading delay, the protocol would react instantly by opening an auction. This would give only auctionLength seconds for people to bid on the auction, making it very possible for the protocol to lose value due to slippage.

The trading delay parameter may only be needed in the early days - before we get to a point where there is a robust market of MEV searchers. We expect that this parameter can be set to zero later on (once a robust market of MEV searchers is established).

Default value: 21600 = 6 hours

Auction length(s)
The Reserve Protocol includes a generic trading system which can be integrated with any type of trading mechanism, but will only have an implementation for Gnosis EasyAuctions at-launch.

The auction length determines how long auctions stay open for. The situations to keep in mind when determining this value are:

If it is set too low, back-to-back auctions may not give arbitrageurs enough time to complete arbitrage loops that involve centralized exchanges. We don’t want capital-constrained traders to have to sit out every-other auction.
If it is set too high, fewer auctions will fill and the protocol will take more time holding the asset being sold. This is because the price can swing more than maximum trade slippage in the unfavorable direction.
Default value: 900 = 15 minutes

Backing buffer (%)
As collateral tokens appreciate, RTokens can be minted by the protocol whenever it gathers the correct ratios of all collateral tokens. This is the most efficient form of revenue capture, because it requires minimal trading of the excess collateral (and thus, a minimal spend on gas fees and trading slippage).

When the protocol is able to gather all the required parts of an RToken, these parts (collateral tokens) get sent to the RevenueTrader contract, where it performs an internal mint to create more RTokens. These new RTokens are then used as yield for both RToken holders and RSR stakers.

The backing buffer parameter is a percentage value that describes how much additional collateral tokens the protocol should hold on to before sending collateral tokens to the RevenueTraders. If this were set to “0”, then it’s possible (though unlikely) that collateral could “take turns” appreciating, causing the protocol to forward individual collateral tokens to the RevenueTraders and never assemble it into new RTokens.

Default value: 1e14 = 0.01%

Max trade slippage (%)
The maximum trade slippage is a percentage value that describes the maximum deviation from oracle prices that any trade that the protocol performs can clear at. Oracle prices have ranges of their own; the maximum trade slippage permits additional price movement beyond the worst-case oracle price.

Setting this percentage too high could cause the protocol to take high losses if auctions are illiquid.

Default value: 0.01e18 or 0.02e18 = 1/2%

Minimum trade volume
The minimum trade volume represents the smallest amount of value that is worth executing a trade for.

Setting this too high will result in auctions happening infrequently or the RToken taking a haircut when it cannot be sure it has enough staked RSR to succeed in rebalancing at par.

Setting this too low may allow griefers to delay important auctions. The variable should be set such that donations of size minTradeVolume would be worth delaying trading auctionLength seconds.

We expect auction bidders to pass-through any gas fees they pay during trading to the protocol. They are under competition, so those that do not will find themselves with less capital over time relative to those that do.

In order for the protocol not to take losses it’s important it knows that bidders will bid in the auction near market prices, which requires that gas prices are not significant relative to the volume of the auction.

Note: Every collateral in the basket should be a large enough portion of the basket that is worth trading at the configured minTradeVolume, even when we are only looking at 5% or 10% of its balance.

Default value: 1e22 = $10k

RToken Max trade volume
This represents the maximum sized trade for any trade involving RToken, in terms of value.

It is important to remark that in addition to the RToken, each collateral plugin will also have its own max trade volume defined.

Default value: 1e24 = $1M

RToken Supply Throttles
In order to restrict the system to organic patterns of behavior, we maintain two supply throttles, one for net issuance and one for net redemption.

When a supply change occurs, a check is performed to ensure this does not move the supply more than an acceptable range over a period; a period is fixed to be an hour.

The throttling mechanism works as a battery, where, after a large issuance/redemption, the limit recharges linearly to the defined maximum at a defined speed of recharge.

Limits can be defined (for issuance and redemption) in rToken amounts and/or as a percentage of the RToken supply.

Issuance Throttle Amount
A quantity of RToken that serves as a lower-bound for how much net issuance to allow per hour.

Defined in RToken amounts.

Must be at least 1 whole RToken. Can be set to a very high numer (e.g. 1e48) to effectively disable the issuance throttle.

Default value: 1e24 = 1,000,000 RToken

Issuance Throttle Rate (%)
A fraction of the RToken supply that indicates how much net issuance to allow per hour.

Can even be set to 0, to solely rely on throttle amount.

Default value: 5e16 = 5% per hour

Redemption Throttle Amount
A quantity of RToken that serves as a lower-bound for how much net redemption to allow per hour.

Defined in RToken amounts.

Must be at least 1 whole RToken. Can be set to a very high numer (e.g. 1e48) to effectively disable the redemption throttle.

Default value: 1e24 = 1,000,000 RToken

Redemption Throttle Rate (%)
A fraction of the RToken supply that indicates how much net redemption to allow per hour.

Can be 0 to solely rely on the throttle amount.

Default value: 2.5e16 = 2.5% per hour

Short freeze duration(s)
The number of seconds a short freeze lasts.

Governance can freeze forever.

Default value: 259200 = 3 days

Long freeze duration(s)
The number of seconds a long freeze lasts.

Long freezes can be disabled by removing all addresses associated to the role.

Default value: 2592000 = 30 days

Unstaking delay(s)
The unstaking delay is the number of seconds that all RSR unstakings must be delayed in order to account for stakers trying to frontrun defaults.

In the case of a collateral token default, RSR holders are not given a choice as to whether their RSR is used to cover the default, since selfish anonymous actors would often choose not to follow through. So, there must be a delay when withdrawing RSR from the staking contract.

In practice, whenever an RSR staker chooses to withdraw their RSR, they must submit a transaction, wait X amount of time, and then submit another transaction to complete the withdrawal. During the waiting period, their RSR continues to be subject to forfeiture in the case of a collateral token default, but stops earning its pro-rata share of the RToken’s revenue.

The goal of this delay is to make it so that at any point in time, staked RSR that has not had a withdrawal transaction initiated is at least X time away from being withdrawn.

Default value: 1209600 = 2 weeks

Reward ratio (decimals)
The reward ratio is the percentage of the current reward amount that should be handed out per block.

Default value: 3209014700000 = a half life of 30 days at a period of 12s.

Mainnet reasonable range: 1e11 to 1e13
