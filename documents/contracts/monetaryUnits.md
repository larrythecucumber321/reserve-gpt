Link: https://reserve.org/protocol/smart_contracts/#some-monetary-units
Title: Monetary Units

Reserve Protocol refers to units of financial value in a handful of different ways, and treats them as different dimensions. Some of these distinctions may seem like splitting hairs if you're just thinking about one or two example RTokens, but the differences are crucial to understanding how the protocol works in a wide variety of different settings.

The following are the three main financial units that apply to the protocol:

Unit of Account: any particular RToken must have a single Unit of Account. This unit is used internally to compare the values of different assets, as when deciding when there's enough revenue to start an auction, or in which of several surplus assets we hold the largest surplus.

By default, the unit of account for all RTokens is USD. As this financial unit is mostly for internal calculations (such as converting price feeds), there is no reason for an RToken deployer to change it—it is therefore also not an RToken parameter.

Target unit: each collateral token in an RToken basket is expected to generally be stable or appreciating against some exogenous currency. The exogenous currency is that collateral's target unit. We expect that in many RTokens that people actually want, all of those target units will be the same, and we can speak of the RToken maintaining stability or appreciation against its target unit.

Reference unit: when collateral tokens are expected to appreciate, it's generally because some DeFi protocol produces a “receipt token” that is freely redeemable for some base token, the redemption rate of which is expected to monotonically increase over time. That base token is the reference unit for the collateral token.

A couple examples:

For a Compound collateral token such as cUSDC, the unit of account is USD, the reference unit USDC and target unit USD.
For an Aave collateral token such as aUSDP, the unit of account is USD, the reference token USDP and target unit USD.
Let's say we're building a pure-stable USD basket, out of USDC, USDP, and DAI. The unit of account would surely be USD. Each collateral token would also be its own reference unit, and their target units would be USD.
Reserve Protocol expects collateral tokens (e.g. cUSDC) to be in a known, predictable relationship with the reference units (e.g. USDC), and the reference units to be in a known, predictable relationship with the target units (e.g. USD) and will flag the collateral token as defaulting if any of these relationships appear to be broken.
