Link: https://blog.reserve.org/comprehensive-risk-mitigation-at-reserve-protocol-68a724e9989e
Title: Comprehensive Risk Mitigation at Reserve Protocol

River
Reserve
River

·
Follow

Published in
Reserve

·
23 min read
·
Sep 28

Preface
As economist John Allen Paulos said, “uncertainty is the only certainty”. This is especially true in DeFi. Spend some time to understand Reserve’s security philosophy, and learn the steps it has taken to ensure the protocol is as robust as possible.

Safety at Reserve is an enduring, timeless process. This edition is the total written version which contains all parts previously shared on Medium in one place. It is long. The length of this series is testament to how seriously core developers take security and it represents a fraction of the actual work that goes into securing Reserve.

This series’s purpose is that the community be left with a keen awareness of the primacy of secure and safe development to Reserve. See the table contents below to assist navigation.

Note that this series requires some understanding of what an RToken is. To quickly familiarize yourself, watch this video.

Table of Contents
To quickly jump to a relevant section, please see the following sections.

Part 1: Why Care About Safety?

Part 2: Mitigating Smart Contract Risk

Part 3: Mitigating Depeg Risk

Part 4: Mitigating Counterparty Risk

Part 5: Mitigating Governance Risk

Part 1: Why Care About Safety?
Risk and risk management is key to investment strategy. Risk stems from uncertainty: decision makers face the challenge of maximizing ROI while navigating a changing market. Both risk and risk management are prerequisites for strong portfolio returns. To be blunt, participants cannot profit in DeFi without strong risk management and even then still stand a good chance of losing everything.

Crypto portfolio management is relatively new. While the objective remains much the same as traditional asset management, a crypto-native risk management approach differs due to novel hazards inherent to DeFi. Crypto portfolio managers have to navigate concepts unique to DeFi: smart contracts, tokenomics, governance frameworks and so on.

DeFi’s unique nature creates complexities in risk assessment, resulting in an industry-specific risk-reward profile. DeFi also offers the potential for significant returns, often surpassing traditional finance benchmarks.

Nevertheless, the risks associated with DeFi are clear with billions of dollars in capital losses between retail and institutional investors alike. Some memorable (forgettable) moments from the past year include the Wormhole bridge getting hacked for $326 million, Euler Finance being exploited for over $200 million — lest the memory of Terra Luna‘s catastrophic collapse is forgotten. Not only do users in DeFi have to contend with often poorly designed economic systems, they also have to factor in the chance there will be a total irretrievable loss of funds — which is less common in traditional finance.

These risks are known and substantial effort has been put into finding solutions. For example, a smart contract audit has become a mainstay for any project and attracting significant TVL without one is challenging.

Demand for audits is an improvement in DeFi — it definitely decreases risk. Unfortunately, for some projects, having one has become a meaningless rubber stamp. These projects assume that one audit proves their contracts are bulletproof. The project then markets itself as “safe” upon audit completion. This is confusing at best and deceptive at worst: no amount of auditing can make a project completely safe.

Given the complex nature of DeFi protocols, one audit is rarely comprehensive and vulnerabilities are missed by teams of the best auditors. While (multiple) audits are necessary, they are not enough.

Despite other important guards such as bug bounties, multi signature wallets, insurance and so on, it is clear that current security efforts industry-wide have largely fallen short. Serious losses have stained DeFi’s reputation and continue to dissuade capital allocators. Due to this polarized risk-reward dichotomy, risk mitigation has become a cornerstone of DeFi.

While savvy DeFi funds have already developed risk frameworks to deploy capital at scale, more is needed to bolster returns and protect against black swan events. This could be a key catalyst for follow-on investment.

In this piece, contributors introduce a framework for understanding how the Reserve Protocol grapples with the many threat vectors plaguing DeFi and how it designed a system which counteracts these risks.

Contributors hope this framework will be used by DeFi investors and projects to not only better gauge DeFi risks but also drive future research, discovery and innovation in this space. The piece contains the following sections:

Mitigating Smart Contract Risk: how Reserve navigates smart contract risk through design and system testing, audits and other tools.

Mitigating Depeg Risk: how Reserve counteracts depeg risk through diversified asset-backing and an overcollateralization system.

