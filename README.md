# Prediction Market Protocol on Solana

This repository implements a decentralized prediction market protocol built entirely on the Solana blockchain. The system allows users to create markets tied to externally verifiable real-world events, trade outcome positions via an on-chain limit order book, and settle markets in a transparent and deterministic manner once outcomes are resolved.

All core functionality is executed on chain using Solana programs, with no reliance on off-chain matching engines or centralized operators. The project focuses on correctness, performance, and protocol-level clarity rather than consumer-facing UX abstractions.

---

## Overview

The protocol enables permissionless creation of outcome-based markets where participants express beliefs by trading positions associated with specific outcomes. Orders are placed as limit orders and matched directly on chain, allowing prices to emerge naturally from market demand.

Each market progresses through a defined lifecycle consisting of creation, active trading, resolution, and settlement. Once an outcome is finalized, settlement logic enforces payouts according to predefined rules, ensuring trustless execution without intermediaries.

This project demonstrates how complex market mechanics such as order matching, position accounting, and settlement can be implemented efficiently within Solana’s execution model.

---

## Why This Is Non-Trivial on Solana

Implementing an on-chain order book on Solana requires careful handling of account sizing, deterministic state transitions, and compute constraints.

Key challenges addressed in this design include:

* Representing order book state within Solana account size limits
* Ensuring deterministic order matching without off-chain coordination
* Safely handling concurrent order placement and cancellation
* Designing settlement logic that is atomic, replay-safe, and deterministic

This project explores these constraints directly rather than abstracting them away with off-chain components.

---

## Features

1. Permissionless market creation
2. On-chain limit order book for outcome trading
3. Position tracking and balance accounting handled by smart contracts
4. Deterministic settlement after outcome resolution
5. High-throughput, low-latency interactions enabled by Solana

---

## Technology Stack

* Solana Blockchain
* Anchor Framework
* Rust (on-chain programs)
* TypeScript (client integration and testing)

---

## Project Structure

```
app/
Frontend application

programs/
Solana programs implementing market logic

programs/polymarket-clone/src/
Core Rust source code

migrations/
Deployment scripts

tests/
Integration tests
```

---

## Prerequisites

* Node.js v14 or higher
* Rust toolchain with Cargo
* Solana CLI
* Anchor Framework

---

## Installation

Clone the repository:

```
git clone https://github.com/h-wal/pred_market
cd pred_market
```

Install dependencies:

```
npm install
```

Build the Solana program:

```
anchor build
```

---


## Design Philosophy

The protocol prioritizes explicit state transitions, deterministic execution, and transparent accounting. All logic is implemented on chain to minimize trust assumptions and maximize composability with other Solana programs.

The architecture is intentionally modular to support future extensions such as oracle integrations, alternative settlement mechanisms, or liquidity abstractions.

Inspired by existing prediction markets such as Polymarket and by broader research into decentralized financial market infrastructure on Solana.
