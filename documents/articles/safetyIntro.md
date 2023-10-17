Link: https://blog.reserve.org/introducing-reserves-safety-series-6b13e44e672c
Title: Introducing Reserve's Safety Series

River
Reserve
River

·
Follow

Published in
Reserve

·
4 min read
·
Sep 11
4

Preface
As economist John Allen Paulos said, “uncertainty is the only certainty”, which is especially true in DeFi. Indulge the team a while to understand Reserve’s security philosophy and learn the steps it has taken to ensure the protocol is as robust as possible.

This introductory installment is the first in a five-part series, and the remaining installments will be introduced over the course of the week. The length of this series is testament to how seriously core developers take security and it represents a fraction of the actual work that goes into securing Reserve. This series’ purpose is that the community be left with a keen awareness of the primacy of secure and safe development.

Note that this series requires some understanding of what an RToken is. To quickly familiarize yourself, watch this video.

Introduction: Why care about safety?
Risk and risk management is key to investment strategy. Risk stems from uncertainty: decision makers face the challenge of maximizing investment return while navigating a changing market.

Both risk and risk management are prerequisites for strong portfolio returns. To be blunt, participants cannot profit in DeFi without strong risk management and even then still stand a good chance of losing everything.

Crypto portfolio management is relatively new. While the objective remains much the same as traditional asset management, a crypto-native risk management approach differs due to novel hazards inherent to DeFi. Crypto portfolio managers have to navigate concepts unique to DeFi: smart contracts, tokenomics, governance frameworks and so on.

DeFi’s unique nature creates complexities in risk assessment, resulting in an industry-specific risk-reward profile. DeFi also offers the potential for significant returns, often surpassing traditional finance benchmarks.

Nevertheless, the risks associated with DeFi are clear with billions of dollars in capital losses between retail and institutional investors alike. Some memorable (or forgettable) moments from the past year include the Wormhole bridge getting hacked for $326 million, Euler Finance being exploited for over $200 million — lest the memory of Terra Luna‘s catastrophic collapse is forgotten.

Not only do users in DeFi have to contend with often poorly designed economic systems, they also have to factor in the chance there will be a total irretrievable loss of funds — which is less common in traditional finance.

These risks are known and substantial effort has been put into finding solutions. For example, a smart contract audit has become a mainstay for any project and attracting significant TVL without one is challenging.

Demand for audits is an improvement in DeFi — it has decreased risk. Unfortunately, for some projects, having one has become a meaningless rubber stamp. These projects assume that one audit proves their contracts are bulletproof. They will then market their code as “safe” upon audit completion — which is confusing at best and deceptive at worst. No amount of auditing can make a project completely safe.

Given the complex nature of DeFi protocols, one audit is rarely comprehensive and vulnerabilities are missed by teams of the best auditors. While (multiple) audits are necessary, they are not enough.

Despite other important guards such as bug bounties, multisignature wallets, insurance and so on, it is clear that current industry-standard security efforts still fall short. Serious losses have stained DeFi’s reputation and continue to dissuade capital allocators. Due to this polarized risk-reward dichotomy, risk mitigation has become a cornerstone of DeFi.

While savvy DeFi funds have already developed risk frameworks to deploy capital at scale, more is needed to bolster returns and protect against black swan events. This could be a key catalyst for follow-on investment.

In this piece, contributors introduce a framework for understanding how the Reserve Protocol grapples with the many threat vectors plaguing DeFi and how it designed a system which counteracts these risks.

Contributors hope this framework will be used by DeFi investors and projects to not only better gauge DeFi risks but also drive future research, discovery and innovation in this space. The piece contains the following sections:

Mitigating Smart Contract Risk: how Reserve navigates smart contract risk through design and system testing, audits and other tools.

Mitigating Depeg Risk: how Reserve counteracts depeg risk through diversified asset-backing and an overcollateralization system.

Mitigating Counterparty Risk: how the protocol mitigates counterparty risk by utilizing transparent and autonomous smart contracts that removes middlemen and enables users to verify public code.

Mitigating Governance Risk: how the Reserve Protocol has implemented robust blunting strategies against governance attack vectors.

With this introduction out of the way, look forward to tomorrow’s piece detailing how Reserve has worked hard to mitigate smart contract risk.

If readers would like to discuss why safety is so important or get clarifications, the core team invites them to join Reserve’s Discord.
