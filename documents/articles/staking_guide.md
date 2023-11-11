Link: https://blog.reserve.org/staking-rsr-on-ethereum-and-base-8218e45f1022
Title: Staking RSR on Ethereum and Base

Earning governance power and RSR yield in exchange for providing first-loss capital.

After being live for 7 months on Mainnet, Reserve has landed on Base — a lightning fast near-zero gas fee Ethereum layer 2 network. With this deployment comes new RTokens and RSR staking opportunities for those looking to earn RSR yield in exchange for governing and providing first-loss capital.

This tutorial will explain the staking, unstaking and bridging processes on both Ethereum Mainnet and on Base.

This tutorial requires an understanding of web3 wallet interactions. With knowledge of fundamental DeFi skills, staking is a straightforward operation.

What is RSR staking?
RSR enables governance and overcollateralization for RTokens deployed on the Reserve Protocol.

RSR stakers provide first-loss capital, meaning their RSR will be auctioned in the case of an RToken’s collateral depegging. This is done so that RToken holders are kept whole, as was proven in the case of the Electronic Dollar ($eUSD) depeg.

Stakers recieve governance votes proportional to the amount of RSR they stake on an RToken, granting those providing this first-loss capital a say on how the RToken is governed.

Each RToken directs a different amount of yield to stakers. eUSD, directs 100% of its yield to stakers, whereas hyUSD sends 16%. This coefficient is configurable and set by governance and incentivises stakers for the risk involved in providing first-loss capital.

Learn more about staking in the protocol documentation.

Mainnet RSR Staking
For purposes of this walkthrough, we have chosen to stake RSR on eUSD. There are many other RTokens and this RToken is being used as an example and does not represent an endorsement. Learn about the different RTokens deployed to mainnet at this register.app page.

To begin, visit register.app. Connect to the Ethereum Mainnet (see top right of the webpage), and be sure that you have RSR in the wallet you are connecting to.

Once you have clicked on the “Stake + Unstake’’ page, you will see eUSD’s staking interface. Connect your web3 wallet in the top right corner using the “Connect” button and register.app will display the amount of RSR in your wallet.

The page also displays the following information:

The ratio of eusdRSR to RSR — eusdRSR is a tradeable receipt for the RSR you have staked on the RToken.
The staking APY — currently up to 12.25% — that you will receive for providing first-loss capital.
The unstaking delay, by default set to 2 weeks, is the delay you must wait for your RSR to be available to withdraw from the RToken to your wallet.

Before taking further steps, verify that the URL you are using is the correct register.app site. This is a critical step in defending against attacks from malicious actors. For mainnet eUSD, this is here.

If these details are acceptable, begin the staking process. To do this, set the amount of the RSR you’d like to stake and then click on the “Stake RSR” button.

First, approve a spend limit for RSR using your wallet’s token approval process.

Once that transaction has been processed, you will now be able to stake your RSR on eUSD.

Once the transaction is confirmed, your RSR will now be staked on eUSD.

Your wallet will receive the amount of eusdRSR in ratio to how much you staked and the RSR:eusdRSR exchange rate.

In this case 1 eusdRSR = 1.02454 RSR, so if you stake 102,454 RSR you will receive 100,000 eusdRSR
Unstaking RSR on Mainnet

To unstake this RSR, enter the amount of RSR you wish to unstake in the register.app “Unstake” box. This can only be up to the same amount of eusdRSR you staked.

Approve the unstake action with your wallet. Once this happens and the cooldown period elapses, you will be able to withdraw your RSR.

For an accurate estimate of the amount of RSR you will receive, multiply the amount of eusdRSR in your wallet by the ratio of eusdRSR:RSR (1:1.02454 as indicated in the image above). If you had 100,000 eusdRSR staked, you will receive 102,454 RSR.

Note that unstaking has a default cooldown period of 2 weeks, after which you will be able to withdraw the RSR into your wallet.

This completes the staking / unstaking workflow for an RToken on mainnet.

Base RSR staking
This process is effectively identical to the mainnet staking process, though it requires a few steps in advance.

The primary advantage of staking on Base is that it will be substantially cheaper to pay for gas fees. There are currently 600 + RTokens on Base and their smaller TVLs mean the staking APYs may vary. There are also security implications for transacting on a rollup.

Nevertheless, if this network fits your risk profile then let’s begin.

Bridging RSR to Base
Before we start, you’ll need to bridge your RSR to the Base network. If you’ve already done this, skip ahead to the actual RToken staking section. If not, please visit this register.app page to begin the bridging process.

Note that withdrawing from Base to mainnet may take up to 7 days to complete, as Base is an optimistic rollup.

To move your RSR from Ethereum mainnet to Base, you’re going to have to select the Ethereum network (as your RSR is currently on this network).

Once that is done, ensure you’re on the correct bridge page (https://register.app/#/bridge?chainId=1) and verify you are depositing to Base (the Network box will indicate “From Ethereum To Base”).

Before you start sending RSR, make sure you send a small amount of ETH to Base so that you can pay gas fees on the network. This will prevent your RSR getting “stuck” until you fund the wallet with ETH. You can do this using this register.app bridge or, if you prefer, the Base Bridge.

Connect your wallet to register.app, and enter the amount of RSR you’d like to transfer. Using your wallet, approve token spending for RSR, and then approve the bridging transaction. Wait for these to confirm, and then your RSR will be deposited to the same wallet on Base.

With this preliminary step completed, it’s time to stake this Base network RSR on an RToken deployed on Base.

Staking / unstaking RSR on an RToken on Base
Connect to the Base network in the top right corner of the register.app webpage. Afterwards, scroll down in the “Select RToken” menu and select the RToken you wish to stake your RSR on. Ensure it has the Base logo next to it and click on it.

Ensure that your wallet is connected to the Base network. If you have yet to do that, please do so by supplying your wallet with the following information:

Network name: Base

Network URL: https://developer-access-mainnet.base.org/

Chain ID: 8453 Currency symbol:

ETH Block explorer URL: https://basescan.org/

See this guide for additional information on connecting your wallet to Base.

Aside from these differences, the staking process is the same on Base as it is on mainnet. The unstaking process is also the same on Base as it is on mainnet. In the interest of brevity, we will not cover the process in the same granular detail.

Closing
This guide takes readers through the process of staking and unstaking RSR on different networks, as well as bridging between them.

If you have any questions about this process or anything relating to Reserve protocol, hop into Reserve Protocol’s discord and community contributors will be happy to hear your thoughts.
