---
permalink: /keepers-and_oracles/
layout: page
title: Keepers and oracles
---

## Keepers

The mechanics of the Dai Credit System relies on rational actors to interact and trade with the system in a way that is profitable to themselves, such as when margin calling CDPs with low collateral. Traders that systematically earn an income from the Dai Credit System by exploiting such opportunities are called **Keepers**. Generalized, a Keeper is an economic agent that contributes to a decentralized system in exchange for built-in rewards. Specifically for Maker this means performing several important functions:

* Margin calling undercollateralized CDPs. A keeper constantly scans the blockchain for CDPs and if it finds a CDP with a positive effective bounty, the Keeper immediately uses its Dai reserves to perform a forced cover to earn the profit from the positive bounty, and then sells the obtained collateral asset on a market in order to keep its Dai balance growing and not suffer undue exposure to other assets.

* Market making the Dai around the Target Price, selling Dai when the market price is higher than the Target Price and buying Dai when the market price is lower than the Target Price.

* Acting as an oracle by providing a price feed to Maker. More information about oracles given below.

To make it easy for anyone to act as a keeper, Maker funds the development of the open source Keeper software stack, which enables anyone to run a server that acts a trading bot and oracle tool to perform the above mentioned functions. It is designed to be run on a small device, such as the Ethereum Computer or a regular raspberry pi.

## Oracles

Another crucial group of external actors that the Dai Credit System requires to function are price feed oracles. Oracles are mechanisms that provide information from the outside world onto a blockchain for smart contracts to consume. For Maker this means price information regarding the market price of the Dai, to determine if it is deviating from the Target Price, as well as information about the market price of the assets used as collateral for the Dai, to determine the bounty for forced covers on CDPs and when a Maker bailout can be triggered.

As smart contracts are unable to verify external data on their own, oracles are often the weakest and most easily attacked part of a DAO. Maker employs mechanisms to reduce **oracle risk**, the risk of oracles providing incorrect information to the detriment of the system. Most importantly, Maker uses multiple redundant oracle systems to deliver its price information, which are processed by Maker to enable the system to function normally even if one or more of the oracle systems are providing incorrect information.

Maker will initially use these oracle systems:

* Keeper, as Makers in house oracle solution this type of oracle is chosen by MKR owners through Makers regular governance mechanisms. Keeper oracles will be cheap to run, and a large amount of them can provide data together as a swarm, giving a high level of redundancy and decentralization.

* Oraclize, an external oracle solution that delivers price information as well as SSL-based cryptographic proof that the information has not been tampered with from its source. Oraclize provides a secondary source of information regarding the market price of assets signed directly by the exchanges.

[//]: <> Pagination - quick & dirty
[//]: <> // TODO Pagination


<div class="pagination">
    <a class="pagination-item older" href="/docs/dai-credt-system/">Part 2</a>
    <a class="pagination-item newer" href="/docs/governance-and-decentralization/">Part 4</a>
</div>