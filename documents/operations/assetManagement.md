Link: https://reserve.org/protocol/protocol_operations/#asset-management
Title: Asset Management

ERC20 assets that need to be used as part of an RToken system (either as collateral or as revenue assets) need to be registered in the Asset Registry contract for that particular RToken.

Governance is in charge of registering, unregistering, and swapping assets.

register: Adds the asset to the Asset Registry, including all the required details the protocol needs to handle that asset.
swapRegistered: Allows to modify/update details and functionality of a previously registered asset.
unregister: Removes the asset from the Asset Registry. It will no longer be used by the RToken system. The intended use of this function is for governance to remove bad collateral contracts. It is important that proposals that perform unregistration of assets should include at the end a call to refresh the basket (refreshBasket()).
A detailed list of non-compatible ERC20 assets is included in the RTokens section
