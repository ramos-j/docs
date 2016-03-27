---
permalink: /dai-credit-system/
layout: page
title: The Dai Credit System
---

## Issuance and supply

The dai is a cryptocurrency on the Ethereum blockchain. Any Ethereum account can hold dai and can transfer it freely to any other account.

When the credit system is initially deployed in early 2016, the value of the dai will be pegged to a target price of 0.73 SDR. The SDR (Special Drawing Right) is an international currency basket maintained by the International Monetary Fund (IMF). Over time, however, the target price will increase, resulting in long-term deflation.

The supply of dai tokens is controlled through a decentralized issuance scheme that allows anyone to issue new dai, while at the same time ensuring that the market price remains stable around the target price. Issuing new dai is done by locking a certain amount of collateral in a smart contract called a *collateralized debt position* (CDP), which holds the *issuance collateral* as well as the *issuance debt*. When a CDP issues dai, the issuance debt is initially set to equal the amount of newly issued dai. Over time, the CDP accrues an *insurance fee*, causing the issuance debt to increase. At any time, the issuer can retrieve the collateral by the issuer by paying down (“covering”) the issuance debt plus whatever insurance fee has been accrued so far. This returns the collateral to the issuer and deletes the CDP. The insurance fee goes into a vault which is used as a first line of defense in the event that Maker needs to bail out bad debt.

>*__Example 1__: An issuer wishes to issue 100 dai, so he locks into a CDP an amount of bitcoin worth significantly more than 100 dai ("excess collateral"). The insurance rate is 2%, so when he wants to retrieve his bitcoins one year later, he will need around 102 dai to cover the CDP.*

The deflationary nature of the dai means that the market value (in SDR) of the issuance debt will also increase over time. Therefore, when calculating the total effective cost, a dai issuer needs to take this into consideration in addition to the insurance fee. The deflation is a transfer of value from dai issuers to dai holders (as payment for borrowing capital), while the insurance fee is a transfer of value from dai issuers to MKR holders (as payment for insuring the collateral).

Issuing dai can be thought of as borrowing capital from the credit system. In practice, the issuer is either seeking to take a leveraged long position on the asset used as collateral ("margin trading"), or else is seeking liquidity in a hard currency without selling the asset used as collateral  (for example, a business collateralizing its own stock in order to raise short-term liquidity for operational expenses).

In both cases, the way the issuer obtains the asset he actually desires is by creating a CDP to obtain dai and then selling the dai on the open market. (On the other side of the trade, buyers will want to obtain dai in order to use it as a stable cryptocurrency or simply to earn capital gains from the long-term deflation.)

>*__Example 3__: An issuer wishes to go margin long on the BTC/SDR pair, so she issues 100 SDR worth of dai by posting 150 SDR worth of BTC to a CDP. She then turns around and buys another 100 SDR worth of BTC with her newly issued dai, putting her at a net 1.66&times; BTC/SDR exposure. She's free to do whatever she wants with the 100 SDR worth of BTC she obtained by selling her dai, while the original BTC held as collateral (150 SDR worth) remains locked until the issuance debt plus the insurance fee is covered.*

Although CDPs are not fungible with each other, the ownership of any one particular CDP is transferable. This allows CDPs to be used in smart contracts that perform more complex methods of issuance (for example, involving more than one actor).

>*__Example 4__: Alice and Bob come together using an Ethereum OTC contract to issue 100 SDR worth of dai backed by bitcoins. Alice contributes 50 SDR worth of bitcoins while Bob contributes 100 SDR worth. The OTC contract takes the funds and creates a CDP, thus issuing 100 SDR worth of dai. The newly issued dai are automatically sent to Bob, who thereby effectively ends up simply buying 100 SDR worth of dai for the equivalent amount of BTC. The contract then transfers ownership of the CDP to Alice, meaning she ends up with 100 SDR worth of issuance debt (denominated in dai) and 150 SDR worth of collateral (denominated in bitcoins). Since she started with only 50 SDR worth of bitcoins she is now 3&times; leveraged long BTC/SDR.*

## Price stability

The stability of the dai around the target price is maintained by continuously matching demand between issuers and holders using *deflation rate adjustment*. The forced cover mechanism directly enforces the target price on the open market using collateral from CDPs. It also ensures short-term liquidity and price support in the face of dai demand shocks.

### Long-term price stability

Deflation rate adjustments ensure that the dai market price remains stabilized around the target price.

