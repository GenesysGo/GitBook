# Slashing

Slashing is a mechanism by which a network punishes bad actors or negligent operators. The Shadow Operator smart contract has a slashing mechanism in place as well.

Health checks are sent to Shadow Operators in the form of RPC pings. Shadow Operators whose machines fail to respond to the health check pings or are behind by higher than a certain amount of slots are considered "down" and are potentially subject to slashing if they persist in that state for too long.

{% hint style="danger" %}
All instances of slashing and failed health checks are handled on-chain and have been validated for consensus by the Solana Mainnet validators. Slashing is recorded on-chain and callable for review to ensure the integrity of the mechanic.
{% endhint %}

The slashing order flow looks something like this:

1. A health check is sent to the Shadow Operator's machine.
2. The Shadow Operator's machine responds back showing that it is 1550 slots behind. This Shadow Node is considered to be in a "down" state because it is not capable of properly serving network requests.
3. The Shadow Operator's machine persists in this state for several minutes.
4. The results of this health check are recorded on-chain in the Shadow Operator Staking smart contract's program account and that Shadow Node is slashed.
5. The smart contract references the current epoch on-chain and how many times that Shadow Node has been slashed during that epoch.
6. $SHDW emissions are slashed first. If a Shadow Node continually shows as being in a "down" state then it is possible for the Shadow Operator's emissions to be slashed to zero and they will earn no rewards for that epoch.
7. If no emissions are available for that epoch because the Shadow Node has consistently been responding poorly to the health check then the staking smart contract will slash the Shadow Operator's collateral.
8. If a Shadow Operator's collateral has been slashed and they fall below a minimum threshold then they are considered "underwater" on their collateral and must replenish it in order to begin earning rewards again.
9. All $SHDW tokens removed as a result of slashing are deposited into the Shadow Operator Emissions smart contract to contribute to future emissions for the Shadow Operators.