Mitigating Counterparty Risk: how the protocol mitigates counterparty risk by utilizing transparent and autonomous smart contracts that removes middlemen and enables users to verify public code.

Mitigating Governance Risk: how the Reserve Protocol has implemented robust blunting strategies against governance attack vectors.

Let’s begin with how Reserve has worked to mitigate smart contract risk!

Part 2: Mitigating Smart Contract Risk
TL;DR
Reserve mitigates smart contract risk in the following ways

Open-source code which fosters transparency and scrutiny
Thorough testing with 93% code coverage minimizing unintended behavior
Automation tools such Echidna and Slither reinforcing the above
Five independent audits including Code4rena and Halborn
An industry leading $5 million ImmuneFi security bug bounty

---

When developing asset-backed-currency software for permissionless RTokens — for the reasons just outlined — security is always on the mind of contributors. To contend with DeFi’s evolving landscape, Reserve implemented a rigorous and dynamic security process to improve the safety and dependability of its smart contracts.

This section explains Reserve’s smart-contract-specific practices. Each of these practices helps safeguard against security pitfalls to provide users greater peace of mind.

Reserve contributors have done everything in their power to follow and exceed industry best practices. As discussed above, DeFi is a pointless exercise if smart contracts cannot be relied upon. Let’s see how Reserve takes this to heart.

Open source code
Let’s start with low hanging fruit. Nearly every DeFi protocol has open source code. Reserve does, and invites users to visit the protocol’s GitHub and verify it. This is preferable to closed source code for a variety of reasons.

Open source code is verifiable by anyone. This means that a far more diverse group with different eyes can examine potential flaws, resulting in more robust code. It also means that the code is monitored and scrutinized 24 hours a day, as opposed to if it were being reviewed simply by one organization in 8 hour work shifts. This increases code security.

Some DeFi protocols prefer to avoid open-sourcing their code. This approach is called “security by obscurity”. Unfortunately, deployed code is potentially viewable using decompilers. This means that determined exploiters will be more familiar than security researchers due to the additional barrier this presents. This is the shaky basis behind security.

Reserve does not agree with this approach, and encourages everyone to view the contracts themselves. The protocol’s transparency is its strength.

Testing and Code Coverage
Testing is crucial for smart contract development. Code coverage is a metric that measures the percentage of deployed code covered by test code. A higher code coverage result (a percentage) means more thorough testing, reducing the chances of unintended smart contract behavior.

Reserve Protocol has 93% code coverage, a level which Google describes as “exemplary”. As such, it is reasonable to argue Reserve’s test process leaves little room for unintended smart contract behavior.

Code coverage was run on https://github.com/reserve-protocol/protocol using solidity-coverage.

You can view the code coverage report here. Reserve’s code contributions follow an in-house style guide Reserve dovetails code coverage testing with “range-exhaustive” or “extreme” testing, which aims to test every line of code against even the most obscure scenarios. All in all, contributor efforts result in readable, resilient, and well-tested code.

Security Automation Tools & Process
The Reserve Protocol uses Echidna and Slither (tools built by auditing partner Trail of Bits), to perform fuzzing and static analysis, respectively. These tools are used throughout the development process and before all releases to meet Reserve’s standards.

Fuzzing aims to verify everything functions as desired — even under extreme circumstances. Reserve’s fuzzing settings are available here — contributors run 3 fuzzing scenarios that check for a total of 47 invariants.

Static analysis automatically finds vulnerabilities and possible optimizations. Reserve contributors provide oversight to this, to maximize its effectiveness.

As the protocol’s understanding of secure development has matured, Reserve has also started to use Foundry, which enables more targeted and faster fuzzing. This will increase the team’s capacity to locate edge cases when developing Reserve smart contracts.

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

Reserve looks to be taking a ‘security by design’ approach, which we love to see. Instead of viewing audits as a quick win in achieving a ‘green tick’ for community goodwill, they’re doing multiple audits, at multiple stages in the development lifecycle, to increase the depth of security scrutiny into their codebase.”

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

Part 3: Mitigating Depeg Risk
TL;DR
Reserve mitigates depeg risk using these techniques:

Having onchain 1:1 diverse asset backing for RTokens
RSR staking overcollateralization
Permissionless minting and redemption, creating profitable arbitrage opportunities to maintain RToken pegs
Anti-bank run mechanisms, such as predictable reserves with proportional distribution