When the market price of the dai is below the target price, the deflation rate of the dai increases, causing issuance to become more expensive and  thus leading to a corresponding reduction in supply. At the same time, the increased deflation rate causes the capital gains from holding dai to go up, thus leading to a corresponding increase in demand. This combination of reduced supply and increased demand causes the dai to appreciate in value, pushing it up towards the target price.

The same mechanism works in reverse if the market price is higher than the target price. The deflation rate decreases, which leads to an increased demand for issuing dai and a decreased demand for holding it. This causes the dai to depreciate in value, pushing it down towards the target price.

This mechanism is a form of negative feedback loop: any deviation away from the target price triggers a push in the opposite direction. The magnitude of the deflation rate adjustments depend on how strongly the market price deviates from the target price, so that strong deviations result in aggressive adjustments while small deviations result in tiny adjustments.

### Short-term liquidity and price support

To directly enforce the target price in the dai markets and to counteract demand shocks, a secondary stability mechanism exists: the forced cover.

Under normal market conditions every dai in existence is backed by an excess of collateral locked in various CDPs. The collateralization ratios (i.e., how much collateral any given CDP contains, as compared to its debt) can be verified cryptographically on the Ethereum blockchain.

A dai token represents an insured claim to the collateral contained in the credit system's CDP portfolio. A dai holder can enforce this claim through the forced cover mechanism, which works by having the holder pay down the debt on behalf of a CDP issuer, and thus buying a portion of the collateral. The amount of collateral that the forced cover buys is determined relative to a price feed. Any leftover collateral is returned to the issuer and the CDP is then deleted.

The cost of doing a forced cover on a properly collateralized CDP comes in the form of a *negative bounty*. This means that the dai holder has to pay a higher price per unit of collateral relative to the target price (note: not the market price).

The bounty varies based on the collateralization of the CDP subject to the forced cover: well-collateralized CDPs have lower (more negative) bounties. All CDPs have a *collateral curve*, which is a function that determines the bounty based on the collateralization. This curve is defined based on the *zero point*, the collateralization percentage at which the bounty is zero. The zero point is different for each type of collateral: riskier or more volatile asset classes have higher zero points, while safer or less volatile assets have lower zero points.

The slope of the collateral curve will initially &mdash; for simplicity reasons &mdash; be set to approximately 1.0, meaning that a 1% movement in collateralization (in either direction) would produce a corresponding 1% change in the forced cover bounty.

>*__Example 5__: If we assume that bitcoin has a zero point of 130%, then a bitcoin-backed CDP collateralized at 135% will have a bounty of -5%.
Assuming further that the dai market price is equal to the target price,
then performing a forced cover of this CDP for 100 SDR worth of dai would only buy 95 SDR worth of bitcoins, implying a 5% net loss for the buyer.*

As the collateralization ratio of a CDP goes below the zero point, its forced cover bounty becomes positive. At this point &mdash; since it now has the function of closing out positions that are too risky &mdash; the forced cover can be thought of as a margin call. The positive bounty will generally cause market forces to instantly margin call the CDP in order to earn the difference between the cover cost and the collateral value as free profit.

>*__Example 6__: An issuer creates a CDP with 130 SDR worth of BTC as collateral and uses it to issue 100 SDR worth of dai. The price of BTC subsequently falls 10%, leaving the CDP at 117% collateralization. The bounty is now +13%. A dai holder quickly performs a margin call by paying down the 100 SDR debt to obtain the 113 SDR worth of BTC, leaving only the remaining 4 SDR worth of BTC to be returned to the issuer.*

The purpose of the forced cover is to provide a buffer of liquid assets from the CDPs in case the price of dai suddenly drops dramatically due to a shock in demand. This is because the bounty of a CDP is determined in terms of the target price of the dai, while the *effective bounty* changes in response to the market price of the dai. The effective bounty changes with the same magnitude as the market price deviation, but in the opposite direction. This creates another negative feedback loop that serves to push the market price towards the target price.

>*__Example 7__: Consider the scenario where there are active bitcoin CDPs at 135% collateralization and a large dai selloff suddenly occurs. If the dai market price deviates more than 5% below the target price, then the effective bounties of all CDPs will increase by more than 5%. Thus, a CDP with 135% collateralization (or lower) which has a nominal bounty of -5% will see its effective bounty hit 0% (or higher), causing it to be margin called by profit-seeking traders. This causes the supply of dai to decrease and creates positive pressure on the dai market price, pushing it upwards.*

