# The GenesysGo RPC Network

{% hint style="warning" %}
YES! The GenesysGo RPC Network is free. Yes, we can offer free infrastructure despite what the uninformed might otherwise think.

The GenesysGo RPC Network is paid for using the royalties from the Shadowy Super Coder NFT and the APR generated from the Shadowy Super Coder DAO Validator.

If you want to support our RPC network and earn APR while you're at it, consider staking your SOL with us:

[https://solanabeach.io/validator/AKoVXpZmi8wSz3sGvCYEygbpdHvSRysWsh36b97iPvKh](https://solanabeach.io/validator/AKoVXpZmi8wSz3sGvCYEygbpdHvSRysWsh36b97iPvKh)
{% endhint %}



## If you are a Solana builder wanting RPC network access...

### **`Mainnet Endpoint:`** [**`https://ssc-dao.genesysgo.net/`**](https://ssc-dao.genesysgo.net/) **``**&#x20;

The SSC DAO network handles both https and wss connections. It provides unlimited data, global DNS load balancing for the lowest latency possible, backed by 300+ bare metal servers in 9 countries across 3 different continents. Additionally, the SSC DAO network has the full ledger history back to the genesis block.&#x20;

A Devnet endpoint is available as well! Note, Devnet does not support the full ledger history all the way back to the genesis block. \
\
Devnet Endpoint: [`https://devnet.genesysgo.net/`](https://devnet.genesysgo.net/)``



## How does the SSC DAO RPC Network function?

The SSC DAO RPC network provides the following:

* A global cluster of servers that has no singular point of failure.
* No data caps&#x20;
* All Solana historical ledger data back to the genesis block&#x20;
* GeoDNS load balancing&#x20;
* 10+ Gigabit speeds
* Provides incredibly high rate limits that would cost $1,000/month or more with other providers
  * Rate limits are handled on a per IP basis, each unique IP has its own bandwidth.
    * `SendTransaction` Limit: 10 RPS + 200 Burst
    * `getProgramAccounts` Limit: 15 RPS + 5 burst
    * Global Limit on the rest of the calls: 200 RPS
      * Please see Solana API documentation if you are unsure what this means: [https://docs.solana.com/developing/clients/jsonrpc-api](https://docs.solana.com/developing/clients/jsonrpc-api)
    * `Burst` allows for batching transactions and requests to be queued for processing instead of receiving a rate limit error (error code 429).
    * Custom endpoints no longer necessary for increased performance.
    * Devnet endpoints are unlimited RPS with no caps.