---

After introducing this piece and explaining how the protocol mitigates smart contract risk, allow contributors the opportunity to explain how RTokens differ in design from existing stablecoins and thus are not as susceptible to depegging.

Last year, Terra collapsed due to a design (flaw) that depegged its UST stablecoin. Since the UST stablecoin was backed endogenously (i.e. by an asset that’s value was tied to UST), unstoppable panic selling ensued once the depeg began. In the end, the entire protocol crumbled and the crisis erased billions from the market.

More recently, USDC, considered the most reputable stablecoin, fell victim to depeg following the Silicon Valley Bank bankruptcy. While it eventually returned to peg, the lack of transparency during the event caused mass panic leading to a similar bank run scenario. Since then, the demand for USDC is down 35%+, illustrating lower confidence in Circle.

This section examines how Reserve Protocol reduces depeg risk and discusses the features that allow the protocol to remain resilient in times of extreme volatility.

Let’s start with how permissionless and transparent protocol operations allow RTokens to resist bank runs and maintain peg.

Redeemability
The RToken peg is maintained by allowing full minting and redeeming for the underlying collateral onchain. RTokens are always backed 1:1 with collateral under regular conditions. Should the price of the RToken in the secondary market deviate from the value of collateral, there is an arbitrage opportunity. Participants looking to restore the peg can redeem the RToken to claim the underlying assets (or vice versa) and profit. This incentivizes a strong 1:1 peg.

Redeemability has another purpose: reducing uncertainty. Uncertainty arises when people can’t verify if their money is actually accessible. However, with Reserve, users can easily check the collateral supporting any RToken and verify that it is adequately backed — more on this in next installment.

To maintain the peg, RToken redemptions are completely permissionless and always fully available. Nevertheless, it is possible that RToken collateral itself may cause the RToken peg to break. To address this, Reserve is designed with another feature: diversification of collateral backing. Instead of relying on a single asset, RTokens accept a variety of collateral types, which reduces the surface area risk associated with any one collateral failing.

This feature gains its strength from diversification and guards against cratering asset value.

Overcollateralization
The second feature that reduces depeg risk is staked RSR overcollateralization, which exists as a mechanism to keep RToken holders whole in the event of a collateral token default.

RSR holders can decide to stake RSR on any one or multiple RTokens. These RSR stakers receive a portion of the revenue from the RToken that they chose to overcollateralize. For example, High Yield USD (hyUSD) stakers earn 16% (at time of writing) of the yield generated by the token.

Should (any) one of the assets in the RToken basket lose its value, the protocol would initially sell all “faulty” collateral for pre-determined emergency collateral. If there is still a shortfall in the value of the backing, it would then seize staked RSR from those who staked on the affected RToken and use it to buy enough emergency collateral to fill the hole.

This mechanism was put to the test during the USDC depeg earlier this year, when Electronic Dollar (eUSD), an RToken, successfully returned to peg days before USDC did. This system passed its first test with flying colors. Indeed, the stakers whose capital was sold off to recapitalize eUSD have also been made whole by this point too. RTokens overcollateralization has been tested and has proven to work both functionally and economically.

In the event an RToken remains undercollateralized even after seizing and selling all staked RSR, the affected RToken holders can redeem their RTokens for a proportional distribution of backing collateral rather than first-come-first-served exit. This is novel in DeFi and reduces the impact of issues experienced by debt protocols. In implementing this, Reserve is protecting user funds and boosting safety.

These two features work in tandem to actually penalize RToken panic redeemers. If they wait for the RSR auction, they will be made whole. If the auction is insufficient to repeg the RToken, then the proportional distribution system will result in a higher return than a panic dump. This is the sort of intentional and innovative mechanism design that Reserve contributors spend months considering.

Mitigating bank-runs
This double system of penalizing panic sellers and RToken overcollateralization acts as an “anti-bank-run” mechanism. To begin, these tokens are redeemable for hard (i.e. exogenous) collateral, which prevents a rush of RToken holders to avoid being the last one with deposits left in the protocol. It is impossible to be left with an unbacked RToken in this way. The proof of reserves for this collateral is always verifiable onchain and is overcollateralized by the RSR staking mechanism.

