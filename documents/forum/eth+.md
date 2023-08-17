Link: https://forum.reserve.org/t/rfc-introducing-eth/386
Title: RFC - Introducing ETH+

Eridian

2
Apr 15
Introduction
Introducing ETH+ 21, a reward-generating Ethereum Liquid Staking Token basket with over-collateralized protection.

The Future of Ethereum is at Stake.

In this RFC, I will give an overview of the new RToken ETH+. I highly encourage the community to ask questions and share their suggestions. If you want to help make this RToken a success, please reach out to me.

Mandate
What is the mandate?
Maintain an Ethereum-aligned Liquid Staking Token basket.
Positively impact the Ethereum staking distribution.
Provide value to ETH+ holders through diversification.
Why is that the mandate?
A simple, Ethereum-aligned, directive that allows flexible governance in the pursuit of this mandate.

What rules does the mandate set for governance?
The mandate does not dictate the specific rules used for the governance of the RToken. The RSR stakers, given their tokens at stake, will act in the best interest of the RToken.

Deployer
Who is the deployer?
Hello :wave: I’m Eridian and I’ve been an active member of the Ethereum staking community for over 18 months. As a member of the EthStaker community and a solo Ethereum staker, I’m interested in all things staking. I write and maintain the EthStaker Knowledge Base, as well as DVStakers, an educational resource focused on the future of Distributed Validator Technology (DVT). I’m an active community member of a number of existing and upcoming LSD protocols, engaging their teams on how to support and onboard community stakers. Any governance tokens that I own of any of these protocols can all be seen on my public ENS eridian.eth. This will continue to be true moving forward, as I believe transparency will be important when suggesting and voting on new LSD tokens to add to the basket.

Primarily though, I’m focused on decentralization and accessibility. Ethereum’s value to the world is as a decentralized network that is credibly neutral, but that isn’t going to happen by accident, we all have to make it happen.

Deployer Address: eridian.eth 0xE3e34FA93575AF41BEF3476236E1A3CDb3F60B85
https://twitter.com/EridianAlpha 16
Why did I decide to deploy the RToken?
LSDs provide an opportunity to expand the Ethereum staking ecosystem beyond people with the 32 ETH minimum requirement for solo staking. It also allows users to gain compounding rewards, something not possible directly with solo staking. But the LSD ecosystem is already daunting for users not deeply involved with the space, and this problem is about to become exponentially worse as a Cambrian explosion of new LSD protocols comes online in the coming months! I always thought an LSD token basket would be a good idea, but it wasn’t until I attended the Reserve Hackathon event in ETHDenver 2023 that I saw how it could be achieved as an RToken. The deployment of the ETH+ RToken is a continuation of that hackathon.

What’s in it for me?
In my original proposal, I suggested that a small portion of the rewards could be directed to a DAO that would support the growth and ongoing maintenance of the RToken. Instead, after giving it some thought, I opted to direct revenue simply to the RToken holders and RSR stakers. In the future, I still think a DAO could be a good idea, and I believe it would be in the best interest of this RToken. However, right now, I don’t have a group of people to form a DAO with who are aligned and supportive of this RToken (but if you’re reading this, that could be you!). I hope that will change as people in the Reserve community and wider DeFi community get behind this project and a DAO could be formed through a governance proposal to the RSR stakers for a share of the rewards.

I believe DeFi is the future of finance. Creating a fairer, more open, and transparent financial system. I’m genuinely excited to see how this project grows and what part I can play in that journey.

Collateral Asset Backing
What does the initial collateral backing for this RToken look like?
50% rETH - RocketPool LSD
50% wstETH - Lido LSD
Why was this collateral backing chosen?
As two of the largest LSDs in the Ethereum staking ecosystem rETH and wstETH provide deep liquidity and a diverse set of validators. They also have Chainlink oracles available which are used to monitor the price of the assets. Oracle availability is currently the main limitation to adding more LSDs to the basket. As reliable oracles become available, new LSD plugins will be created, and proposals will be submitted to RSR stakers for inclusion into the basket.

A part of the RTokens mandate is to “positively impact the Ethereum staking distribution” which means encouraging more equitable distribution of LSDs. As Lido currently has a significantly larger share of the total Ethereum stake than RocketPool, setting an equal collateral backing encourages greater usage and adoption of rETH.

Should governance keep the collateral backing as it is or update it whenever it can?
The collateral backing should be updated whenever a new LSD can be integrated at a technical and social level, or an existing LSD in the basket is no longer viable. As governance proposals can be put forward and voted on by RSR stakers for the RToken, there won’t be set criteria for which LSDs should be included or rejected, as this will be decided by the RSR stakers.

