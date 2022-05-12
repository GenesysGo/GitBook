---
description: In an infinite multiverse, there is no such thing as fiction. - Scott Adsit
---

# Shadow Realms

Shadow Realms are the pocket realities that make up the Shadow Net. Each Shadow Realm preloads all Solana Mainnet programs, effectively creating a self contained shard of Solana Mainnet. Both the builder experience and the user experience inside of a Shadow Realm is identical to the experience using the Solana Mainnet.

Shadow Realm blocks are built by Shadow Validators whose compute has been allocated to that specific Shadow Net. Transactions processed inside of a Shadow Realm are paid using the $SHDW token (in lieu of $SOL) and transaction fees inside of a Shadow Realm are identical to Solana Mainnet.&#x20;

## **What are the benefits of using a Shadow Realm?**

* Builders are provided with a self contained dev environment that exactly mimics the Solana Mainnet. This will improve on development times significantly as compared to the current model where dapp builders deploy on local machines first, then rebuild/redeploy on Devnet, and then finally deploy again to Mainnet.
* Shadow Realms exist for as long as needed, potentially existing forever. They can be created instantly and wiped out just as quickly.&#x20;
* Because each Shadow Realm is a self contained environment, they potentially offer a much greater degree of stability than the Solana Mainnet especially during times of network congestion or software rollups.
* One project can potentially utilize many different Shadow Realms, each tailored to a specific use case or aspect of the project.

## How does a Shadow Realm work?

{% hint style="warning" %}
Please note, this is meant to communicate the general feel and flow. The specifics are always subject to change if we come up with a better implementation.
{% endhint %}

1. Shadow Realm creation begins on the Solana Mainnet. To create a Shadow Realm a transaction is signed on Solana Mainnet via the Shadow Net smart contract and that transaction signature is validated and stored on chain.
2. A Solana Mainnet Program Account is created and associated with that Shadow Realm's creation.
3. The Shadow Net Smart Contract then passes the signature to the Shadow Validators who use those instructions to create a Shadow Realm.
4. Shadow Net Validators receive a snapshot of the most recent state of all Solana Mainnet Program accounts from the Shadow Drive and the snapshot is unpacked to bring the Shadow Validators online.
   * This process is nearly identical to the process used by Solana Validators during the most recent chain halt. The most recent valid block was agreed upon by the majority of Solana Mainnet validators and then each validator downloaded and unpacked the snapshot containing that block and all relevant state.
5. At the same time, if the creator of a Shadow Realm chooses, they can also include instructions sent to the Solana Wormhole Token Bridge. These instructions could direct the Wormhole to bridge over existing Mainnet token assets so they are immediately available in the new Shadow Realm.
   * This is very similar to how the Wormhole Token Bridge can port token assets across different blockchains.
6. From here, a Shadow Realm operates exactly as it would if a builder deployed a Testnet validator on their local machine. Except the Shadow Net handles all the heavy lifting!
7. When the instructions are given, messages are sent through the Wormhole which updates the other program's state on the Solana Mainnet entirely. Any tokens that were produced or traded in a Shadow Realm as a result of the program just use a token bridge.