Should the overcollateralization not fully recapitalize the RToken, those looking to receive the hard collateral underlying the RToken will only be able to do so proportionally (as opposed to first come first serve, which is the norm in DeFi). All of these features reduce the chance of a bank run occurring in the first place, and should it come to that then there is no incentive to get your collateral out of the RToken earlier. Excluding a hyperinflation event, the likelihood of a bank run occurring on an RToken is extremely low.

For an example of a protocol that did not prevent the negative consequences of a bank run, see Iron Finance. Reserve’s careful design and intentional development has gone some way to make this event significantly less likely to happen to RTokens.

Part 4: Mitigating Counterparty Risk
TL;DR
Reserve Protocol mitigates counterparty risk through

Autonomous smart contracts enabling verification of protocol activity and eliminating the need for error-prone or censoring middlemen
Transparent onchain proof of reserves helping users verify RToken backing

---

This is the third part in Reserve’s Safety series. This entry will focus on how Reserve protocol mitigates counterparty risk. It does this primarily by utilizing transparent and autonomous smart contracts. These contracts remove middlemen and enable users to verify public code, corroborate proof of reserves, and ensure that the protocol is operating as intended at all times. All these features make a case for RTokens to be safer stores of value than traditional assets, validating an RToken’s reduced risk profile.

Transparent smart contracts
Reserve is a fully onchain DeFi protocol. It is immutable and public. Active contracts are open sourced, and all transactions that occur can be verified using a block explorer such as Etherscan. Detailed technical documentation explains how the protocol functions and provides guidance on how to navigate system parameters. The Reserve team went to great lengths to ensure that everything in the protocol is as transparent as possible, making every function performed fully traceable. This gives interested parties the ability to verify for themselves that the protocol does exactly what it was designed to do, independent of any third party interference. This means that RToken holders know what is going on behind the scenes in Reserve because they can view it onchain themselves.

This is in contrast to traditional financial infrastructure (including centralized exchanges). Let’s consider depositing money into a bank. The existing financial system has a track record for placing the money into where it is saying it is not. For example, a creditor cannot trace where their deposited assets have been loaned, which contributed to the catastrophic consequences of the 2008 financial crises. It also had demonstrably catastrophic consequences during the recent exchange blowup. Exchange leadership would have been unable to misuse customer funds had he been using public and verifiable smart contracts. If the exchange was operating publicly onchain, alarm bells would have immediately been set off by numerous onchain monitoring organizations. The black box of their centralized exchange allowed the organization to obfuscate fund deployment for many months — obviously not a safe environment for custody of funds.

This man-in-the-middle attack risk is unwelcome and presents a barrier to the development of safe stable currency. It is an avoidable risk that has been accepted by traditional market participants unaccustomed to a more transparent alternative. Given that there are no man-in-the-middle issuers, custodians, or middlemen for RTokens, transparency becomes a critical feature of Reserve Protocol helping mitigate errors, deception and censorship.

Proof of Reserves Availability
RToken backing is always available for both verification and redemption — 24 hours a day. This is possible interacting directly with the Reserve protocol smart contracts or using the Register.app token explorer — for example see ETH+ RToken asset-backing here. With this simple ability, users do not need to hope a 3rd party stores their funds where they are instructed to. This is entirely handled by impartial computer code that acts in the way it is told.

Impartiality for proof of reserves brings considerable benefits. In a time of perceived crisis, should stressed users need to verify what an RToken is backed by, it is easy for them to do so. If they want to exit an RToken position, they can do so. They can even do so during times of actual crisis when the RToken is “frozen” (which is triggered under certain governance-predefined conditions).

All these benefits enabled by impartiality reduce the probability of RToken holders engaging in abrupt withdrawals from their RToken positions. This acts as a countermeasure against situations resembling bank runs — as detailed in Part 2. This system facilitates a system whereby a redemption from one RToken holder does not come at the expense of other RToken holders. Moreover, this mechanism aids in maintaining the stability of RToken prices, as users retain the option to liquidate their RToken positions at their discretion.

This trends to an ecosystem in which user funds are safe, verifiable and accessible at all times — a cornerstone of the RToken value offering.

