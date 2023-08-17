Link: https://reserve.org/protocol/smart_contracts/#basket-dynamics
Title: Basket Dynamics

“Baskets” in the Reserve Protocol are arrays of financial values that the protocol references when keeping RTokens fully collateralized at all times. We differentiate between the following three types of baskets:

Prime basket: This is the target collateral basket at the onset of an RToken that defines which collateral needs to be deposited for issuances. The prime basket is directly set by governance, and only changes through successful governance proposals. It consists of an array of triples (<collateral token, target unit, target amount>) where each portion of the basket has a target amount of the target unit that should be represented by collateral token.

For example, if the prime basket contains the triple <cUSDC, USD, 0.33>, that means "The RToken should contain 0.33 USD per basket, as represented by cUSDC".

Reference basket: When the prime basket is updated by governance or in the case of a collateral default, the protocol will determine a new “Reference Basket” and then take certain actions (described in the Protocol Operations section) to change the collateral makeup until it matches the new basket. This new basket is called the reference basket and, like the prime basket, consists of a set of triples <collateral token, reference unit, reference amount>. Each triple means that each basket unit must contain an amount of collateral token currently equivalent to reference amount of the reference unit.

For example, if the reference basket contains the triple <aDAI, DAI, 0.33>, then one basket unit should contain whatever amount of aDAI is redeemable in its protocol for 0.33 DAI.

Collateral basket: the collateral basket is derived, moment-by-moment and on-demand, from the reference basket. Since DeFi redemption rates can change every transaction, so can the collateral basket. The collateral basket is a set of pairs <collateral token, token amount>. Each pair means that each basket unit must contain token amount of collateral token.

For example, if the reference basket contains the pair <cUSDC, O.29>, then one basket unit will contain 0.29 cUSDC.
