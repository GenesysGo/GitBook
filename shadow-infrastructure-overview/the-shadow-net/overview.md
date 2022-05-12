# Overview

## **Summary**

The Shadow Net is a collection of dedicated on-demand Solana instances, or Shadow Realms. It is powered by a network of Shadow Validators whose configurations have been tweaked to focus on maintaining consensus on smaller scales than the full Solana Mainnet. Each Shadow Realm provides an on-demand Solana blockchain environment identical to the state of the Solana chain at the time of its creation.

Upon the creation of a Shadow Realm, Shadow Validators create a fork of the Solana Mainnet and preload all of its program accounts. In doing so, builders are provided an environment that looks, feels, and acts exactly like the Solana Mainnet. The key difference being that the blockchain ledger stored by Shadow Validators from the moment of creation onward is specific solely to that Shadow Realm. Essentially, blocks built inside of a Shadow Realm are filled only with the transactions from that project's smart contracts.&#x20;

From there, a project's builders can decide which transactions are sent through the Solana Wormhole back to the Solana Mainnet validators for inclusion in the Solana Mainnet chain.

## Why are we building Shadow Net?

The Shadow Net addresses critical needs of the Solana ecosystem:

1. It makes Solana horizontally scalable by sending the most compute heavy processes to the L2.
2. Builders are provided with a devnet environment that is identical to the Solana Mainnet. Currently, the Solana Devnet does not completely mimic Mainnet.
3. Shadow Realms add additional layers of stability to the Solana blockchain as a whole.
4. The Shadow Net creates another utility use case for the $SHDW token, thus providing $SHDW holders with additional value.
5. Smart contract interoperability between blockchains, facilitated via Wormhole integration, helps to make onboarding to Solana easier than ever for the largest projects from other blockchains and for legacy non-blockchain businesses beginning their blockchain journey.

## What are Shadow Validators?

The Shadow Net is made up of a network of Shadow Validators which communicate using their own gossip network, not integrated with the main chain.&#x20;

Shadow Validators run a lite version of the Solana validator code which gives them the same functionality as the Solana Mainnet validator network but with a focus on horizontal scaling. When a Shadow Realm is created Shadow Validator resources are allocated to that realm and the Shadow Validators begin building blocks and writing those blocks to a Shadow Ledger stored locally on the machines and backed up by the Shadow Drive, should the builders desire it.

Builders interact with Shadow Validators in exactly the same way as they do with the Solana Mainnet validators. The Solana RPC API calls all function exactly the same and the way that Shadow Validators reach consensus, build blocks, and accept transactions is all identical to the Solana Mainnet validators.

After discussions with the Solana Labs team, it was decided to allow for as much customizability in Shadow Realms as possible. This includes whether you want your Shadow Realm powered by a decentralized Shadow Validator network or a centralized one. This design is intended to help ease the transition for non-blockchain based projects and companies into blockchain (specifically Solana) and will allow Shadow Net to serve as an onboarding mechanism to increase overall user count for Solana.

