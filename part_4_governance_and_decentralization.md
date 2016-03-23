---
permalink: /governance-and-decentralization/
layout: page
title: Governance and decentralization
---

## Authority in Decentralized Autonomous Organizations

Authority in DAOs work differently than in traditional organizations. It is entirely explicit, and direct, in the sense that if an entity has the authority to spend funds from the DAO or change a variable in the business logic it can be done by sending a transaction to a smart contract on the blockchain, and the action will immediately happen (except in cases where the DAO has rules in place to delay it). A DAO can be fully modifiable, meaning that its authority can change any part of its smart contracts and business logic, or it can be restricted, with parts of its infrastructure permanently locked down and unmodifiable, even by the DAOs authority. Restricted authority is useful to help users trust that the DAO will not suddenly alter its service in a detrimental way, or steal their funds.

In the Maker DAO, the highest authority to modify and control the system resides with the owners of the MKR token, the Maker shareholders. The power is exercised through the shareholders voting on actions, with each MKR giving one vote. A simple majority vote is able to change the voting rules, altering the business logic, spending funds, or permanently restricting the DAO authority.

## Governance processes in Maker

To allow shareholders to coordinate their votes and discuss regulatory and business strategies, a weekly governance meeting is held as a conference call using the teamspeak platform. While initiating proposals and voting on them can be done at any time, the framework of the governance meeting makes it easier for shareholders to do so in an organized and systematic fashion.

The Maker Slack channel functions as the primary communications platform, upon which the governance meeting is scheduled and shareholders can discuss any and all aspects of the DAO and its governance.

## The road to decentralization.

Implementing Maker and the Dai Credit System will be a gradual process due to the high security requirements and many layers of complexity involved. To make the process as smooth and efficient as possible, Maker will start off with a more centralized governance model, and will move towards full decentralization over time as usage of the system increases.

### The Dai Alpha

In the earliest live implementation of Maker, called the Dai Alpha, MKR voting is not implemented and the authority over the system is instead held by a central group of people known as the Alpha Dynasty. This lack of decentralization is in place to enable flexibility during the early stages of the system, as well as allow deployment of the system sooner. Authority over the system is still implicitly held by MKR owners, with the Alpha Dynasty explicitly carrying out their will, similar to the dynamic between a board of directors and shareholders in a real company.

During the Dai Alpha, the Dai Credit System will not be fully implemented in a decentralized form either. CDPs will be manually created and their collateral will be held by the Alpha Dynasty in multi signature smart contracts, with the rules of the Dai Credit System manually enforced by the Alpha Dynasty. The process will be fully transparent and verifying the stability and collateralization of the Dai will be as simple as in the full implementation, but Dai users, as well as Maker shareholders, will have to trust the members of the Alpha Dynasty. For this reason they are chosen to be the founders and most active community members of the Maker DAO.

### Implementation steps

There are several phases after the Dai alpha that will be implemented in discrete steps in the following order.

**Decentralized CDP engine**. When it is deployed CDPs will no longer have to be created manually, and users can issue Dai directly by interacting with the CDP engine smart contracts on the blockchain. The CDP engine will not have Maker Insurance so the stability of the Dai will not be as strong as with the full implementation of the Dai Credit System. As there is still no MKR voting when the CDP engine is implemented, the Alpha Dynasty will still be Makers authority and shareholders and users will need to trust them.

**MKR voting**. This feature will allow shareholders to fully control the Maker DAO by proposing actions and voting on their execution through a user interface. With this implemented the Alpha Dynasty will no longer be necessary and Maker will have decentralized governance.

**Maker Insurance**. This feature means that Maker will be able to automatically inflate the MKR supply in order to bail out CDPs. When it is implemented the Dai will have full stability and strong decentralization.

**Authority lockdown**. When the features of the Dai Credit System have been fully implemented, all there is left is to lock down the permissions of the Maker authority, which is now controlled by MKR shareholders. Doing this will make it impossible for shareholders to confiscate collateral from the CDPs of Dai issuers, and will limit how quickly the risk parameters and monetary policy of the Dai Credit System can be changed. The end result is maximized decentralization and resilience of the Dai stablecoin.

## Long term governance

In beginning of the Dai Credit System its risk parameters and monetary policy will be controlled on a day to day basis by a dynasty, a group of people having central control over the system but supervised by MKR shareholders and with restricted permissions. In the long run the day to day governance of the system will be managed by decentralized prediction markets according to the concepts of futarchy governance. This way Maker will be fully governed by the free market down the level of day to day decisions.


<div class="pagination">
    <a class="pagination-item older" href="/docs/keepers-and-oracles/">Part 3</a>
    <a class="pagination-item newer" href="/docs/mkr-distribution-and-the-mkr-fund/">Part 5</a>
</div>
