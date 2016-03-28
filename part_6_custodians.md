---
permalink: /custodians/
layout: page
title: Custodians
---


## Linking the global economy with the Dai Credit System

Custodians are legal entities (incorporated companies), registered in national jurisdictions around the world, that perform vital functions to ensure the stability and economic efficiency of the Dai Credit System.

At its core, a custodian is an entity that has special issuance privileges given to it by Maker's governance process. These issuance privileges mean that a custodian can back its dai issuance with collateral which is held internally (i.e., on the company’s books and accounts), rather than as locked collateral on the Ethereum blockchain.

This can be done in an cryptoeconomically secure manner by ensuring that the governance process enforces five main requirements:

### Reserve buffer

If a custodian receives a debt ceiling from Maker and uses it to issue dai in order to trade it for other assets, then the custodian needs to be able to withstand the volatility of these other assets. Therefore, a custodian must always maintain a minimum *reserve buffer* of capital, which ensures that it stays solvent even when there are price swings in its assets. The reserve buffer of a custodian is comparable to the zero point of a CDP.

>*__Example 1__*: A group of investors form a new custodian in Singapore and initially inject $50,000 USD worth of capital into its Singapore bank account. The Maker governance process has decided that the custodian reserve buffer requirement is 20% of issuance debt, giving the custodian a maximum debt ceiling of $250,000 USD. If the custodian issued all the dai at once and sold them off for other assets, it would end up with a capital pool worth a total of $300,000 USD, along with $250,000 USD worth of debt.

### Custodian trap

The custodian trap is a special smart contract that gives Maker "lethal leverage" against a custodian, should the custodian be unable to pay down its issuance debt within a short timeframe. A custodian trap usually holds two types of assets: either the vast majority of legal stock in the custodian company, or else MKR tokens individually provided by investors or partners of the custodian.

The existence of the custodian trap ensures that the custodian is forced to always remain liquid and able to cover all of its debt at once with short notice. It also means that a custodian cannot profitably walk away from its debt. This keeps the counterparty risk at a reasonable level as there is no incentive for the custodian to attack Maker.

>*__Example 2__*: A custodian in Singapore uses a legal security gateway service to allow it to track its shares on the Ethereum blockchain. The custodian then creates a custodian trap smart contract and puts 90% of its stock in it. According to negotiations with the Maker governance process, the custodian's trap is set to have a delay of one month. If the custodian later does not fulfill its obligations to Maker regarding the size of its reserve buffer relative to its debt, then Maker is able to spring the trap, forcing the custodian to pay down all of its debt within one month. If after a month the debt still has not been paid off, then the shares in the custodian are auctioned off to the highest bidder. (Note that the custodian shares also represent a claim to 90% of the custodian's assets.) The proceeds of this sale is then used to pay down the custodian's debt.

### Diversified portfolio

Every custodian must hold a portfolio of stable and sustainable assets, with an aggregate volatility that is low enough to ensure that the reserve buffer will always be enough to cover price swings. Custodians will generally want to target a portfolio composition that gives them a higher yield than what they have to pay in issuance costs.

### Total public transparency

In order for the Maker governance process to be able to properly determine whether a custodian is solvent and adhering to the reserve requirements, it will be necessary for custodians to have the entirety of their accounting completely public and transparent in such a way that real time audits are available to be performed by anyone at any time. In addition to this general requirement of total transparency and total information availability, in order to maximize the accessibility of the information to MKR stakeholders, each custodian must also actively present, at a time near each governance meeting, a summary of its positions as well as any changes since the last presentation.

### Graceful exit

At all times, a custodian needs to have a clear, publicly available plan that details exactly how it could wind down its positions and pay off its debt in a manner that doesn’t result in significant loss of funds or delays due to liquidity issues, regulatory problems or other factors. As part of this process, the custodian must prove its ability to pay down its issuance debt well within the delay period of its custodian trap. The ability to exit gracefully is important in the case where a conflict occurs between a custodian and its host jurisdiction. (For example, a country may decide to try to ban the Dai Credit System, making it difficult or impossible for a custodian to operate legally.)

## Competitively awarding debt ceilings

Ideally, custodians should be incentivized not just to fulfill but in fact to actively improve the security provided by the requirements listed above. The key to achieving this will be to foster a competitive environment in which, when debt ceilings are raised by the Maker governance process, those custodians are favored who have demonstrated an ability to actively pursue the spirit of the custodian requirements.

## The face of Maker to the incumbents

Custodians create a contact surface with which Maker can interact with the incumbent institutions around the world which are able to impact Maker's growth and stability &mdash; most importantly, governments. As custodians are owned and run individual people, they can use their personal connections, trust and reputation to secure Maker an inroad to partnerships that normally would be out of reach to a DAO. For example, financing a joint venture with a government, or coordinating with governments to funnel money into strategic sectors in return for public support of Maker. Seeking and maintaining relationships and shared interests with governments and public institutions will be crucial in order to ensure that the rise of Maker and the proliferation of the dai is seen as a positive development by the incumbents, and that they will not budge to protectionist urges by vested interests that stand to be disrupted.


<div class="pagination">
    <a class="pagination-item older" href="/docs/mkr-distribution-and-the-mkr-fund/">Part 5</a>
    <span class="pagination-item newer">…</span>
</div>
