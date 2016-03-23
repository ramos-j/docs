---
permalink: /custodians/
layout: page
title: Custodians
---


## Linking the global economy with the Dai Credit System

Custodians are legal entities (incorporated companies), registered in national jurisdictions around the world, that perform vital functions to ensure the stability and economic efficiency of the Dai Credit System.

At its core, a Custodian is an entity that has special issuance privileges given to it by the Maker governance process. These issuance privileges mean that a Custodian can back its dai issuance with internally held collateral (i.e. held on the company’s books and accounts) rather than held as locked collateral on the Ethereum blockchain.

This can be done in an cryptoeconomically secure manner based on the Maker Governance Process enforcing five main requirements:

### Reserve Buffer

A Custodian that receives a debt ceiling from Maker and uses it to issue Dai to sell in order to hold other assets needs to be able to withstand volatility in these other assets that it holds. Because of this, it is required that a Custodian always maintains a minimum buffer of capital that ensures it stays solvent even if there are price swings in the assets it holds. The reserve buffer is similar in nature to the zero point of CDP’s, as it the excess capital the Custodian must hold (equivalent to collateralization above 100% in CDPs)

>*__Example 1__*: A group of investors form a new Custodian in Singapore, and initially inject 50,000 USD worth of capital into the Custodian, held in its Singapore bank account. The Maker Governance Process has decided that the Custodian Reserve Buffer requirement is 20% of Issuance Debt. This means that the 50,000 USD reserve buffer would give the Custodian a maximum debt ceiling of 250,000 USD. If the Custodian issued all the Dai at once and sold them off for other assets, it would end up with a total capital pool of 300,000 USD, and 250,000 USD debt.

### Custodian Trap

The Custodian Trap is a special smart contract that gives Maker “lethal leverage” against a Custodian, should the Custodian be unable to pay down its Issuance Debt within a short timeframe. A Custodian trap usually holds two types of assets: 1) the vast majority of legal stock in the Custodian company is held in escrow in the Custodian Trap 2) MKR individually provided by investors or partners of the Custodian.

The existence of the Custodian trap ensures that a Custodian is forced to always remain liquid and able to cover all of its debt at once with short notice. It also means that a Custodian cannot profitably walk away from its debt, and generally means that Custodians do not need to be .

>*__Example 2__*: A Custodian in Singapore uses a legal security gateway service to allow it to track its shares on the Ethereum blockchain. The Custodian then creates a Custodian Trap smart contract and puts 90% of its stock in it. According to negotiations with the Maker Governance Process, the Custodians trap is set to have a delay of 1 month. If the Custodian later does not fulfill its obligations to maker regarding the size of its reserve buffer relative to its debt, Maker is able to spring the trap, and force the Custodian to pay down all of its debt within 1 month. If all of the debt isn’t paid off within a month, the 99% of the Custodians share total share supply are auctioned off to the highest bidder or bidders (which also means a claim to 99% of the Custodians’ assets) and the proceeds of this sale is then used to pay down the Custodians debt.

### Diversified Portfolio

A Custodian needs to hold a portfolio of stable and sustainable assets, with an aggregate volatility that is low enough to ensure the reserve buffer will always be enough to cover market swings. Custodians will generally want to target a portfolio composition that gives them a higher yield than what they have to pay in issuance costs.

### Total Public Transparency

In order for the Maker Governance Process to be able to properly determine if a Custodian is solvent and adhering to the reserve buffer requirements, it is necessary for Custodians to have the entirety of their accounting completely public and transparent, with real time audits available by anyone at any time. In addition to the general, passive requirement of total transparency and total information availability, Custodians also need to actively present a summary of their positions as well as all changes since last presentation, at a time near the governance meeting, in order to maximize the accessibility of the information to Maker stakeholders.

### Graceful Exit

At all times, a Custodian needs to have a clear, publicly available plan that details exactly how it could wind down its positions and pay off its debt in a manner that doesn’t result in significant loss of funds or delays due to liquidity issues, regulatory problems or other factors. As a part of this process the Custodian needs to prove that it is able to pay down its issuance debt well within the Custodian trap delay period. Exiting gracefully is important in case of a conflict between a Custodian and its host jurisdiction happens, such as if a country decides to ban the Dai Credit System, in which case it will be impossible for a Custodian to operate legally.

## Competitively awarding debt ceilings

The key to ensuring that custodians are incentivized to not just fulfill but actively improve the security offered by the five Custodian requirements listed above, is to foster a competitive environment where those custodians that show ability to actively pursue the spirit of the requirements are favored when debt ceilings are raised by the Maker Governance Process.

## The face of Maker to the incumbents

Custodians creates a contact surface with which Maker can interact with incumbent institutions around the world that can impact its growth and stability, most importantly governments. As custodians are owned and run individual people, they can use their personal connections, trust and reputation to secure Maker an inroad to partnerships that normally would be out of reach to a DAO, such as financing joint ventures with governments or coordinate with governments to funnel money to strategic sectors, in return for public support. Seeking and maintaining relationships and shared interests with governments and public institutions is going to be crucial to ensure that the rise of Maker and the proliferation of the Dai is taken as a positive by the incumbents, and that they will not budge to protectionist urges by vested interests that stand to be disrupted.


<div class="pagination">
    <a class="pagination-item older" href="/docs/mkr-distribution-and-the-mkr-fund/">Part 5</a>
    <span class="pagination-item newer">…</span>
</div>