Compare this to the lived experience of USDC holders during the SVB bank run crisis discussed in Part 2. They were unable to verify if USDC was indeed 1:1 backed by US dollars deposited into banks, and so a market formed with users betting against one another as to whether or not the “stablecoin” would return to peg. Many large positions were exited at discounts as high as 12% because participants were unsure if USDC would ever be backed again. Ultimately it did repeg, but this event is not acceptable for a currency that is supposed to be the backbone of a new financial system. This issue is even more pronounced when considering the notoriously non-transparent USDT. The absence of on-chain, verifiable reserves gives rise to numerous complications, rendering it an insecure choice for storing funds.

As an aside, astute readers will note eUSD’s backing is entirely USDC and USDT linked tokens. This is indeed a cause for concern. Thanks to overcollateralization mechanisms inherent (see the installment discussing this topic here) to RTokens, the market perceives these RToken backing concerns to be sufficiently mitigated — as proven by eUSD’s $20M market cap.

.

Part 5: Mitigating Governance Risk
TL;DR
Reserve works to mitigate the pitfalls of onchain governance in the following ways:

A governance structure that aligns decision makers with holders
A multi-stage governance process which enhances review and deters malicious proposals
Specific, accountable executive governance roles like Pauser, Short Freezer, Long Freezer and Guardian, following the principle of “least privilege”
A sufficiently decentralized upgradability system which preserves flexibility while ensuring responsible changes

---

Governance poses significant challenges to all DeFi protocols and DAOs — especially when the protocol’s ownership is fully onchain. A stark reminder of these risks is the $182M governance attack on Beanstalk’s DAO, where a malicious proposal was snuck through governance.

Against this backdrop, Reserve has built a robust strategy to guard against governance attack vectors while still maintaining meaningful decentralized governance.

Decentralized Governance
The Reserve Protocol uses a modified OpenZeppelin Governor instance, known as Governor Alexios. The lifecycle of a proposal is simple: a proposal is created, a waiting period occurs (for 2 days), after which a snapshot is taken and the vote begins (3 more days). A majority vote over quorum triggers the proposed change after an additional timelock (3 more days).

Each protocol change takes at least 8 days to pass a governance cycle. This multi-stage governance system offers numerous layers of security and a large time window to detect threats.

RTokens are governed by those staking their RSR onto the RToken. In exchange for providing first-loss capital, they earn governance rights — as well as yield from the underlying collateral.

With capital at risk, governors tend to responsibly balance profit and capital preservation. Additionally, with a 14-day unstaking period and delayed revenue streaming for RSR stakers, myopic governance initiatives can be avoided. This makes for a safer governance environment in which decisions are carefully considered and weighed before any action is taken.

This onchain governance system was chosen against a backdrop of ever-increasing multisignature wallet use. When used without the appropriate safeguards, they can be taken over by a malicious majority — at the cost of millions in user funds. Multisig wallets also can lack transparency, making risk analyses difficult. They introduce governance risks by empowering an “in” group and disenfranchising voters. It’s also true that human susceptibility to social engineering attacks can also undermine the intended benefits — such as multisig signers getting targeted in a coordinated way to sign something they otherwise would not, like the Harmony bridge hack.

Collateral Asset Protocol Governance
RToken governance was designed to enable laser focus on matters pertaining only to the respective RToken. On top of providing first-loss collateral in exchange for yield, as explained in part 2, they also earn governance rights. Each RSR staked is an additional vote, meaning governors with the most capital at risk have the largest say in the RToken’s governance. This was an intentional design for a variety of reasons.

Given that capital is at risk, an RToken’s governors / stakers (the same) will closely monitor any changes in the parameters of the underlying collateral. For example, High Yield USD (hyUSD) governors are incentivized to pay close attention to MIM governance as it is an underlying collateral asset for hyUSD. If MIM governance choose to do an action that could risk the collateral’s health, it could depeg hyUSD and stakers would have their collateral seized. This is against their aims. Diligent monitoring is fostered by the Reserve protocol design.

This is in contrast to governors of an entire protocol (often without first-loss capital at stake), who have a far wider surface area to focus on (i.e. a plethora of DeFi integrations) and are likely unable to remain as vigilant as these highly specialized RToken governors.

Should RToken governors decide that the underlying asset is too risky, then they can vote to switch the assets backing the RToken. This oversight trends to a culture of responsible decision making. This is unique to RToken design, and contributes to boosting RToken safety.

