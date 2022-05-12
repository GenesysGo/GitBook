# Solana Wormhole Integration

## More than just a token bridge...

The Solana Wormhole provides the Shadow Net with incredible functionality. While the Wormhole is most widely known as a token bridge, it is a much more versatile program than that. First of all, if you aren't familiar with the Solana Wormhole then I would highly suggest watching this video:

{% embed url="https://www.youtube.com/watch?t=1s&v=w2C8lrFTnrc" %}

Understanding the Wormhole is very important because this is how Shadow Net passes instructions from one Shadow Realm to the other and, most importantly, to the Solana Mainnet.&#x20;

## Cross Chain Messaging

Using the Wormhole, Shadow Net is able to receive instructions from the Solana Mainnet and these instructions dictate how the Shadow Realm is configured and the way in which it interacts with the Solana Mainnet.

As explained in the overview, these instructions tell the Shadow Net the current "state" of the project's program account and effectively seed a Shadow Realm with the needed data to re-create the state of the Solana Mainnet. From there, the Shadow Net would report updates to the Shadow Realm state as frequently or infrequently as the project desires. Those updates would update the "state" of the program account on Solana.

So, here's one kind of example (an NFT mint) to make this a little easier to understand:

1. Project BUIDL initializes their Candy Machine on Solana Mainnet and has a program address of: **GkYcyvjgjf2j3UVukUsjbc37i88FNyNrDqeyBXDDikr1**
   * _Note, this is the program account address. This address denotes how the Solana Mainnet validators identify a smart contract which lives on-chain._
   * Project BUIDL's NFT drop will be generating 10,000 unique and randomly generated SOLPaperhand NFTs.
2. Project BUIDL also initializes the creation of a Shadow Realm on Shadow Net. Instructions are passed to the Wormhole Guardians. Wormhole Guardians are designed to protect the integrity of a message as it goes from one chain to another.
   * For more information on who the Wormhole Guardians are please go here: [https://wormholenetwork.com/network/](https://wormholenetwork.com/network/)
3. Because a Shadow Realm is a re-creation of the Solana Mainnet at that moment in time, the BUIDL NFT contract's state is re-created identically. We know that this is a valid request with a valid signature because the Shadow Validators and the Wormhole Guardian's consensus mechanism agreed on the validity.&#x20;
   * _Please refer back to the Overview for info on how Shadow Validators achieve the re-creation of the Solana Mainnet state._
4. Project BUIDL is incredibly hyped and so hundreds of thousands of potential minters are racing to click and mint their SOLPaperhand NFT. The Project BUIDL front-end UI and back-end smart contract are pointing at the Shadow Realm.
5. The mint goes off successfully! The BUIDL NFT smart contract inside of the Shadow Realm has generated 10,000 unique SOLPaperhand NFTs with different characteristics and which wallet addresses generated them. Now... to get those NFTs into the hands of the minters on the Solana Mainnet!
6. The Shadow Net smart contract sends the new updated state of **GkYcyvjgjf2j3UVukUsjbc37i88FNyNrDqeyBXDDikr1** to the Wormhole Guardians.&#x20;
   * This is an example of cross chain messaging, we're not bridging any tokens (yet...).&#x20;
   * The Shadow Validators are instead passing a message to the Wormhole Guardians saying, "The state of **GkYcyvjgjf2j3UVukUsjbc37i88FNyNrDqeyBXDDikr1** has changed and here is what it looks like now."
7. The Wormhole Guardians all look at this message from the Shadow Validators and agree on its contents and its validity. The Guardians then sign off on the message and pass it to the Solana Mainnet.
   * This is a huge oversimplification but one can think of the Wormhole Guardians as couriers almost.
8. The Solana Mainnet validators receive the message that was passed to them by the Wormhole Guardians from the Shadow Validators. The Solana Mainnet validators receive the message and update the state of **GkYcyvjgjf2j3UVukUsjbc37i88FNyNrDqeyBXDDikr1** to reflect which wallets minted the NFTs and what was minted.
9. These changes are then built into the Solana Mainnet blocks. The difference though is all of the minting spam and minting transactions took place in the Shadow Realm. The compute from the Solana Mainnet validators is only used once the final state of the SOLPaperhand NFT generation and sale has been finalized and the program account's state needs to be updated.

{% hint style="warning" %}
Additional examples will be added over time. We understand that there are many moving parts and want to make sure there are several different kinds of examples to help people wrap their heads around the actual flow.
{% endhint %}

