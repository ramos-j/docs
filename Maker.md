Maker
=====

Quick information
-------------------------------

Maker is a Decentralized Autonomous Organization (DAO) that backs the value of the dai stablecoin on the Ethereum blockchain. A DAO is an organization that is entirely blockchain based, using smart contracts to enforce its rules and business logic.

**DAI** is a stablecoin used for trade and transfers on Ethereum. A stablecoin is a cryptocurrency with price stability.

**MKR** is a speculative share that backs the value of the dai. Maker earns a continuous fee on all outstanding dai, in return for governing the system and taking on the risk of bailouts. Maker's income is funnelled to MKR owners through Buy&Burn.

#### Quick links

* [Chat](https://makerdao.slack.com) - Primary platform of community interaction
* [Forum](https://forum.makerdao.com) - For debate and proposals
* [Subreddit](https://www.reddit.com/r/makerdao) - Best place to get lateste news and links
* [GitHub](https://github.com/makerdao) - Repository of the public Maker code
* [TeamSpeak](https://ts.makerdao.com/) - For governance meeting conference calls
* [SoundCloud](https://soundcloud.com/makerdao) - Governance meeting recordings
* [MakerX](https://x.makerdao.com) - MKR and DAI decentralized exchange


Introduction to the dai stablecoin and Maker
------------------------------------

### Dai and Maker

Dai is a stablecoin, and Maker is the organization that backs its stability. This is achieved by keeping the dai *market price* stable around a *target price* using two backing mechanisms: 

* **The Dai Credit System**  ensures all outstanding dai are backed in excess by liquid assets as collateral. So if the target price is 1 USD, there will always be locked collateral worth more than 1 USD backing each outstanding dai.

* **The Maker Stability Service** acts as a failsafe in case there is bad collateral, automatically diluting the MKR supply to pay for bailouts if they are needed due to a collateral crash.

New dai enter the money supply when a *borrower* uses the Dai Credit System to borrow dai by posting collateral with Maker. The collateral is held in a smart contract called a Collateralized Debt Position (CDP) from where it is used to back the stability of the dai. It is always possible to instantly verify that all dai are fully backed according to the rules of the Dai Credit System, since the collateral is held in transparent smart contracts on the Ethereum blockchain.

Any Ethereum account is free to borrow dai without any requirements or restrictions beyond posting adequate collateral. Dai borrowing has no term limits, and borrowers can open and cover CDPs at any time.

Dai *holders* buy dai from borrowers and use it as a stablecoin for transactions with users and applications on Ethereum, or as a long-term deflationary store of value.

### MKR, the share of Maker

MKR is the name of the token that act as shares in the Maker DAO. The price of MKR depends on the performance of the Dai Credit System.

MKR gains value from the Dai Credit System because the MKR token represents ownership of the Maker Stability Service. All dai borrowers pay a *stability fee* which is funneled to MKR owners with Buy&Burn. In return, Maker is forced to bail out any bad debt in the event of a sudden collateral crash (called a *black swan event*). Bailouts are done with Emergency debt backed by forced dilution of the MKR supply. As a result, MKR owners are exposed to both the profits and the risk of the Maker Stability Service.

The total MKR supply starts at 1,000,000 MKR. Before deployment of the system 421,897 MKR (42.1897%) was distributed to founders and early buyers.

The remaining undistributed 578,103 MKR was given to the Maker Fund, a smart contract that holds money on behalf of the Maker DAO and is controlled by MKR owners through the Maker Governance Process.

### The basic mechanics 

The target price of the dai is denominated in Special Drawing Rights (SDR) - an international currency basket maintained by the IMF that has low volatility against all major world currencies. When the Dai Credit System is launched, the value of 1 DAI will be pegged to an initial target price of 1 USD worth of SDR at [the exchange rate reported by the IMF](https://www.imf.org/external/np/fin/data/rms_sdrv.aspx). After launch the dai will detach from this initial target and start to slowly appreciate against the SDR over the long term while maintaining low volatility in the short term.

Borrowing new dai is done by locking an amount of collateral inside a Collateralized Debt Position (CDP) smart contract, which then sends newly borrowed dai to the borrowers wallet, while also creating a corresponding amount of debt. Over time, the CDP accrues a stability fee which is added on top of the debt. The borrower can retrieve the posted collateral by *covering* the debt plus the stability fee accrued since the CDP was created. All stability fees from CDPs go into the Buy&Burn contract

The Buy&Burn contract uses dai sent to it to buy up MKR from the market and "burn" it, permanently removing it from the MKR total supply. The continuous cash flow from the stability fee gets turned into a continuous cash flow into the MKR, giving it an intrinsic value based on the total long term value of this earned cash flow.

>*__Example 1:__ Bob wants to borrow 100 dai. He locks an amount of BTC worth significantly more than 100 dai into a CDP and uses it to borrow 100 dai. The 100 dai is instantly sent directly to his Ethereum account. Assuming that the stability fee is 0.5% per year over the coming year bob will need 100.5 dai to cover the CDP if he decides to retrieve his BTC after one year.*

The deflationary nature of the dai means that the market value (measured in SDR) of the debt also increases over time, adding an additional cost to borrowing beyond the *Maker fee*. The dai deflation is a transfer of value from dai borrowers to dai holders, while the Maker fee is a transfer of value from dai borrowers to MKR owners.

In practice, the borrower is either seeking to take a leveraged long position on the asset used as collateral (“margin trading”), or seeking liquidity in a hard currency without wanting to sell the asset used as collateral (for example, a business collateralizing its own stock in order to raise short-term liquidity for operational expenses).

In both cases, the way the borrower obtains the asset he actually desires is by selling the borrowed dai on the open market for the asset he wants. On the other side of this trade, buyers will want to obtain dai in order to use it as a stable cryptocurrency on the Ethereum blockchain or simply to earn capital gains due to its long-term deflationary nature.

>*__Example 2:__ Bob wishes to go margin long on the BTC/DAI pair, so he borrows 100 SDR worth of dai by posting 150 SDR worth of BTC to a CDP. He then buys another 100 SDR worth of BTC with his newly borrowed dai, putting him at a net 1.66x BTC/SDR exposure. He’s free to do whatever he wants with the 100 SDR worth of BTC he obtained by selling the dai, while the original BTC held as collateral (150 SDR worth) remains locked until the debt plus the stability fee is covered.*

Although CDPs are not fungible with each other, the ownership of a CDP is transferable. This allows CDPs to be used in smart contracts that perform more complex methods of borrowing (for example, involving more than one actor).

>*__Example 3:__ Alice and Bob collaborate using an Ethereum OTC contract to issue 100 SDR worth of dai backed by BTC. Alice contributes 50 SDR worth of BTC while Bob contributes 100 SDR worth. The OTC contract takes the funds and creates a CDP, thus borrowing 100 SDR worth of dai. The newly borrowed dai are automatically sent to Bob. From Bob's point of view he is buying 100 SDR worth of dai by paying the equivalent value in BTC. The contract then transfers ownership of the CDP to Alice, meaning she ends up with 100 SDR worth of debt (denominated in dai) and 150 SDR worth of collateral (denominated in BTC). Since she started with only 50 SDR worth of BTC, she is now 3x long BTC/SDR.*

How Maker keeps the dai stable
------------------------------

The stability of the dai around the target price is maintained by continuously matching supply and demand, through modifying the demand for borrowing and the demand for holding via *deflation rate adjustment*. An additional mechanism, the *forced cover*, directly enforces the target price on the open market using collateral from CDPs, and also ensures short-term liquidity and price support in the face of dai demand shocks.

### Long-term stability and the deflation rate

Deflation rate adjustments ensure that the dai market price remains stabilized around the target price. When the market price of the dai is below the target price, the deflation rate of the dai increases, causing borrowing to become more expensive and thus leading to a corresponding reduction in supply. At the same time, the increased deflation rate causes the capital gains from holding dai to go up, leading to a corresponding increase in dai demand. This combination of reduced supply and increased demand causes the dai to appreciate in value, pushing it up towards the target price.

The same mechanism works in reverse if the market price is higher than the target price: The deflation rate decreases, leading to an increased demand for borrowing dai and a decreased demand for holding it. This causes the dai to depreciate in value, pushing it down towards the target price.

This mechanism is a negative feedback loop: deviation away from the target price in one direction triggers a push in the opposite direction. The magnitude of the deflation rate adjustments depend on how strongly the market price deviates from the target price, so that strong deviations result in aggressive adjustments while weak deviations result in small adjustments.

### Short-term liquidity and price support

To directly enforce the target price in the marketplace and to counteract demand shocks, a secondary stability mechanism exists: the forced cover.

Under normal market conditions every dai in existence is backed by an excess of collateral locked in CDPs with many different collateral types. The *collateral ratio* (the proportion of collateral to debt) of every CDP is transparent and can be verified cryptographically on the Ethereum blockchain.

The forced cover mechanism is a way for dai holders to pay down the debt on behalf of a CDP borrower in order to buy a portion of the collateral that is locked in the CDP. The amount of collateral that the forced cover buys is determined relative to a price feed. Any leftover collateral is returned to the borrower and the CDP is then deleted.

The cost of doing a forced cover on a properly collateralized CDP comes in the form of a negative *nominal bounty*, which means you have to pay a penalty for the privilege of getting instant, guaranteed liquidity.

The bounty varies based on the collateral ratio of the CDP, so that well-collateralized CDPs have lower (more negative) bounties. This relationship between collateral ratio and bounty is defined by the *collateral curve* (a linear function with slope -1, meaning a 1% increase in the collateral ratio of a CDP will result in a 1% decrease of the CDP's bounty). collateral curves are defined by their *zero points*, which is the collateral ratio at which the bounty is zero. The zero point is different for each type of collateral according to a basic principle: riskier and more volatile collateral types have higher zero points, while safer and less volatile assets have lower zero points.

>*__Example 4:__ If we assume that bitcoin has a zero point of 130%, then a bitcoin-backed CDP collateralized at 135% will have a bounty of -5%. Assuming further that the dai market price is equal to the target price, then performing a forced cover of this CDP for 100 SDR worth of dai would only buy 95 SDR worth of BTC, implying a 5% net loss for the buyer.*

When the collateral ratio of a CDP goes below the zero point, the forced cover bounty of the CDP becomes positive. At that point the forced cover can also be thought of as a *margin call*, since it serves the function of closing positions that are deemed too risky. A positive bounty generally causes market forces to instantly margin call the CDP in order to profit on the difference between the cover cost and the collateral value.

>*__Example 5:__ An borrower creates a CDP with 130 SDR worth of BTC as collateral and uses it to issue 100 SDR worth of dai. The BTC/SDR price subsequently falls by 10%, leaving the CDP at 117% collateralization. The bounty is now +13%. A dai holder quickly performs a margin call by paying down 100 SDR worth of debt in order to obtain 113 SDR worth of BTC. The remaining 4 SDR worth of BTC is returned to the borrower.*

In addition to serving as margin calls, the purpose of the forced cover is to provide a market buffer of liquid assets in the form of the collateral assets held in the CDPs, in case the price of dai suddenly drops dramatically due to a shock in demand or supply. The nominal bounty of a CDP is determined in terms of the target price of the dai, while the *effective bounty* changes in response to the market price of the dai. The effective bounty changes with the same magnitude as the market price deviation, but in the opposite direction. This results another negative feedback loop that counteracts sudden price shocks and serves to push the market price of the dai towards its target price.

>*__Example 6:__ Consider a scenario in which we assume that the zero point of bitcoin is 130%, and there are a number of active bitcoin CDPs at 135% collateralization. A large dai selloff suddenly occurs. If the dai market price deviates 6% below the target price, the effective bounty of all CDPs increases by 6%. Thus, a CDP with a collateral ratio of 135% (giving it a nominal bounty of -5%) will see its effective bounty hit +1% (-5% nominal bounty and 6% market price deviation from the target price). A positive effictive bounty will cause the CDPs to be margin called by profit-seeking traders. The resulting margin calls cause the supply of dai to decrease and creates positive pressure on the dai market price, pushing it upwards as the value of the collateral falls.*

When the market price deviates above the target price, the forced cover mechanism has a different effect. The zero point of a collateral asset type also determines its minimum initial collateral ratio when new dai is borrowed. However, like the bounty, this requirement is calculated in terms of the target price, not the market price. Therefore, when the market price increases above the target price, the effective collateral requirement for borrowing dai goes down, increasing the supply of dai and pushing the price down towards the target price.

The Maker Stability Service
---------------------------------------

The biggest risk to the stable value of the dai is the risk of CDP undercollateralization. Should a CDP see a massive price decrease in its collateral to the point where its collateral ratio falls below 100%, there would no longer be enough collateral in the position to buy back the dai it originally borrowed (plus the stability fee). If such undercollateralization events were left unchecked in a significant amount of the outstanding CDPs, it could destroy confidence in the dai and break its stability. margin calls usually prevent undercollateralization from happening, but it always takes some amount of time for profit seeking traders in the market to react. Widespread, sudden undercollateralization of CDPs that happen too fast to be mitigated by margin calls is referred to as a **black swan event**.

To ensure the stability of the dai under all circumstances, Maker provides a stability service that shields the Dai Credit System from black swan events and transfers all risk of undercollateralization to MKR owners. This mechanism is called *Maker Stability Service* and involves three stages: *Maker Bailout*, *emergency debt* and *forced dilution*.

### Maker Bailout - Automatic bailouts of bad debt

Despite the high profit incentive for traders to perform margin calls once the collateral ratio of a CDP falls just a few percentage points below its zero point (giving it a positive effective bounty), there is still a risk of one or more CDPs becoming undercollateralized if a crash in the value of the collateral happens very quickly. Once a CDP becomes undercollateralized, there is no longer any profit incentive for traders to perform a margin call of the CDP and the dai is no longer fully backed, putting the stability of the system at risk.

To solve this, Maker will automatically perform a bailout using emergency debt. emergency debt is backed by the ability of Maker to dilute the MKR supply.

### emergency debt and forced dilution - Automatic MKR dilution to pay for bailouts

To perform Maker bailouts Maker automatically borrows dai backed by emergency debt and uses the newly borrowed dai to perform the bailouts. emergency debt doesn’t require collateral, but is backed by the unique ability of Maker to dilute the MKR supply. There is no limit to the amount of emergency debt that can be borrowed, so when a major black swan event happens the emergency debt instantly grows to the combined size of all CDPs that became undercollateralized.

As soon as Maker assumes emergency debt, Buy&Burn is paused and forced dilution is triggered. The inflation happens continuously at a rate that corresponds to a 100% increase of the total MKR supply per year. The newly borrowed MKR are automatically sold off for dai, which is then used to successively pay down and remove the emergency debt from the system. This process continues until all the emergency debt has been paid down, at which point the system returns to normal and starts building up new reserves in the stability Vault, and resumes Buy&Burn.

How Maker mitigates collateral risk
------------------------------------

Two primary factors determine the risk profile of a *collateral asset type*: market depth, and volatility. While these two factors are related (higher market depth generally implies less volatility) they still contribute separately to the risk profile of the collateral asset type and are managed with separate risk parameters.

### Collateral risk due to low market depth

The impact of market depth on the risk of a collateral asset type is managed through its *debt ceiling*. The debt ceiling of a collateral asset type is the maximum amount of debt that can be backed by it (across all CDPs of the given collateral asset type). Once the debt ceiling for a collateral asset type has been reached, no more dai can be borrowed using that asset as collateral - until some of the existing CDPs are covered. New dai can still be borrowed using other types of collateral).

### Collateral risk due to high volatility

The volatility of a collateral asset type is mitigated using the collateral curve. The collateral curve is defined by the zero point of the collateral asset type, because it has a slope of -1. The zero point gets set at a level where there is enough collateral to ensure that there will be plenty of time where an undercollateralized CDP will have a positive bounty, even if faced with the highest volatility observed for that asset class under normal conditions. Hence, more volatile assets will have higher zero points (allowing for less leverage by borrowers), while less volatile assets will have lower zero points (allowing for more leverage).

How external agents assist Maker
--------------------------------

The mechanics of the Dai Credit System relies on external agents to do mutually beneficial economic interactions with it. External agents are things like individuals, companies, smart devices and other DAOs.

### Keepers - Keeping the system economically efficient

Traders that systematically earn an income from the Dai Credit System by exploiting simple profit opportunities are called keepers. In a general sense, a keeper is an economic agent that contributes to decentralized systems in exchange for built-in rewards. In the context of Maker, keepers perform several important functions:

**margin calling undercollateralized CDPs**

Each keeper is constantly scanning the blockchain for CDPs. When a CDP gets a positive effective bounty, the keeper will immediately perform a forced cover using its dai reserves to profit from the positive bounty.

**Market making the dai around the target price**

Each keeper will want to try to sell dai when the market price is higher than the target price and similarly buy dai when the price is below the target, in order to profit from the known long term convergence towards the target price and make money from the spread.

To make it easy for anyone to act as a keeper, Maker is funding the development of an open source software stack (also called keeper). This will enable anyone to run a server that acts a trading bot and oracle tool to perform the above-mentioned functions. The keeper software is designed to be run on a small device, such as a Raspberry Pi or the Ethereum Computer.

A keeper can aditionally also act as an Oracle by providing a price feed, as described in the following section.

### Oracles - providing external price feeds

Another crucial group of external actors that Maker requires to function are price feed oracles. Oracles are mechanisms that provide information from the outside world onto a blockchain for smart contracts to consume. Maker needs information about the market price of the dai in order to determine its deviation from the target price. It also needs information about the market price of the various assets used as collateral for the dai, in order to determine the bounty for forced covers on CDPs, as well as when a Maker Bailout should be triggered.

As smart contracts are unable to verify external data on their own, oracles are often one of the weakest and most easily attacked part of a DAO. Maker employs mechanisms to reduce oracle risk (the risk of oracles providing incorrect information to the detriment of the system). Most importantly, Maker uses multiple redundant oracle systems and processes the information internally in order to enable the credit system to function normally even if one or more of the price feed oracles are providing incorrect information.

Notable oracle systems in the short term:

**Keeper** is Maker's in-house oracle solution. This type of oracle is chosen by MKR owners through the Maker Governance Process. Keeper oracles will be cheap to run, and a large amount of them can deliver data together as a swarm, providing a high level of redundancy and decentralization.
 
**Oraclize** is an external service that delivers price information directly from centralized exchanges, along with SSL-based cryptographic proofs that the information has not been tampered with. This type of service has a different risk profile than more decentralized oracle models, making it very useful in a portfolio of diversified price feeds.

**Augur** is an example of a DAO that is capable of maintain a reliable decentralized oracle. While it currently does not support realtime price feeds, it may become possible in the future for DAOs to provide price feeds to Maker as a service.

### Custodians - collateral storage specialists

A Custodian is a company (legal entity) that specializes in repackaging legal securities into a format that can be used as collateral for borrowing dai. This is achieved through a unique smart contract called the *custodian trap* which enablopes Maker to give the custodian a debt ceiling based on its internal holdings of legal securities. Custodians enable the system to rapidly respond to demand shocks of dai.

Governance of Maker
-----------------------------------

Authority in DAOs work differently than in traditional organizations. It’s entirely explicit and direct, in the sense that if an entity has the authority to perform an action (e.g. spend funds from the DAO or change a variable in its business logic), it can do so by sending a transaction to a smart contract on the blockchain and the action will unconditionally and irreversibly happen the moment the transaction is confirmed — unless the DAO has specific rules in place to delay it. 

A DAO can both be *dynamic*, meaning that its authority can change any part of its smart contracts and business logic, or it can be *locked*, meaning that parts of its infrastructure are permanently immutable even by the highest authority in the DAO. Locking down all or parts of the business logic of a DAO is useful to help users trust that the DAO will not suddenly alter its service in a detrimental way or steal their funds.

### The Maker Governance Process

*Direct governance* means controlling Maker directly through voting with an Ethereum account that holds MKR. An account gets a vote for each MKR token held. MKR owners who actively vote and participate in governance are called *governors*. A simple majority vote has full authority of the system to change the voting rules, alter the business logic, spend money from the Fund, and locking down Maker's smart contracts as the system matures.

There are four major phases when governors exercise direct governance over Maker through the voting process. 

**The first phase** is deploying and publishing the *action proposal*, a smart contract that will change the status quo of Maker if it gets executed by directly modifying the state of its smart contracts. 

**The second phase** is *initiating* the action proposal for public vote by the governors. This enables governors to vote on the action proposal with their MKR and starts the expiration timer of the action proposal.

**The third phase** is the voting process - voting is done according to the voting rules of the system, that themselves are modifiable until they are locked down by the governance process. Each action proposal has an experiation time after which it is automatically abandoned. 

**The fourth phase** is execution of the *action*, the transaction that modifies the state of the Maker smart contracts.

### Voter organization

An important part of direct governance is voter organization. To make it as straightforward as possible for governors to coordinate their votes and discuss action proposals, a weekly *formal governance meeting* is held as a conference call using the TeamSpeak platform, currently defined to happen every sunday at 15:00 GMT. 

While the contract system allows initiating proposals for vote at any time - during normal conditions it is in practice only done at the governance meeting. If a proposal is initiated for vote outside the social framework of the governance meeting it indicates either an attack on the system, or a breakdown of the governance framework and a potential governance crisis.

All governance related discussion and debate that doesn't take place in the framework of the governance meeting is referred to as *informal governance*. The Maker Slack chatroom and the Maker forum act as the primary communications platforms for shareholders to discuss and debate all aspects of the DAO and its governance, and for governors to schedule governance meetings.

### Governance in action: from idea to action proposal

**Informal governance proposal:** A new proposal will first be brought up and discussed on Slack and the forum - in this setting of public and freeflowing information a proposal will be rapidly scrutinized and any obvious objections will be raised immediately by the community. The proposal can then be amended based on input and objections, or abandoned.

**Formal governance proposal:** Once a proposal has been amended to a form that doesn't have any obvious objections, it can move on to formal governance. Formal governance ensures that every governor is present to weigh the proposal as it is presented in formal parlance that emphasizes the use of simple English with live translation to other major languages. If there is input and objections to the proposal they have to be properly articulated, and if necessary the proposal can be delayed until the next governance meeting to allow another week of informal governance. When a proposal no longer has any formal objections or input, an action proposal has to be created and published for scrutiny so that governors can ensure that it properly implements the spirit of the proposal.

**Direct governance vote:** When the action proposal is considered ready for vote, it is initiated by the proposer and governors can begin the process of voting for or against it. As mentioned above, the initiation has to be done during the governance meeting, or it is considered either an attack or a governance crisis. The process of voting extends beyond the governance meeting where it was proposed, allowing plenty of time for every governor to vote even if they weren't present.

Implementing Maker and the road to decentralization
-----------------------------------

Due to the high security requirements and the many layers of complexity involved, implementing Maker and the Dai Credit System will be a gradual process. To make this process as smooth and efficient as possible, Maker is starting off with a more centralized governance model. Over time, as usage of the system increases, Maker will move towards full decentralization.

### Maker Centralized Alpha: Contract system deployment and token platform

In the earliest live implementation of Maker only the MKR token is live, but implemented without MKR voting or any other behaviour beyond being a regular token with 1,000,000 supply. The ability to propose actions rests with a centralized admin multisig known as the Alpha Dynasty. This lack of decentralization is in place to allow an earlier deployment of the system, and to enable flexibility during its early stages. Authority over the system will still implicitly be held by MKR owners and the Maker Governance Process, and the Alpha Dynasty will be responsible for carrying out the intentions of the Maker Governance Process exactly as described with no formal authority of their own. This should be considered similar to the dynamic between a company’s board of directors and its shareholders, however as there is no explicit legal link in place both the users and the shareholders of the system will have to trust the members of the Alpha Dynasty. For this reason, they are chosen to be the founders and most active and vested community members of Maker.

**Upgrade to Semi-Decentralization**

An early planned upgrade of the system is the implementation of semi-decentralization, which reduces the centralization of the system as it allows MKR owners to vote to block action proposals proposed by the Alpha Dynasty. This significantly reduces the centralization risk of the Alpha Dynasty and means that as long as enough governors are actively voting, no undesirable actions can be passed.

### Dai Alpha: Minimum Viable Product

The first implementation of the dai stablecoin is called the Dai Alpha.

During the Dai Alpha, the Dai Credit System will not be fully implemented. All CDPs will be manually created and their collateral will be managed by the Alpha Dynasty using semi-decentralized action proposals. The rules of dai borrowing and margin calls will be manually enforced by the Alpha Dynasty with simplified mechanics dictated by the governance process.

### Long-term development roadmap

There are several phases on the roadmap after the Dai Alpha. The development will happen in discrete steps, in the following order.

-   **Dai Credit System (Decentralized CDP engine)**

    This feature will allow users to borrow dai directly by interacting with Maker's contracts on the Ethereum blockchain.

    When the CDP engine is deployed, the Maker Stability Service will not yet have been implemented, so the stability of the dai will not be as strong as in the full implementation as there are no automatic bailouts.

-   **Decentralized MKR voting**

    This feature will allow shareholders to fully control the Maker DAO by proposing actions and voting on their execution through a user interface.

    Once this is implemented, the Alpha Dynasty will no longer be necessary and from this point on Maker will have a fully decentralized governance structure.

-   **Maker Stability Service (automatic bailouts and forced dilution)**

    This feature means that Maker will be able to automatically dilute MKR in order to bail out undercollateralized CDPs. The dai will have its stability mechanics fully implemented.

-   **Authority lockdown**

    Once all the features of Maker and the Dai Credit System have been fully implemented, all that’s left to do is to lock down the permissions of the governors.

    This will prevent shareholders from destructive behaviour like attempting to confiscate collateral from the CDPs of dai borrowers. It will also limit how quickly the risk parameters and overall monetary policy of the credit system can be changed, which also prevents destructive behaviour such as using sudden parameter adjustments as an attack vector.

    The end result is maximized decentralization and resilience of the dai stablecoin.

Features of Ethereum
----------------

### Transactions

In the short term Ethereum transactions have an average block time of around 12 seconds, with at least several blocks required before a transaction can be considered confirmed. Transaction fees in the form of gas have to be paid in Ether.

In the long term, after the switch to Ethereum Serenity, the confirmation time of transactions will move to become a few seconds, practically appearing to be instant. Transaction fees will be payable in any asset, including dai.

### Privacy

At the switch to Serenity, Ethereum will be upgraded to have advanced support for ring signature transactions. Ring signatures are able to provide near perfect anonymity for token transfer between accounts. The implementation of this feature will give the dai the same level of anonymity as Monero, one of the most popular privacy focused cryptocurrencies.

### AML and KYC

KYC services native to the Ethereum blockchain are being developed by multiple high profile blockchain development companies, which makes it easy for dai users to be in compliance with regulations on AML and KYC in their jurisdictions, if applicable.