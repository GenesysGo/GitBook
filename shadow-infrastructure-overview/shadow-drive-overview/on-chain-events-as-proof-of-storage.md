# On-chain events as Proof of Storage

First, please allow me to set some context about Solana itself… At the most basic fundamental level, blockchains are nothing more than ledgers. Ledgers record the history of how things have changed over time and all of those changes combined give you the current “state”. Solana is all about its “accounts” and the “state” of those accounts.

What do I mean by “state”? Let’s use computers as an example… Everything in a computer is 0’s and 1’s. The bit stores just a 0 or 1: it’s the smallest building block of storage. **If a bit is a 1 then its current state is 1. If a bit is 0 then its current state is 0.** That bit is either a 0 or a 1, the history of that bit is not relevant to whether that bit’s state is currently a 0 or a 1.

The next thing we need to know is that Solana is unique in the way it structures everything as an “account.” This is important terminology, so here’s the definition:

![https://docs.solana.com/terminology](<../../.gitbook/assets/image (7).png>)

Thinking back to state, the history of the accounts on Solana is completely irrelevant to their current state. Why? Because all the events that took place in order to arrive at the current state were reviewed by the Proof of History consensus mechanism (i.e. the Solana Validator network) and deemed to be valid.

Tying everything together, what Solana is really built to achieve and maintain consensus on is the state of all accounts on the network. **It is a state machine.** In fact, **“the world’s most performant global state machine”** is exactly how Solana is described in its Twitter bio.

![https://twitter.com/solana](<../../.gitbook/assets/image (4).png>)

The current state of Solana is already hashed, but then it is shredded and decentralized across all the validators of the network. Effectively what this means is that Solana can recreate the current state of every piece of data on the blockchain… every wallet address, every program that’s been deployed, the location of every single token… at a moment’s notice… **without** needing to know anything about the historical transactions that led up to the current state.

Now, just because historical transactions are irrelevant to the current “in the moment” state of all accounts on Solana (because every event leading up to the present had to be passed through the Solana validator network and therefore was part of the consensus that led to the current state) doesn’t mean that historical transactions aren’t important to the **developers and users** performing actions on Solana.

This is where we circle back to Shadow Drive. The Shadow Drive utilizes the world’s most performant state machine to ensure the validity and integrity of the state of its storage network via on-chain change events.

It’s easiest to explain in real terms, so here’s an example… Let’s say you upload NFT metadata to Shadow Drive and want that data to be stored permanently and want it to be immutable.

1. An NFT project uploads their NFT metadata to Shadow Drive. The NFT project wishes for this metadata to be stored forever and wants it to be immutable.
2. These instructions from the NFT project creators are passed to the Shadow Drive smart contract and the smart contract sends a transaction request to the Solana validators which has been signed by the NFT project’s wallet.
3. An account hash is created on-chain that indicates which NFT project the metadata is associated with, that this metadata is immutable, and to be stored permanently.
4. Then the hash plus the actual NFT metadata itself are hashed again, sharded, and uploaded to Shadow Drive by the smart contract in the appropriate storage format and location to ensure that the data can never be edited (not even by the NFT founders who uploaded it) and never deleted.

Under this design, the Shadow Drive smart contract only recognizes signatures from the wallet associated with the stored data. In this example, any transaction requests to change the data listed as immutable in Shadow Drive would fail to be validated by the Solana validators. This is because the smart contract would not pass through any instructions to edit or delete this data, due to the fact that the data is immutable and therefore cannot be edited or deleted.

In the **“Shadow Drive Smart Contract”** section, we will go deeper into how the Shadow Drive smart contract interacts with the Solana validator network to ensure that the data stored in Shadow Drive and the Paxos consensus mechanism inside are also being validated to ensure their current state (and thus the integrity of the data) remains intact.
