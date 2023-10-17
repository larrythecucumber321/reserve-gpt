Link: https://blog.reserve.org/reserve-protocol-v1-3-0-0-release-9c539334f771
Title: Reserve Protocol V1 — 3.0.0 Release

Streamlining Trades with Atomic Dutch Auctions
Larry the Cucumber
Reserve
Larry the Cucumber

Published in
Reserve

·
4 min read
·
Sep 20
10

We are thrilled to announce the 3.0.0 release of the Reserve Protocol V1. This release marks the protocol’s most expansive update to date, and delivers much anticipated enhancements to performance, security and developer engagement.

The Journey So Far
Release 1.0.0 was debuted in Bogota almost a year ago, which hailed the mainnet launch of the Reserve Protocol
Release 2.0.0 reached the All Clear milestone, after clearing extensive security audits and the community at large was invited to use the protocol
Release 2.1.0 was a minor release for bug fixes and performance improvements. eUSD upgraded from 2.0.0 through an on-chain proposal, demonstrating the decentralized upgradeability of RTokens
Owing to the modular design of the Reserve Protocol, existing RTokens can upgrade to and benefit from more frequent releases in ways that other DeFi protocols with calcified codebases might struggle (e.g. lack of compatibility between Uniswap V2 and V3).

Streamlining Trades with Dutch Auctions
Core to this update is the introduction of Dutch Auctions, designed to streamline protocol operations and enhance trader experience. This innovation improves on the current batch auction design by introducing atomic execution and improved slippage constraints, which together facilitate easier permissionless usage.

Dutch auctions start with a very high price which incrementally lowers until someone places a bid at a rate they’re satisfied with, concluding the auction. In traditional (batch) auctions, the price starts low and rises as multiple bidders compete to be the successful buyer — a much more uncertain process. Unsuccessful bidders in batch auctions are still required to spend gas to compete, whereas the competitive arena in Dutch auctions happens off-chain in mempools. This democratizes the auctions, enabling entry for more participants — likely resulting in better trade execution.

The beauty of this upgrade for Reserve is that it plugs RToken auctions (e.g. for revenue) into Ethereum’s MEV machinery, empowering searchers to more confidently automate protocol operations, to the benefit of all users.

Fortifying Security
Security is prime for Reserve. It remains a cornerstone in this release, evident in the following enhancements:

Elimination of “delegatecall” during rewards claiming. This imposes stricter security guidelines on community plugin developers and thwarts the possibility of malicious plugins being able to drain RToken funds. This involves the use of ERC20 wrappers which have the job of claiming rewards and forwarding them to the RToken. For example, Compound USDC will no longer be deposited into RTokens, but rather a wrapped version, which has logic for claiming COMP rewards
Introducing the notion of a “basket warmup” which acts as a safeguard against short-term oracle manipulation attacks, thus promoting safer RToken trading
The development team extends thanks to the Code4rena team and participating auditors for their thorough audit of the 3.0.0 release codebase. Find more details in the full report here.

Enhancing Developer Experience
The growing number of developers and protocols integrating RTokens can look forward to several quality-of-life improvements, including:

Historical Baskets: On-chain access to historical baskets of RTokens, providing a window into an RToken’s evolution

Asset Monitoring: Improved monitoring of underlying assets through the “lastRefresh” function, ensuring the RToken state remains current

Trading Experience: Providing finer-grain ability to interact with RToken trading actions, segregating the contract calls for rebalancing and revenue handling operations, and decreasing the overall number of required calls

Custom Redemptions: During RToken basket changes, RToken redemption prices remain higher thanks to being able to redeem assets in the same proportion as the percentage of rebalancing progress. Previously, if a redemption was made between 0% — 100% progress, a loss would be incurred

Empowering RToken Communities
The Reserve Protocol continues to facilitate the creation of robust on-chain DAOs governing asset-backed RTokens in the following ways:

New, more granular controls over the set of emergency governance roles and functions are also provided to foster greater decentralization within RToken communities. Specifically, emergency pauses are instituted on RToken trading and issuance individually, and the elevated Guardian and Owner roles are not automatically granted the ability to pause RToken systems.

Lastly, users will notice significant gas-saving benefits during stRSR withdrawals and gain the option to cancel stRSR unstaking. This will substantially reduce friction and increase user participation, thereby promoting RToken decentralization.

Ready for the Next Chapter
We invite you to explore the updated Reserve Protocol, a step forward in advancing the asset-backed currency movement. For existing RToken communities, upgrade steps are available here. See the full changelog of the 3.0.0 release here.
