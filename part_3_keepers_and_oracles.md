---
permalink: /keepers-and_oracles/
layout: page
title: Keepers and oracles
---

## Keepers

The mechanics of the Dai Credit System relies on rational actors to interact and trade with the system in ways that is profitable to themselves &mdash; such as margin calling CDPs with low collateral. Traders that systematically earn an income from the credit system by exploiting such opportunities are termed *keepers*. In a general sense, a keeper is an economic agent that contributes to a decentralized system in exchange for built-in rewards. In the context of Maker, keepers perform several important functions:

* Margin calling undercollateralized CDPs. Each keeper is constantly scanning the blockchain for CDPs. As soon as it finds a CDP with a positive effective bounty, it will immediately perform a forced cover using its dai reserves to earn the bounty. It will then proceed to sell the obtained collateral asset on a market in order to keep its dai balance growing and not suffer undue exposure to other assets.

* Market making the dai around the target price. Each keeper will want to try to sell dai when the market price is higher than the target and buy dai when the price is lower than the target, in order to profit on the spread.

* Acting as an oracle by providing a price feed. (More information about this is given below.)

To make it easy for anyone to act as a keeper, Maker is funding the development of an open source software stack (called Keeper). This enables anyone to run a server that acts a trading bot and oracle tool to perform the above-mentioned functions. The Keeper software is designed to be run on a small device, such as a Raspberry Pi or the so-called Ethereum Computer.

## Oracles

Another crucial group of external actors that the credit system requires to function are the price feed oracles. Oracles are mechanisms that provide information from the outside world onto a blockchain for smart contracts to consume. Maker needs information about the market price of the dai in order to determine its deviation from the target price. It also needs information about the market price of the various assets used as collateral for the dai, in order to determine the bounty for forced covers on CDPs, as well as when a Maker bailout should be triggered.

As smart contracts are unable to verify external data on their own, oracles are often the weakest and most easily attacked part of a DAO. Maker employs mechanisms to reduce *oracle risk* (the risk of oracles providing incorrect information to the detriment of the system). Most importantly, Maker uses multiple redundant oracle systems and processes the information internally in order to enable the credit system to function normally even if one or more of the price feed oracles are providing incorrect information.

Maker will initially use these oracle systems:

* Keeper. As Maker's in-house oracle solution, this type of oracle is chosen by MKR owners through Maker's regular governance mechanisms. Keeper oracles will be cheap to run, and a large amount of them can provide data together as a swarm, providing a high level of redundancy and decentralization.

* Oraclize. An external service that runs on Ethereum and delivers price information along with SSL-based cryptographic proofs that the information has not been tampered with. Oraclize provides a secondary source of information for the market price of assets, signed by the webservers of the centralized exchanges themselves.

<div class="pagination">
    <a class="pagination-item older" href="/docs/dai-credt-system/">Part 2</a>
    <a class="pagination-item newer" href="/docs/governance-and-decentralization/">Part 4</a>
</div>
