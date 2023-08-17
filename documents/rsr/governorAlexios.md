Link: https://reserve.org/protocol/reserve_rights_rsr/#governor-alexios
Title: Governor Alexios

The Reserve team has deployed a recommended governance system for RTokens (Reserve Governor Alexios) that will be suggested to RToken deployers by default. This governance system is a slightly modified version of the OpenZeppelin Governor.

Governor Alexios allows RSR holders to participate in the decision-making process of the protocol by proposing, voting on, and executing proposals. It follows a delegation system where RSR holders can delegate their voting power to other addresses. This enables efficient participation in the decision-making process and increases voter turnout.

The governance process is divided into three sub-phases:

Proposal: Proposals can include changes to the protocol's parameters, new feature implementations, or anything else that requires the approval of RSR holders. Proposals can be created by anyone who holds the minimum required amount of tokens.
Vote: A vote is a decision made by a token holder on a proposal. Votes can be cast in favor, against, or abstain. Token holders can also delegate their voting power to another address to vote on their behalf.
Execution: Once a proposal has been approved, it can be executed to perform the intended action.
A timelock component is introduced once a proposal is approved. This adds a configurable delay between the approval of a proposal and its execution, which allows RToken holders to make a decision before something is changed.

The following parameters can be configured for the governance process:

Proposal Threshold: The minimum voting weight required to create a proposal.
Quorum: The minimum total voting weight required to consider a voting valid.
Voting snapshot delay: The time to stake between the proposal is created and the snapshot of voting weights is taken.
Voting period: The duration of the voting period for each proposal.
Execution delay: The delay before a successful vote is executed. Provides time to RToken holders to make a decision before changes are applied.
By default, the end-to-end process for approving & executing proposals is 8 days:

Voting snapshot delay: 2 days
Voting period: 3 days
Execution delay: 3 days
Within RSR Governor, each RToken can have different roles assigned to it—the Pauser, the Short Freezer, the Long Freezer, and the Guardian—which can be given to any Ethereum addresses by the RToken deployer/owner. Each have the ability to put their RToken’s system into certain states in the case of an attack, exploit, or bug. These states are:

Paused: when an RToken’s system is paused, all interactions besides redemption, ERC20 functions, staking of RSR, and rewards payout are disabled.
Frozen: when an RToken’s system is frozen, all interactions besides ERC20 functions and staking of RSR are disabled.
For additional information, please refer to the [System States + roles section](https://reserve.org/protocol/smart_contracts/#system-states-and-roles).
