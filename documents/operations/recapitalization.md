Link: https://reserve.org/protocol/protocol_operations/#recapitalization
Title: Recapitalization

Fully collateralized vs. fully funded
When we talk about recapitalization, we make a distinction between two states that an RToken can be in:

Fully collateralized: the protocol is holding the right balances of the right tokens to offer 100% RToken redeemability.
Fully funded: the protocol is holding the right amount of value, but not necessarily the right amounts of collateral to offer 100% RToken redeemability.
The Reserve Protocol aims to be fully collateralized at all times, but likely won’t always be. For example, right after governance decides to change the collateral basket, the protocol will be fully funded but won’t yet hold all the necessary collateral to offer full redeemability. Similarly, in the case of a collateral default, the protocol might be fully funded through excess collateral or RSR overcollateralization, but likely won’t yet be fully collateralized to offer full redeemability.

When the protocol is not fully collateralized, it will sell off any assets it is holding that are not part of the proper collateral basket until either (a) the protocol is fully collateralized again or (b) RSR from the stRSR contract needs to be sold to recapitalize the protocol.

Recapitalization through Reserve Rights
If any of an RToken’s collateral tokens were to default, the default flag would instantly be raised by the protocol through the default checking mechanisms explained in the Monetary Units section. At that point, the protocol will sell as much of the faulty collateral as it can through auctions and use the proceeds, as well as any excess collateral still in the system, to purchase the predefined emergency collateral (which you can read more about in the How to deploy an RToken section (coming soon)).

In the case that the proceeds of the auction(s) + any excess collateral still in the system do not provide enough value to fully collateralize the RToken with the emergency collateral, the protocol will attempt to recapitalize using RSR tokens staked in the stRSR contract. More concretely, the required amount of RSR tokens will be seized from the stRSR contract and sold for the required amount of emergency collateral through auctions—resulting in an even “haircut” for all RSR stakers.
