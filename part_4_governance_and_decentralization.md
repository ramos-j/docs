---
permalink: /governance-and-decentralization/
layout: page
title: Governance and decentralization
---

## Authority in decentralized autonomous organizations

Authority in DAOs work differently than in traditional organizations. It's entirely explicit and direct, in the sense that if an entity has the authority to spend funds from the DAO or change a variable in its business logic, it can do so by sending a transaction to a smart contract on the blockchain and the action will immediately, unconditionally, and irreversibly happen &mdash; unless of course the DAO has rules in place to delay it. A DAO can be fully modifiable, meaning that its authority can change any part of its smart contracts and business logic, or it can be restricted, meaning that parts of its infrastructure are permanently locked down and unmodifiable even by the DAOs owners. Restricted authority is useful to help users trust that the DAO will not suddenly alter its service in a detrimental way, steal their funds, etc.

In the Maker DAO, the highest authority to modify and control the system resides with the owners of the MKR token &mdash; the Maker shareholders. The power is exercised through the shareholders voting on actions, with each MKR giving one vote. A simple majority vote is able to change the voting rules, altering the business logic, spending funds, or permanently restricting the DAO authority.

## Governance processes in Maker

To allow shareholders to coordinate their votes and discuss regulatory and business strategies, a weekly governance meeting is held as a conference call using the TeamSpeak platform. While initiating proposals and voting on them can be done at any time, the framework of the governance meeting makes it easier for shareholders to do so in an organized and systematic fashion.

Maker's Slack account functions as the primary communications platform for the shareholders to schedule governance meetings as well as discuss any and all aspects of the DAO and its governance.

## The road to decentralization

Due to the high security requirements and the many layers of complexity involved, implementing Maker and the Dai Credit System will be a gradual process. To make this process as smooth and efficient as possible, Maker is starting off with a more centralized governance model. Over time, as usage of the system increases, Maker will move towards full decentralization.

### The Dai Alpha

In the earliest live implementation of Maker, called the Dai Alpha, MKR voting is not implemented and the authority over the system is instead held by a central group of people known as the Alpha Dynasty. This lack of decentralization is in place to allow an earlier deployment of the system, and to enable flexibility during its early stages. Authority over the system will still implicitly be held by MKR owners, whereas the Alpha Dynasty will simply be carrying out their will &mdash; similar to the dynamic between a company's board of directors and its shareholders.

During the Dai Alpha, the credit system will also not be fully implemented in a decentralized form. All CDPs will be manually created and their collateral will be held by the Alpha Dynasty in multisig smart contracts. The rules of the credit system will be manually enforced by the Alpha Dynasty. The process will be fully transparent and verifying the stability and collateralization of the dai will be as simple as in the full implementation. However, both the users and the shareholders of the system will have to trust the members of the Alpha Dynasty. For this reason, they are chosen to be the founders and most active community members of Maker.

### Implementation steps

There are several phases after the Dai Alpha that will be implemented in discrete steps, in the following order.

#### The decentralized CDP engine

Once the CDP engine is deployed, users will be able to issue dai directly by interacting with a set of smart contracts on the Ethereum blockchain. At this point, Maker Insurance will not yet have been implemented, so the stability of the dai will not be as strong as in the full implementation. Furthermore, there will not yet be any MKR voting, so users and shareholders will still need to trust the Alpha Dynasty to be Maker's executive authority.

#### MKR voting

This feature will allow shareholders to fully control the Maker DAO by proposing actions and voting on their execution through a user interface. Once this is implemented, the Alpha Dynasty will no longer be necessary and from this point on Maker will have a decentralized governance structure.

#### Maker Insurance

This feature means that Maker will be able to automatically dilute MKR in order to bail out bad CDPs. Once this is implemented, the dai will have full stability and strong decentralization.

#### Authority lockdown

Once all the features of the Dai Credit System have been fully implemented, all that's left to do is to lock down the permissions of the Maker authority (now controlled by MKR shareholders). This will make it impossible for shareholders to do things like confiscate collateral from the CDPs of dai issuers. This will also limit how quickly the risk parameters and overall monetary policy of the credit system can be changed. The end result is maximized decentralization and resilience of the dai stablecoin.

## Long-term governance

Initially, the risk parameters and monetary policy of the credit system will be controlled by the Alpha Dynasty. In the long run, this responsibility will be handed over to a set of decentralized prediction markets according to the concept of *futarchy*. This way, Maker will ultimately be fully governed &mdash; even down to the level of day-to-day operations &mdash; by the free market.

<div class="pagination">
    <a class="pagination-item older" href="/docs/keepers-and-oracles/">Part 3</a>
    <a class="pagination-item newer" href="/docs/mkr-distribution-and-the-mkr-fund/">Part 5</a>
</div>
