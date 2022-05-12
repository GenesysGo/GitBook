---
description: >-
  Click a button and a Wormhole + Devnet appears with the state of all Solana
  Mainnet programs preloaded - Toly
cover: ../../.gitbook/assets/server_background_only (1).png
coverY: 0
---

# The Shadow Net

{% hint style="warning" %}
The Shadow Net section is under construction and will be updated with greater detail over the coming weeks.&#x20;

_Last Updated: May 9th, 2022_
{% endhint %}

The Shadow Net allows Solana builders the ability to create private instances of the Solana blockchain for as long or as short a period of time as they like. These private instances, or "Shadow Realms", are enhanced by their integration with the Solana Wormhole which enables full bridging of Mainnet tokens to and from the Shadow Realms.&#x20;

Once inside a Shadow Realm, transaction fees are no longer paid in $SOL and are instead paid using the Shadow Net's native token $SHDW. You can't hop between realities and not expect the laws of reality to change at least a little bit!

Read on to learn more about the Shadow Net, how it works at a high level, and the use cases.

## The World's Laziest Roadmap

...because roadmaps are stupid and always end up changing anyways...

**v.0 Proof of Concept -** An NFT mint held in the Shadow Realms

1. Create an NFT Program Account on Solana Mainnet.
2. Create a Shadow Realm connected to the Solana Mainnet via the Wormhole.
3. The NFT Auction is held in the Shadow Realm. Mint fees paid in $SOL, gas fees paid in $SHDW.
4. Results of the NFT mint are validated by Shadow Validators, forwarded to the Wormhole Guardians for validation, and then validated again by the Solana Mainnet validators for inclusion in the Solana Mainnet blockchain.
5. The Solana Validators update the state of the NFT program account to reflect the results of the sale resulting in users who minted in the Shadow Realm receiving their NFT in their Solana Mainnet Wallet.
6. The Shadow Realm is then shut down as it is no longer needed.

**v.1 Shadow Net** - Full Deployment

An open source network powered by $SHDW as the gas fee token. Dedicated validators running a lite version of the Solana validator configs allocated to processing transactions specifically for the creator of that Shadow Realm.

**v.2 Shadow Net** - Decentralized Deployment

1. Similar to the criteria for becoming a Wormhole Guardian Node operator, running a Shadow Validator will only be open to high quality validator operators with a proven track record.
2. The existing delegation model used for delegating $SOL to Solana validators will be implemented across the Shadow Validators. This creates another mechanism for $SHDW holders to stake $SHDW, earn rewards, and contribute to strengthening the network.
3. Implementation of stake-weighted voting in order to provide fully decentralized Shadow Realms for projects that desire it.

