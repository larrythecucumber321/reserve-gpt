Link: https://reserve.org/protocol/reserve_rights_rsr/#staking
Title: RSR Staking

Reserve Rights (RSR) exists as an overcollateralization mechanism to protect RToken holders in the unlikely event of a collateral token default. In order for RSR holders to provide this overcollateralization, they can decide to stake on any one RToken, or divide their RSR tokens by staking on multiple RTokens. RSR holders can also decide not to stake their RSR at all.

In return for providing this overcollateralization, RSR stakers can expect to receive a portion of the revenue from the specific RToken that they stake on. As a general rule, RSR stakers can expect higher returns (APYs) as the market cap of the RToken they stake on increases.

When RSR is staked on an RToken, it's deposited into a staking contract specific to that RToken, and the staker receives a corresponding ERC-20 token, representing their staked RSR position on that particular RToken. This token is transferrable and fungible with other staked RSR balances for that RToken, so you can send any portion of the staked position to someone else or trade it, and the new holder can un-stake it if they choose to.

Staked RSR can earn rewards, based on three factors:

The amount of revenue the RToken generates
The portion of revenue that governance has directed to RSR stakers
Your portion of the total RSR staked on that RToken

As a simple example, suppose (these numbers are just made up for simplicity, to make the arithmetic clear):

A fictional RToken generated $100 in revenue in a period
20% of revenue was designated for RSR stakers
1000 total RSR was staked
You had staked 100 of the total 1000 RSR that is staked
In this simple example, you would get $100 _ 20% _ (100/1000) = $2 for that period.

The protocol stores revenue for a particular RToken in different ERC20s (including RTokens). When staking rewards are distributed, it market-buys RSR via auctions with these ERC20s and deposits it into the staking contract to distribute the rewards to RSR stakers. Thus, as rewards are earned, the exchange rate of staked RSR to RSR increases.

When RSR is staked, it is actually at stake. Staked RSR can be seized by the protocol in the event of a collateral token default, in order to cover losses for RToken holders. It's seized pro-rata if this happens.

Un-staking RSR comes with a delay, which is configurable by governance, and predicted to usually be between about 7 and 30 days. This delay is necessary so that in the event of a default, the staked RSR will remain in the staking contract for long enough to allow the RToken to seize any RSR it needs to cover losses.

During the unstaking delay period, the staker does not earn any rewards. This is necessary to prevent stakers from withdrawing and re-depositing over and over in order to subvert the withdrawal delay mechanism.

The easiest way to stake your RSR is to use a user interface that interacts with the Reserve Protocol smart contracts, such as Register. If you're looking for an easy tutorial on how to stake, please refer to this [article](https://blog.reserve.org/how-to-stake-your-rsr-on-an-rtoken-b39636f13e4b).