What is the estimated APY with the initial collateral backing?
The estimated APY is based on the rewards accumulated by the underlying staked assets.

There is no guaranteed APY and there is always a risk that a slashing event or other unforeseen circumstance could cause the underlying collateral to lose value, even past the point of the RSR over-collateralized protection. Smart contract risk also means that nothing is certain, everything is at risk. Nothing presented here is financial advice and it should not be considered financial advice.

Revenue Distribution
What will the initial revenue distribution look like?
95% passed through to the RToken holders.
5% distributed to the RSR stakers for providing governance and over-collateralized de-peg protection.
Example:
100 ETH total is staked in the RToken basket, 50 ETH with RocketPool for rETH and 50 ETH with Lido for wstETH. Over time rewards are earned by those two protocols so now the total value of the ETH in the basket is 105 ETH. 95% would be passed through to the RToken holders (4.75 ETH) and 5% would go to the RSR stakers protecting and governing the RToken, equating to (0.25 ETH).

Why was this particular distribution chosen?
This ratio was chosen to be competitive in a growing LSD market. If the rewards for holding the ETH+ were significantly lower than the underlying assets then it would not be attractive for users to hold the RToken over those assets directly.

The reward distribution for RSR stakers must also be attractive so that they have the incentive to stake and risk their tokens, while also providing governance.

This fee is comparable with existing competitors in the Ethereum LSD index space.

This balance should be reviewed and adjusted in the future if the RSR staker governance decides the ratio should be updated.

Product Differentiation
How does this RToken differ from competitors?
A key differentiator of the ETH+ token in comparison to competitors is the over-collateralized protection provided by RSR stakers.

To have a dynamic basket of tokens, governance is required. Competitor indexes can either have completely centralized single-entity governance or a general DAO governance where anyone with the DAO governance token can vote.

ETH+ utilizes RSR stakers to provide both governance and over-collateralized protection. This ensures an aligned incentive for the governance voters to vote in the best interest of the RToken, and to actively protect it from any malicious proposals.

The RSR stakers are active participants and are rewarded proportionally for their input to the specific RToken ETH+. They have “skin in the game”.

Why will people use this RToken?
Passive yield exposure: Users can enjoy attractive rewards on their ETH through a diversified basket of liquid staking tokens.
Diversified counterparty risk: ETH+ offers over-collateralized protection and simplifies DeFi integrations.
Reputation neutrality: ETH+ allows for simple DAO treasury diversification.
RSR staking protection: RSR tokens will be sold off in the event of a de-peg to cover losses suffered by the basket.
Go To Market
Who do you see as the early adopters and advocates of this RToken?
People who like stacking ETH
People who want passive (compounding!) rewards without monitoring every new LSD token and manually rebalancing their portfolio.
DeFi enthusiasts exploring ways to earn passive income
DeFi yield farmers, especially on Curve
DAOs who want to diversify their treasuries
RSR stakers who believe in the project
Community members are invited to create novel strategies and tactics to raise awareness for ETH+ and improve its positive impact on the wider Ethereum ecosystem. If you have go-to-market ideas and would like to contribute please leave comments and suggestions.

What does success look like for this RToken?
A highly liquid reward-generating token that can be easily minted, traded, and used in DeFi protocols on both Ethereum L1 and L2s.

Branding
Why was this RToken name chosen?
This RToken embodies Ethereum values and culture, plus diversified rewards. ETH+ represents this, and also it stands out as a simple name from the growing list of complex LSD names (abcETH, xyzETH, stk2.0ETH2V2.0, etc.).

What does the logo look like?
ETHPlusLogo
2134×2134 114 KB
Why was this logo chosen?
A simple logo that is easily recognizable at all size ranges and can be associated with the token name even without knowing anything about the token.

What does the brand represent?
The brand is the embodiment of the RToken mandate:

Maintain an Ethereum-aligned Liquid Staking Token basket.
Positively impact the Ethereum staking distribution.
Provide value to ETH+ holders through diversification.
Call To Action
What is expected from the RToken’s governors?
Advocates of ETH+ adoption, usage, and the values of the mandate.
Active participation in both forum discussions and governance proposal votes.
An interest in the Ethereum Staking ecosystem, keeping up-to-date on developing technologies and new LSD providers.
What can the community do to make this RToken a success?
Get involved! If you ever wanted to be “early” to a project, now’s the time :slightly_smiling_face:
Please share any thoughts you have about this RToken in the comments below.
