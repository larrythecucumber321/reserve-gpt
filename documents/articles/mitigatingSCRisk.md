Link: https://blog.reserve.org/mitigating-smart-contract-risk-d65d1182f11b
Title: Mitigating Smart Contract Risk

River
Reserve
River

·
Follow

Published in
Reserve

·
7 min read
·
Sep 12
2

Introduction
This is the second installment in Reserve’s Safety Series, the first of which can be viewed here. This installment will discuss how Reserve’s protocol team has worked to mitigate smart contract risk to help safeguard against security pitfalls to provide users greater peace of mind. It requires an understanding of RTokens, and we invite readers to learn about them here.

When developing asset-backed-currency software for permissionless RTokens — for the reasons explained in the first installment of this series — security is always on the mind of the development team. To contend with DeFi’s shifting landscape, Reserve implemented a rigorous and dynamic security process to improve the safety and dependability of its smart contracts.

Reserve contributors have done everything in their power to follow and exceed industry best practices. As discussed yesterday, DeFi is a pointless exercise if smart contracts cannot be relied upon. Let’s see how Reserve takes this to heart.

Open source code
Let’s start with low hanging fruit. Nearly every DeFi protocol has open source code. Reserve does, and invites users to visit the protocol’s GitHub and verify it. This is preferable to closed source code for a variety of reasons.

Open source code is verifiable by anyone. This means that a far more diverse group with different perspectives can examine potential flaws, resulting in more robust code. It also means that the code is monitored and scrutinized 24 hours a day, as opposed to if it were being reviewed simply by one organization in 8 hour shifts. This increases code security.

Some DeFi protocols prefer to avoid open-sourcing their code. This approach is called “security by obscurity”. Unfortunately, deployed code is potentially viewable using decompilers. This means that determined exploiters will be more familiar than security researchers due to the additional barrier this decompiling presents. This difficulty is the shaky basis behind security by obscurity.

Reserve does not agree with this approach, and encourages everyone to view the contracts themselves. The protocol’s transparency is its strength.

Testing and Code Coverage
Testing is crucial for smart contract development. Code coverage is a metric that measures the percentage of deployed code covered by test code. A higher code coverage result (a percentage) means more thorough testing, reducing the chances of unintended smart contract behavior.

Reserve Protocol has 93% code coverage, a level which Google describes as “exemplary”. As such, it is reasonable to argue Reserve’s test process leaves little room for unintended smart contract behavior.

Code coverage was run on https://github.com/reserve-protocol/protocol using solidity-coverage.

You can view the code coverage report here. Reserve’s code contributions follow an in-house style guide Reserve dovetails code coverage testing with “range-exhaustive” or “extreme” testing, which aims to test every line of code against even the most obscure scenarios. All in all, contributor efforts result in readable, resilient, and well-tested code.

Security Automation Tools & Process
The Reserve Protocol uses Echidna and Slither (tools built by auditing partner Trail of Bits), to perform fuzzing and static analysis, respectively. These tools are used throughout the development process and before all releases to meet Reserve’s standards.

Fuzzing aims to verify everything functions as desired — even under extreme circumstances. Reserve’s fuzzing settings are available here — contributors run 3 fuzzing scenarios that check for a total of 47 invariants.

Static analysis automatically finds vulnerabilities and possible optimizations. Reserve contributors provide oversight to this to maximize its effectiveness.

As the protocol’s understanding of secure development has matured, Reserve has also started to use Foundry which enables more targeted and faster fuzzing. This will increase the team’s capacity to locate edge case bugs when developing Reserve smart contracts.

Collaboration with Ethereum Security Community
Blockchain security is too complex to be handled by any one group of contributors. Fortunately, Ethereum has a world-class security community that Reserve has engaged with great success.

Let’s begin with how Reserve Protocol has engaged multiple leading security firms and undergone audits. These include:

