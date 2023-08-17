Link: https://reserve.org/protocol/protocol_operations/#staking-and-un-staking
Title: Staking & un-staking

Reserve Rights (RSR) holders can decide to stake their RSR tokens on RTokens to make RToken holders whole in the unlikely event of a collateral token default, and receive a portion of the revenue the RToken makes in return.

This section will go into more detail about the low-level aspects of RSR staking. For a more high-level description, please refer to the Reserve Rights Staking section.

Right after staking RSR tokens on an RToken, the staker receives a stRSR (staked Reserve Rights) token at a particular exchange rate to RSR. This exchange rate starts at 1.00 and will change over time—either by RToken revenue being shared to the RSR stakers, or through overcollateralization slashing.

To participate and vote in Governance proposals, stakers need to delegate their stakes to themselves to activate their voting weight.

If an RSR staker decides to un-stake their RSR tokens, they’ll have to wait the un-staking delay (by default set to 2 weeks) before receiving their RSR tokens back. While in the delay period, the stRSR to RSR exchange rate is locked (the staker is no longer accumulating revenue from the RToken). However, the RSR is still liable to be slashed in the case of a collateral default.

The reason for a stRSR position needing to be slashable, but not earning revenue, during the un-staking delay period is because the alternative would allow for gaming of the system. If revenue was still being accumulated during the delay period, one could immediately un-stake after staking their RSR (and repeat this process) to circumvent the delay period—ultimately resulting in a less consistent overcollateralization pool.

Un-staking a stRSR position requires two transactions, one to initiate the un-staking process and one at the end of the delay period to receive the RSR tokens back. In between these two transactions the stRSR position is not transferable, as stRSR gets burned upon the first transaction).
