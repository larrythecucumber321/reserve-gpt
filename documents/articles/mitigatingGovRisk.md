Link: https://blog.reserve.org/mitigating-governance-risk-63aab4e3debf
Title: Mitigating Governance Risk

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
Sep 15
6

In this final section of Reserve’s safety series, the potential pitfalls of RToken governance and how Reserve has worked to diminish them will be discussed.

Governance poses significant challenges to all DeFi protocols and DAOs — especially when the protocol’s ownership is fully onchain. A stark reminder of these risks is the $182M governance attack on Beanstalk’s DAO, where a malicious proposal was snuck through governance.

Against this backdrop, Reserve has built a robust strategy to guard against governance attack vectors while still maintaining meaningful decentralized governance.

Decentralized Governance
The Reserve Protocol uses a modified OpenZeppelin Governor instance, known as Governor Alexios. The lifecycle of a proposal is simple: a proposal is created, a waiting period occurs (for 2 days), after which a snapshot is taken and the vote begins (3 more days). A majority vote over quorum triggers the proposed change after an additional timelock (3 more days).

Each protocol change takes at least 8 days to pass a governance cycle. This multi-stage governance system offers numerous layers of security and a large time window to detect threats.

RTokens are governed by those staking their RSR onto the RToken. In exchange for providing first-loss capital, they earn governance rights — as well as yield from the underlying collateral.

With capital at risk, governors tend to responsibly balance profit and capital preservation. Additionally, with a 14-day unstaking period and delayed revenue streaming for RSR stakers, myopic governance initiatives can be avoided. This makes for a safer governance environment in which decisions are carefully considered and weighed before any action is taken.

Multisig addresses
Onchain governance exemplifies a purer decentralized decision-making system. However, due to the complexity of such processes, some protocols instead opt for multisig wallets, a type of protocol-owned wallet that requires multiple approvals for transactions. This substitutes onchain governance processes, often as a claimed temporary measure.

Multisig wallets undoubtedly have the potential to enhance security and mitigate risks. As such, many protocols use them to control key protocol functionality. Nonetheless, they are often not being used with necessary safeguards and their disproportionate control over DeFi protocols is motivated often by developer convenience as opposed to safety.

When used without the appropriate safeguards, they can be taken over by a malicious majority — at the cost of millions in user funds. Multisig wallets also can lack transparency, making risk analyses difficult. They introduce governance risks by empowering an “in” group and disenfranchising voters. It’s also true that human susceptibility to social engineering attacks can also undermine the intended benefits — such as multisig signers getting targeted in a coordinated way to sign something they otherwise would not, like the Harmony bridge hack.

To address these issues, Reserve has chosen to pursue onchain governance from the outset, thus increasing RToken security through censorship resistance, and transparency. Onchain governance nullifies any chance for multisig keys to be compromised or for other unauthorized access to RToken assets (remember that governance controls almost every important parameter for RTokens) that would result in a loss of funds. By choosing to decentralize ownership from the outset, the protocol has increased safety for its users.

In prioritizing safety over convenience, Reserve creates a robust onchain decision making system without the vulnerabilities associated with overreliance on multisig wallets — from day one.

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

Safety Principles Conclusion
This series is testament to the priority Reserve invests in user safety. While risk is around every corner in DeFi, Reserve has taken numerous efforts to come as safe as it can be. Years of painstaking, procedural, and thoughtful work has been verified and proven with comprehensive test suites and audits conducted at huge expense. Be it the smart contracts themselves, the assets backing the RTokens, the onchain decision making system or the counterparties RTokens depend on, Reserve has gone the extra mile in maximizing safety. If RTokens are to become the future of money, all these efforts are necessary and will continue to be as the protocol matures.

The Reserve development team is grateful for your attention paid to this topic. Reserve will be revisiting this series and providing updates over time and welcome your feedback.

If readers would like to discuss any part of this installment or this series, we invite them to join Reserve’s Discord.
