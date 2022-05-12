---
description: Trustless Permissionless Solana Optimized Storage
cover: ../../.gitbook/assets/server_background_only (1).png
coverY: 0
---

# Shadow Drive Overview

The Shadow Drive has been designed as the solution to Solana’s growing need for an on-chain ecosystem native storage solution. The following pages are intended to outline what Shadow Drive is, how it works, and why it works. These pages will do so by explaining things in practical terms as our goal is for a wide range of people to fully understand what is being built, rather than a select few. The hard-core academic types with a deep love for algorithms will likely find these pages to be largely disappointing.

Please note, this paper assumes some basic knowledge of GenesysGo, $SHDW, and the Solana architecture as a whole. This paper is, by design, not meant as an introductory resource to GenesysGo or Solana. Instead, this paper should be viewed as a resource for those considering GenesysGo’s Shadow Drive as a potential storage solution or for those attempting to vet the Shadow Drive’s long term viability.

If you aren’t familiar with Solana’s architecture, then it is highly recommended to spend some time learning about how Solana validators store “Account State”, what “AccountsDB” is, and what goes into the creation of “on-chain accounts.” Please see the Solana Discord (discord.gg/solana) and check out the dev-resources channel if none of these things are familiar to you.

## Contents <a href="#8ee5" id="8ee5"></a>

1. Summary
2. What is Shadow Drive?
3. Under the hood of Shadow Drive
4. Solana On-Chain Events and Proof of Storage
5. The Shadow Drive Smart Contract(s)
6. The Shadow Drive Enhanced GenesysGo Network Architecture
