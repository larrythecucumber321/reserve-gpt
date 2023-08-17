Link: https://blog.reserve.org/the-rtoken-deployer-checklist-7d92466c1304
Title: The RToken Deployer Checklist

Reserve’s mission is to increase adoption of, and expand access to sustainable, inflation proof, stable currency. The Reserve Protocol is a free, permissionless platform to build, deploy and govern asset-backed currencies — we call them “RTokens.”

The protocol has undergone an extensive four-year research and development process, resulting in a codebase that has been rigorously tested and audited. Review the audits here.

The following post will walk you through what you need to know to create successful RTokens. If you have a question about Reserve or RTokens, there is always someone helpful and available to answer questions. Don’t be shy, drop into our Discord and get involved!

If you haven’t already, we encourage you to spend 30 minutes on this video to get to know the Reserve Protocol and RTokens that share revenue, are censorship-resistant, and have proof of reserves on-chain, 24/7.

Register.app is one of the many potential frontends available to interact with the Reserve Protocol to launch or stake RTokens on Ethereum mainnet. Here is an in-depth video overview of Register.app.

Anyone, including anons, can set parameters, create, and mint an RToken in less than an hour at Register.app. Users minting the RToken are required to deposit the collateral basket 1:1, or use the provided zap utility to obtain the underlying collateral with a single token.

Asset-backing, stability & yield
Each collateral asset in the Reserve Protocol requires a plugin built by developers or protocols in the community. For example, Aave may build the aUSDC plugin, or an entrepreneur may build the plugins for Convex or Flux Finance. The good news is if you are an RToken deployer, there are already over 25 different collateral plugins available to you. See our active list at this link and click “Add to Basket.” More information on building collateral plugins can be found here.

Here is a link to all the parameters mentioned in the Register.app.

The most attractive RTokens may have attributes that include diverse backing, interesting revenue share approaches, good branding and messaging, unique ecosystem use cases, and partnership integrations. However, as you can imagine, just because anyone can deploy and mint an RToken that does not mean people will adopt and use it. Given the low barriers and permissionless nature of launching RTokens, every RToken may not be successful. Making something great is up to you.

Regarding your proposed RToken, we encourage you to fork this model and utilize DefiLlama to identify collateral assets that meet your expectations for yield vs safety.

We recommend that you not put all of your eggs in one basket. An RToken with a diverse basket of 4 to 8 assets would diversify your (smart contract, censorship, asset) risk exposure should any single asset become unstable or experience a black swan event. We suggest RToken deployers use proven stable assets unless the RToken deployer has unique knowledge and understanding of more exotic protocols and assets.

Backtesting stability
In addition to the model above, we created the RToken backtester to help prospective RToken creators experiment with different basket compositions and visualize how their custom basket would perform over time against a benchmark of their choice. The backtester tool is simple to use:

If you would like to use custom basket weighting, make sure the toggle is on. If the toggle is off, the tool will utilize income weighted baskets.
Select the basket weights for each component of our basket. For example, if you have 3 assets in your baskets and you want one to have 50%, while the other two have 25%, you would write in “50,25,25”
Select the pools you would like to use in your basket in the corresponding order to the basket weights you inputted in step #2
Select a pool that you would like to use as your benchmark rate
Click Run and see how your basket would have performed vs the benchmark you selected! (Sample video can be found here)
RSR Stakers choose which RTokens to support or not to support through staking. RTokens share revenue with RSR stakers who provide governance and over-collateralization for each RToken. The upside is stakers share revenue and have a voice. The downside is a risk of the stake being slashed should asset-backing of an RToken fail.

RToken deployers will compete to design and deploy safe RTokens that will attract the most RSR stakers which can lead to network effects and accelerate adoption for RTokens. Learn more about RSR staking here.

A few basic questions for your RToken:
What is your RToken’s unique selling proposition for its ecosystem?
How will your RToken achieve its first $20 million in TVL? Who are the user segments and use cases?
Are there any partnerships or integrations available with other ecosystems?
What is the aggregate yield target for the RToken? How will the revenue be split among stakeholders? (fork this model)
What is the RToken collateral basket mix? (fork this model)
Example RTokens
If you would like to see how the above questions were answered for existing RTokens please take a look at recent ETH+ and hyUSD examples.

Go deeper
We invite you to join the Reserve Discord to brainstorm on these questions and more with the community. There you’ll meet other developers, protocols, go to market maxis and community members that can play a role in helping to launch your RToken.

For more information, please read the Reserve Protocol FAQ.
