Link: https://reserve.org/protocol/smart_contracts/#system-states-and-roles
Title: System States and Roles

Reserve Protocol contains five core governance roles that any governance smart contract can easily integrate in order to create new governance systems for RTokens:

OWNER: the top level decision maker, typically a decentralized governance smart contract, responsible for setting or updating all RToken parameter values, RToken baskets, etc. - The RToken OWNER has the power to:
grant and revoke roles to any Ethereum account
pause and unpause the system
freeze and unfreeze the system
set governance parameters
upgrade system contracts
PAUSER: has the ability to pause and unpause an RToken’s system. The PAUSER role should be assigned to an address that is able to act quickly in response to off-chain events, such as a Chainlink feed failing. It is ok to have multiple pausers. It can be robot-controlled. It can also consist of a 1-of-N multisig for high availability and coverage. It is acceptable for there to be false positives, since redemption remains enabled. See the table below for more information on what exactly a “pause” of an RToken means.
SHORT_FREEZER: has the ability to freeze an RToken’s system for a short period of time. The SHORT_FREEZER role should be assigned to an address that might reasonably be expected to be the first to detect a bug in the code and can act quickly, and with some tolerance for false positives, though less than in pausing. It is acceptable to have multiple short freezers. It can be robot-controlled. It can also consist of a 1-of-N multisig for high availability and coverage. If a bug is detected, a short freeze can be triggered which will automatically expire if it is not renewed by LONG_FREEZER.
When the SHORT_FREEZER call freezeShort(), they relinquish their SHORT_FREEZER role, and can only be re-granted the role by the OWNER (governance). The OWNER may also step in and unfreeze at any time.
LONG_FREEZER: has the ability to freeze an RToken’s system for a long period of time. The LONG_FREEZER role should be assigned to an address that will highly optimize for no false positives. It is much longer than the short freeze. It can act slowly and needs to be trusted. It is probably expected to have only one long-freezer address. It allows only 6x uses per long-freezer. It exists so that in the case of a zero-day exploit, governance can act before the system unfreezes and resumes functioning.
When the LONG_FREEZER calls freezeLong(), they spend a “charge”. A LONG_FREEZER starts with 6 charges, and when they run out of charges they relinquish the LONG_FREEZER role. Only the OWNER can re-grant the role or top up an accounts charges.
GUARDIAN: has the ability to reject proposals even if they pass. Should be assigned to a multisig or EOA that can be trusted to act as a backstop. It is acceptable if it is relatively slow to act. Only one guardian address should be defined.
💡 While Reserve Protocol is a fully open system that allows the integration of any custom governance smart contract for RTokens, the Reserve team has deployed a recommended governance system that will be suggested to RToken deployers. If you’re interested in reading about its details, please refer to the Governor Alexios.

The roles mentioned above each have the ability to put their RToken’s system in specific non fully functional states in the case of an attack, exploit, or bug. These states are:

Paused: when an RToken’s system is paused, all interactions besides redemption, ERC20 functions, staking of RSR, and rewards payout are disabled. An RToken’s system can be paused by any of the Pauser addresses calling pause() and resumed by calling unpause().
Frozen: when an RToken’s system is frozen, all interactions besides ERC20 functions and staking of RSR are disabled. An RToken’s system can be short-frozen by any of the SHORT_FREEZER addresses calling shortfreeze(). This freeze can be extended by any of the LONG_FREEZER addresses calling longfreeze(), or can be resumed by the SHORT_FREEZER or OWNER addresses by calling unfreeze().
