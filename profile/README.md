<div align="left">

# Traiecta Labs

**A router between Stellar and the EVM chains, over rails that already earned their trust.**

![Route](https://img.shields.io/badge/route-Stellar%20%3A%3A%20EVM-C2703D?style=flat-square&logo=stellar&logoColor=white)
![Rails](https://img.shields.io/badge/rails-CCTP%20%2F%20Axelar%20%2F%20Allbridge-2F6FED?style=flat&labelColor=111827)
![License](https://img.shields.io/badge/license-MIT%20%2F%20Apache--2.0-2F6FED?style=flat)

</div>

## The claim

Traiecta is not a bridge and does not pretend to be one. It never decides on its own that a cross-chain message is real. It hands a transfer to a rail that already made that decision and was audited for it, then keeps the fee, the limits, and the claims.

## How a transfer moves

A Stellar leg and an EVM leg meet at a router that prices every available rail and takes the one that lands the most money. On Stellar the router is a Soroban contract with one adapter per rail. On the EVM side it is the same router written in Solidity. A tracker follows the middle of the journey, where a transfer exists only as an attestation inside somebody else's API.

## Stellar and EVM, treated differently

Stellar ledgers close in roughly five seconds with deterministic finality, so a closed ledger is final and the Stellar watcher never rewinds. EVM chains finalize probabilistically, so the EVM watcher tracks confirmations and reorgs. The two watchers are separate for that reason, not for symmetry.

## Repositories

| Repository | Role | Stack |
| --- | --- | --- |
| [traiecta-contracts](https://github.com/Traiecta-Labs/traiecta-contracts) | routers and rail adapters for Stellar and EVM | Rust, Solidity, TypeScript |
| [traiecta-api](https://github.com/Traiecta-Labs/traiecta-api) | transfer tracking, rail pollers, and a REST API | TypeScript, Postgres |
| [traiecta-app](https://github.com/Traiecta-Labs/traiecta-app) | routing UI, live quotes, and the transfer tracker | Next.js, wagmi |

`Stellar` · `Soroban` · `EVM` · `CCTP` · `Axelar` · `Allbridge`
