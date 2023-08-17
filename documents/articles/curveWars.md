Link: https://blog.reserve.org/reserves-participation-in-the-curve-wars-e95ff34a3c8b
Title: Reserve’s participation in the Curve Wars

This article will go into detail about Reserve’s participation in the Curve Wars — what it entails and how it benefits RToken deployers & RSR holders. If you are solely interested in learning how to LP with your RSR tokens, feel free to jump ahead to the “Providing liquidity with RSR” section.

The phenomenon of the “Curve Wars” has been an omnipresent topic of discussion in the DeFi world for quite some time now, and you might have heard that Reserve recently decided to participate. In this article we want to share Reserve’s strategy in it and describe how it benefits RToken deployers & RSR holders. For a primer on what exactly the Curve Wars entail we recommend this article.

Reserve’s strategy
Curve is a decentralized exchange (DEX) known as the best place in DeFi for building stablecoin liquidity due to (a) its ability to provide low slippage trades between stablecoins and (b) its liquidity incentive mechanism with CRV, the platform’s governance token.

RToken deployers will want to provide an easy & cheap way for their RTokens to be bought, as minting new RTokens can be quite expensive in gas fees. We believe Curve to be the ideal exchange for early-stage RTokens as the creation of trading pairs is permissionless and we can help incentivize high APYs for people who provide liquidity through the strategy described below.

The way the optimal Curve incentive strategy works is quite complex. As we don’t want you to leave with more confusion after reading this article, we’ll cut some corners and only give you the highest-level explanation in a few steps:

Those who own veCRV (locked CRV tokens) decide which Curve trading pools get incentivized through CRV emissions (or, in other words, which pools can offer a higher APY for providing liquidity).
Over the years, Convex Finance has acquired the majority of veCRV in the market, which has resulted in vlCVX (vote locked Convex tokens) holders now deciding for the most part which Curve pools can offer a higher APY for providing liquidity.
Reserve wants RToken & RSR pools to have a high APY for providing liquidity, as more liquidity on these pools will result in easier & cheaper buying & selling of RTokens & RSR.
So.. Reserve has been purchasing large amounts of CVX tokens and locking them for vlCVX, which gives us a lot of voting power to decide which Curve pools are incentivized with more CRV rewards (and will use that power to incentivize RToken & RSR pools).
Reserve is currently the #7 largest protocol holder of CVX, holding about $4.9 million worth of its token.

Source: DAO CVX Leaderboard
Providing liquidity with RSR
As described in the section above, Reserve’s large holdings of CVX tokens allow us to have a lot of voting power on which Curve pools can offer a high APY for providing liquidity. We intend to use this power to offer LPs on RToken & RSR pools high APYs, thereby making it easier & cheaper to buy/sell them on-chain.

As of today there are no RToken pools on Curve yet, which means that the entirety of our CVX voting power goes into the RSR/FRAX-USDC pool. As a result, LPs to this pool can currently earn up to 67.4% in yearly rewards. As this is not a fixed APY, it is expected to go down if more people decide to LP or if new RToken pools come to exist (as Reserve will then dedicate part of its CVX voting power to those pools). Nevertheless, this could be an interesting opportunity for RSR holders wanting to put their tokens to work while waiting for native RToken staking APYs to pick up.

That being said, choosing to LP tokens on Curve comes with a few intrinsic risks — ones that we highly recommend you learn about before considering to LP. Let’s take a look at what those risks are.

What to consider before providing liquidity
The following are a few considerations to keep in mind if you’re thinking of LPing into the RSR/FRAX-USDC pool:

Exposure to FRAX + USDC: when an LP in this pool, you are exposed to RSR, FRAX & USDC. This means that, besides being exposed to RSR, you are also exposed to any risks of FRAX and USDC.
Variable yields: as described in the sections above, the APY on this pool is not fixed. It could go down as more tokens are being LPed or more RToken pools come to exist.
Ethereum gas fees: Curve is known to be gas inefficient, which means that the LP action itself, claiming rewards, and/or withdrawing tokens from the pool could turn out more expensive than you expected. Make sure to double-check the estimated gas prices on your transactions!
Impermanent loss (IL): impermanent loss refers to the phenomenon where LPs of tokens earn less from price movements of those tokens than if they had simply held on to them. We recommend learning about IL and/or using an IL calculator before deciding to LP your tokens.
Smart contract risk: as with any DeFi protocol, there is smart contract risk. While both Curve and Convex have existed for quite some time, are in the top 5 DeFi protocols based on TVL, and are generally considered “battle-tested”, it is important to be aware of this risk.
Before we dive into a step-by-step guide on how to LP on Curve, we’d like to cover one more topic, namely why Reserve decided to include FRAX in the RSR pool.

Why did we include FRAX in the RSR pool?
Before FRAX came along, the most popular tokens that could be traded on Curve were paired with what’s called the 3pool — a pool consisting of USDC, DAI & USDT. After some time, Frax Finance decided to offer an alternative, the Frax Base Pool consisting of 50% USDC and 50% FRAX (which in itself is currently mostly composed of USDC).

What makes pairing with FRAX attractive is the fact that Frax is one of the largest holders of vlCVX and uses this voting power to proportionally vote on all pools that include FRAX to help incentivize liquidity.

In summary, pairing with FRAX is a way to be mostly denominated in USDC, have easy trading into USDC, and to take advantage of Frax Finance’s incentivizes for higher yield.

Step-by-step guide on how to LP on Curve
Make sure you are holding RSR, FRAX and USDC tokens in a non-custodial wallet such as MetaMask.
On https://curve.fi/, navigate to the “Pools” section, search for “RSR” and click on the RSR+FRAX/USDC (FRAXBP) pool to go to its detail:

3. After connecting your Ethereum wallet, press the “Add all coins in a balanced proportion” button to avoid slippage & MEV bots and use the “Approve Spending” button to allow Curve to access the required amount of your tokens (this will prompt three transactions to be signed in your wallet).

4. After having approved the spending, click the “Deposit” button to deposit your tokens into the Curve liquidity pool.

5. After successfully depositing your RSR, FRAX & USDC tokens you will have received LP tokens in return, which you can see in your wallet by adding the LP token’s contract address to your wallet or by inspecting your Ethereum address on debank.com or zapper.fi. From this point onward you will be receiving the pool’s variable APY.

Steps to stake LP tokens on Convex for bonus APY

1. If you wish to boost your APY you can do so by depositing your LP tokens into Convex Finance. To do so, navigate to the Convex staking page, connect your wallet, and search for RSR in the “Stake Curve LP Tokens” section.

2. Under “Deposit”, select the amount of LP tokens you wish to stake and click the “Approve” button to allow Convex to access the required amount of tokens.

3. After approval, click on “Deposit & Stake”, sign the transaction in your wallet, and you’ll start earning boosted APYs on your initial deposit!

Disclaimer: this guide described a way to provide RSR liquidity on Curve, which is different from native RSR staking on RTokens and includes its own risks. Staking on RTokens can be done through Register.app once RTokens get added.

The author of this article does not recommend providing liquidity or not doing so. This is merely an explainer to answer any questions our community may have.
