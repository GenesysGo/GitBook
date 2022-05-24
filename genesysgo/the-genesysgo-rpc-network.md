# The GenesysGo RPC Network

## If you are a Solana builder wanting RPC network access...

### **`Mainnet Endpoint:`** [**`https://ssc-dao.genesysgo.net/`**](https://ssc-dao.genesysgo.net/) **``**&#x20;

The SSC DAO network handles both https and wss connections. It provides unlimited data, global DNS load balancing for the lowest latency possible, backed by 300+ bare metal servers in 9 countries across 3 different continents. Additionally, the SSC DAO network has the full ledger history back to the genesis block.&#x20;

Devnet endpoints are available as well! They're uglier bc it's just devnet but they work just fine! Note, Devnet does not support the full ledger history all the way back to the genesis block. Private Cluster Devnet:

[`https://psytrbhymqlkfrhudd.dev.genesysgo.net:8899/`](https://psytrbhymqlkfrhudd.dev.genesysgo.net:8899/) `wss://psytrbhymqlkfrhudd.dev.genesysgo.net:8900/`



## How does the SSC DAO RPC Network function?

The SSC DAO network provides the following:

* A global cluster of servers that has no singular point of failure.
* No data caps&#x20;
* Archive nodes with data back to genesis&#x20;
* GeoDNS load balancing&#x20;
* Gigabit speeds
* Provides incredibly high rate limits that would cost $1,000/month or more with other providers
  * Rate limits are handled on a per IP basis, each unique IP has its own bandwidth.
    * `SendTransaction` Limit: 10 RPS + 200 Burst
    * `getProgramAccounts` Limit: 15 RPS + 5 burst
    * Global Limit on the rest of the calls: 200 RPS
      * Please see Solana API documentation if you are unsure what this means: [https://docs.solana.com/developing/clients/jsonrpc-api](https://docs.solana.com/developing/clients/jsonrpc-api)
    * `Burst` allows for batching transactions and requests to be queued for processing instead of receiving a rate limit error (error code 429).