Trail of Bits: Report date: Aug 2022, review report: (link)
Solidified: Report date: Oct 2022, review report: (link)
Ackee: Report date: Oct 2022, review report: (link)
Halborn: Report date: Nov 2022, review report: (link)
Code4rena: Report date: Mar 2023, review report: (link)
Something important to note with Code4rena is that their auditors are independent security researchers operating on a bounty basis. This makes their skillset extremely diverse and so it may find things formal auditors do not. The plurality of Code4rena’s auditors provides a perfect compliment to Reserve’s more formal audit partners.

The findings of these audits were all addressed pre-release. Looking forward, Reserve is going the extra mile by scheduling 2 additional audits (for this iteration of the protocol), acknowledging that no number of audits can guarantee absolute safety. This proactive approach demonstrates the protocol’s commitment to getting as close to a secure system as possible.

Reserve additionally offers a $5,000,000 Immunefi bug bounty (the third largest in bounty size at time of writing). This bug bounty is industry-leading, and presents a significant incentive to responsibly disclose any potential contract errors. This bug bounty is likely sufficiently high for an erring hacker to decide to contact Reserve, which is not necessarily true for all bug bounties.

This results in a smart-contract ecosystem that is tested, verified and designed to prevent loss.

Code4rena, one of the leading security organizations in DeFi, had this to say about Reserve’s approach to security:

“Reserve looks to be taking a ‘security by design’ approach, which we love to see. Instead of viewing audits as a quick win in achieving a ‘green tick’ for community goodwill, they’re doing multiple audits, at multiple stages in the development lifecycle, to increase the depth of security scrutiny into their codebase.”

Diversification of Smart Contract Exposure
RTokens require external assets. These external assets have inherent smart contract risk. RToken code is an additional layer of risk on top of this inherent external smart contract risk. While it may be true that the additional (or “stacked”) smart contract risk is lowered thanks to Reserve’s tight security procedures, trust in the underlying assets is necessary.

Since RTokens consist of many different tokens with many different smart contract systems, RTokens enjoy distributed smart contract exposure. This is known as horizontal contract diversification and it reduces the potential impact of a security breach on RToken holders. Traditionally, DeFi users rely on a single protocol — concentrating risk into one set of smart contracts.

Imagine a user who holds an RToken backed by diverse collateral. If a total security breach occurs in an asset that is 10% of the RToken’s collateral — say, a Curve LP position — the investor would only face a 10% loss.

Consider if the same investor had placed all their funds in one Curve LP and it bricked — their assets would be valueless. A superior and diversified risk profile is obtained using RTokens versus just one protocol asset. This potential loss is then further diminished by RSR staking, which will be touched on next.

All things being equal, the aggregate tolerated risk increase is potentially minor (drawing from RToken smart contract risk), but partial reliance on a number of different smart contract sources spreads this risk across multiple protocols. In doing so, Reserve offers users a more risk-diversified DeFi product, which diminishes potential losses.

Oracles
As it stands, the source of all RToken price feeds is Chainlink. Chainlink, a widely trusted oracle in DeFi, provides reliable pricing information of underlying collateral so that the protocol can accurately and reliably ensure that the RTokens in the system are adequately collateralized.

Chainlink feeds are industry standard and are trusted by leading ecosystem participants. RToken deployers choose Chainlink feeds for their assets because they are geographically decentralized, robust and well maintained.

Nevertheless, this is DeFi and occasional errors have occurred. In light of this, RTokens were designed to be “oracle-agnostic”, meaning that an RToken deployer can choose any type of oracle they please.

While Chainlink has been the only price feed used so far for RTokens, it does not mean that this will always be the case. This helps mitigate the risk of a single point of failure and increases the safety of the RToken system.

Conclusion
This chapter demonstrates Reserve’s commitment to security when developing smart contracts. Contributor actions reflect rigorous security measures and do so in the pursuit of reaching a trusted and reliable platform for creating asset-backed currencies. Note that all of these steps are taken with each iteration of the protocol, such as the upcoming 3.0.0 release. This process is continuous and never-ending.

If readers would like to discuss or get clarifications on how Reserve has worked to mitigate smart contract risk, the core team invites them to join Reserve’s Discord.

The next installment in this series will follow soon, and discusses how RTokens mitigate the risk of price depeg.