When the market price deviates above the target price, then the forced cover mechanism has a different effect. The zero point of a collateral type is also the minimum initial collateralization requirement for issuing new dai, but (like the bounty) this requirement is calculated in terms of the target price. Therefore, when the market price increases, the effective collateral requirement for issuing dai go down, thus increasing the supply of dai and pushing the price down in the direction of the target price.

## Undercollateralization

The biggest risk to the stable value of the dai is the risk of CDP undercollateralization. Should a CDP see a massive price decrease in its collateral to the point where its collateralization ratio falls below 100%, then there would no longer be enough collateral in the position to buy back all the dai it originally issued (plus the insurance fee). If such undercollateralization events were left unchecked and allowed to happen to a significant amount of the outstanding CDPs, this could destroy confidence in the dai and break its stability. (Widespread, sudden undercollateralization that happens too fast to be mitigated by margin calls is sometimes referred to as a "black swan event.")

To ensure the stability of the dai under all circumstances, Maker provides an insurance service that shields the credit system from black swan events by transferring the losses to MKR holders through three mechanisms: *Maker bailout*, *emergency debt* and *forced MKR inflation*.

### Maker bailout

Despite the massive profit incentive for traders to perform margin calls once the collateralization of a position falls just a few percentage points below its zero point (giving it a positive bounty), there is still a risk of one or more CDPs becoming undercollateralized if the crash happens very quickly. Once a CDP becomes undercollateralized, there is no longer any profit incentive for traders to perform a margin call.

Instead, in this case, Maker will autonomously perform a bailout using funds stored in its emergency vault. This vault receives the insurance fees paid out from CDPs when they are covered and thus normally has a pool of funds readily available to quickly perform a bailout.

### Emergency debt

Should too many CDPs become undercollateralized simultaneously to the point where there isn’t enough dai in the emergency vault to bail them all out, then in this case Maker automatically issues dai backed by emergency debt and uses that to perform the bailouts. Emergency debt doesn’t require collateral but is backed by the ability of Maker to inflate the MKR supply. There is also no limit to the amount of emergency debt that can be issued, and it will always correspond to the combined debt of the CDPs that were undercollateralized when the emergency debt was initially triggered.

### Forced MKR inflation

Once Maker assumes emergency debt, forced MKR inflation gets triggered. The inflation is continuous at a rate that corresponds to a 100% increase of the MKR supply per year. The inflated MKR is automatically sold off for dai, which is used to successively pay down and remove the emergency debt. This process continues until all the debt has been paid down, at which point the system returns to normal and immediately starts building up new emergency reserves once again.

### The function of MKR

The market value of MKR is what ultimately insures the collateral of the credit system. As such, the price of MKR is directly exposed to the risk of the whole system. To compensate MKR owners for taking on this risk, during times of stability (when there is no outstanding emergency debt), the dai held in the emergency vault is slowly sold off for MKR. The MKR thus obtained is permanently destroyed in an automatic process called *buy and burn*. The rate at which buy and burn happens is determined by MKR holders through voting. The result (in the absence of undercollateralization events) is a successive decrease in the supply of MKR, causing its price to increase.

## Collateral requirements and debt ceilings

Two primary factors determine the risk of a given collateral type: market depth, and volatility. While these two factors are related (higher market depth generally means less volatility) they still contribute separately to the overall risk and are thus each managed with a separate mechanism.

### Market depth risk management

The impact of market depth on the risk of a given collateral type is managed through its *debt ceiling*. The debt ceiling of an asset class is the maximum amount of issuance debt that can be held in CDPs which are collateralized by that kind of asset. Once the debt ceiling for any given asset class has been reached, then no more dai can be issued using that kind of asset as collateral until some of the existing CDPs are covered. New dai can still be issued using different kinds of assets as collateral.

### Volatility risk management

The volatility of a given type of collateral is managed through its collateral curve, defined by the zero point. The zero point is set in such a way so as to ensure that the collateral buffers of the CDPs are sufficient to have a positive bounty (and thus get margin called) even in times of the highest volatility observed for the asset class under normal conditions. Hence, more volatile assets will have higher zero points, allowing for less leverage by issuers, while less volatile assets will have lower zero points, allowing for more leverage.


<div class="pagination">
    <a class="pagination-item older" href="/">Part 1</a>
    <a class="pagination-item newer" href="/docs/keepers-and_oracles/">Part 3</a>
</div>