Guardians and the Principle of Least Privilege
In addition to the governance process above, there are four important governance roles serving as additional layers of defense. These distinct role owners have different powers, each designed to safeguard against different levels of crisis.

This system is designed along the principle of “least privilege”. This aims for a problem to be solved by a group with as little power as possible — as opposed to providing total emergency control. This prevents tyrannical decision making that could have an adverse effect on RToken holders.

These roles are divided between different addresses, and the framework minimizes the likelihood of governance attacks by decreasing and distributing trust throughout the RToken’s emergency power infrastructure.

Ownership of these roles is defined by RToken governors, ensuring responsible use and accountability. If they are dissatisfied with the role holder, they can simply vote them out.

The first role is the Pauser: one entity (or multiple) who can stop the issuing or trading of new RTokens, but cannot stop RToken redemptions (or other functions). This could be one person, a multisig or even a bot which triggers based on failsafe conditions. Since this is the lowest level of guardian, false positives are not a big concern.

Above this stands the “Short Freezer”, an entity capable of freezing RTokens. This disables nearly all RToken functions including minting, redeeming, and unstaking. This “short freezer” can maintain the freeze for a governance-determined amount of time, which is then passed onto the highest level of freezer: the Long Freezer.

Long Freezers can extend the duration of the freeze. This “long freeze” is much longer than the short freeze, and so governance should carefully consider who can trigger it. This particular role exists so that in the case of a zero-day exploit (for example), governance can act before the system unfreezes.

Finally, there is the Guardian role. This address has the ability to reject proposals even if they pass through the governance process. This is a very important role, so RToken governors take selection very seriously.

See the different powers specified between a “paused” RToken and a “frozen” RToken in the table above. It’s important to note that each action has a predefined and limited number of uses to prevent potential for abuse.

The differences in granularity provided by each segmented layer mean that RToken governors have appropriate permissions to apply to incidents varying in severity. This ensures RTokens remain operational to the fullest extent possible in difficult circumstances, and in a trust-minimized manner.

Decentralized Upgradability
The revelation that Oasis upgraded its contracts to confiscate $140M belonging to Jump Crypto sparked debate as to whether or not this violated Ethereum’s core tenet of immutability. Immutability has many benefits as well as costs, but Reserve is fortunate to have found a middle ground: decentralized upgradeability.

Reserve’s production contracts are designed as upgradeable according to OpenZeppelin’s Proxy Upgrade Pattern — but this comes with strings attached. All proposed upgrades must pass the 8 day governance cycle discussed above, controlled by each RToken’s governors. This allows for RTokens to choose not to adopt the latest Reserve contracts if they do not agree with them.

This approach respects decentralization and reduces risk at the same time, whilst affording a high degree of flexibility for potential necessary changes.

Conclusion to Comprehensive Risk Mitigation at Reserve Protocol
Thus concludes Reserve’s safety series. The ~6000 words are testament to the priority Reserve invests in user safety. While risk is around every corner in DeFi, Reserve has taken numerous efforts to come as safe as it can be. Years of painstaking, procedural, and thoughtful work has been verified and proven with comprehensive test suites and audits conducted at huge expense.

It has started this work by making the smart contracts open source, rigorously testing them, engaging the wider Ethereum security for audits. In creating a basket of assets, Reserve has diversified users’ smart contract risk. Core team members followed this up with a focus on assets backing the RTokens by maximizing the likelihood of their 1:1 redeemability which is assisted by overcollateralization in case of an emergency. After this, the development team worked diligently to reduce counterparty risk, which was achieved through ensuring RToken reserves were always verifiable onchain and that the contracts that handled RToken operations themselves were also verifiable. Finally, the protocol learned from the experiences from others using exclusively onchain governance to avoid the trap of multisignature wallet dominance as well as incentivised active governance by requiring governors to put capital at risk. Reserve has also worked hard to make sure the RTokens remain upgradable, but has acted in a way that respects the requirement to make this process as safe and decentralized as possible.

If RTokens are to become the future of currency, all these efforts are necessary and will continue to be as the protocol matures.

The Reserve development team is grateful for your attention paid to this topic. Reserve will be revisiting this series and providing updates over time and welcome your feedback.

If readers would like to discuss any part of this installment or this series, we invite them to join Reserve’s Discord.
