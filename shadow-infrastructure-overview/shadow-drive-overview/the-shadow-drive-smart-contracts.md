# The Shadow Drive Smart Contracts

The Shadow Drive smart contracts are designed to fit multiple use cases. The beauty of smart contracts is the flexibility of design, which is one of the great things about building a storage layer as opposed to building a whole new blockchain (again, why build a whole new blockchain when we already have the world’s most performant state machine at our disposal).

**The Shadow Drive Smart Contract and Paxos**

The Paxos consensus mechanism is pretty amazing and is, arguably, the forerunner to the Proof of History consensus mechanism. As written in the Solana docs, Leslie Lamport (the creator of Paxos) is credited as the greatest technical influence to Solana. Another great resource explaining Paxos can be found here: [https://understandingpaxos.wordpress.com/](https://understandingpaxos.wordpress.com)

![Confirmed: Sneakers = Peak Performance](<../../.gitbook/assets/image (5).png>)

These pages are not meant to be a deep dive into Paxos. Instead, they will focus on how the Shadow Drive smart contract interacts with Paxos. Inside of Shadow Drive, a series of monitor daemons maintain the CRUSH map and ensure the integrity of the data stored within Shadow Drive. They also guard against unauthorized changes to the data and can restore all of the data stored within Shadow Drive. They are very similar to Solana validators in this way, and they should be considered the guardians of the state of all the data stored in Shadow Drive.

They are also what will allow for the decentralization of Shadow Drive, as monitor daemons can be housed on any host machine to participate in the quorum and all consensus voting can be recorded on-chain. More on this later, but Shadow Operators wishing to become Shadow Monitors would be held to a much higher standard of slashing and collateral requirements. This would be similar to the Serum/Mega-Serum node structure currently in place by Project Serum.

Circling back to the Shadow Drive smart contract... The smart contract has admin control over Shadow Drive and is the gatekeeper for uploading or editing anything held in the storage layer. Additionally, Shadow Monitors are configured to report their state and their votes to the Solana validator network for validation and inclusion on-chain. This provides an on-chain mechanism for the recording and slashing of Shadow Monitors either attempting malicious activity or not participating in maintaining the integrity of Shadow Drive’s data store. This is very similar to how the Solana validator network records and reports on the vote history of Solana validators and is a critical part of ensuring that Shadow Drive is a trustless permissionless network.

TL;DR: Shadow Monitors run a lightweight consensus mechanism and the Shadow Drive smart contract ensures that the activity of that consensus is trustless and fully visible to all on-chain.

Please note, uploads/edits of data are different than reading data. Projects using Shadow Drive to store their data will have the ability to control who can and cannot read what has been uploaded.

**Mutable vs. Immutable Storage**

We learned from watching existing storage providers and feel that it is important we ensure users have choice in how their data is stored. Some data should be stored perpetually, but not all data requires this. In fact, one could argue that very little data actually needs to be stored forever. This is likely one of the reasons why Arweave only stores \~60TB (as of the time of writing) of data in total. Which is very fascinating when you consider the fact that Arweave currently has a market cap of \~$1.5b (as of time of writing), yet stores a relatively small amount of data.

With all that said, users will select how they want their data stored, and that will impact the overall cost of storage and the way that cost is assessed.

The $SHDW token is broken up into fundamental units called “Shades”. Shadow Drive focuses on the fundamentals of storage and, at the most fundamental level, Shadow Drive stores bytes. Therefore, in the spirit of simplicity, the following conversions are applied:

1,000,000,000 Shades = 1 $SHDW

_This is in line with 1b lamports equaling 1 $SOL as a measure of the cost computational units_

1,000,000,000 bytes = 1 gigabyte

_Therefore…_

1 byte stored = 1 Shade or 1 gigabyte = 1 SHDW

**Immutable storage** is relatively simple… If you upload 1gb of data to Shadow Drive, then a cost of 1 $SHDW is applied and the smart contract sends that $SHDW to the Shadow Operator smart contract to be sent out to Shadow Operators as emissions for operating Shadow Nodes. The data is flagged as “immutable” by the Shadow Drive smart contract and is therefore unable to be edited or deleted.

**Mutable storage** is a little more complex (but not overly so) and relies on staking and rent mechanics very similar to the ones used by Solana in their on-chain accounts design. If you upload 1gb of data to Shadow Drive, then you are required to **stake** 1 $SHDW. On a per epoch basis, rent is assessed against mutable storage at the rate of 1 SHDW per GB per year. Therefore, uploading 1gb of data to Shadow Drive would look something like this…

1. A user uploads 1gb of data into Shadow Drive. In order to do so, the user is required to stake 1 $SHDW with the Shadow Drive smart contract.
2. On a per epoch basis, rent is assessed and removed from the staked $SHDW (unless the user has flagged the data as immutable) in the form of Shades. By the end of a 1 year period, the storage user would need to add additional $SHDW to their account or risk the data being deleted.
3. The rent assessed each epoch is sent to the Shadow Operator Smart Contract and adds to the pool the smart contract pays out to Shadow Operators as emissions.
4. If, after six months, the storage user unstakes their $SHDW (signaling that they no longer need this data to be stored), then they would have paid .5 $SHDW in rent and would receive .5 $SHDW back.
5. If, after six months, the storage user decided to flag their data as immutable, then they would need to add the difference between what is currently staked in the smart contract and what it would cost to immutably store their data. So, a user with 1gb of data stored and .5 $SHDW staked in the smart contract (after six months of staking) would need to add .5 $SHDW in order to make their data immutable.

This design was adopted in order to help the network benefit from reduced liquidity and ensure the longevity of the Shadow Operators. The benefit to users of mutable storage is that their short-term storage needs are met; and once those needs have been met, the mutable storage user can potentially unstake their $SHDW at a higher value than what they purchased it for. The benefit to those who use immutable storage is that they can rest assured that their account data will be retained for continual access/usage into perpetuity. This also means that as the price of $SHDW fluctuates, users of immutable storage will likely have paid a cheaper price for storage as years pass.

In the end, we believe immutable storage to be the best overall value, but we also recognize that short-term data storage needs should not be forced into a singular regime.

_Please note, the team reserves the right to change any and all aspects of storage design/costs in order to ensure the long term viability of Shadow Drive and Shadow Operators. We would rather make tweaks to one protocol along the way instead of building a new protocol each time to address any unforeseen issues._
