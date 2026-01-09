# Prediction Market Protocol on Solana

This repository implements a decentralized prediction market protocol built entirely on the Solana blockchain. The system allows users to create markets tied to real world events, trade outcome positions through an on chain order book, and settle markets in a transparent and deterministic manner once outcomes are resolved.

All core functionality is executed on chain using Solana programs, with no reliance on off chain matching engines or centralized operators. The project focuses on correctness, performance, and protocol level clarity rather than consumer facing abstractions.

## Overview

The protocol enables permissionless creation of outcome based markets where participants can express beliefs by trading positions associated with specific outcomes. Orders are placed as limit orders and matched directly on chain, allowing prices to emerge naturally from market demand.

Each market progresses through a defined lifecycle consisting of creation, active trading, resolution, and settlement. Once an outcome is finalized, settlement logic enforces payouts according to predefined rules, ensuring trustless execution without intermediaries.

This project demonstrates how complex market mechanics such as order matching, position accounting, and settlement can be implemented efficiently within Solana’s execution model.

## Features

1. Permissionless market creation
2. On chain limit order book for outcome trading
3. Position tracking and balance accounting handled by smart contracts
4. Deterministic settlement after outcome resolution
5. High throughput and low latency interactions enabled by Solana

## Technology Stack

Solana Blockchain
Anchor Framework
Rust for on chain programs
TypeScript for client integration and testing

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

## Prerequisites

Node.js version 14 or higher
Rust toolchain with Cargo
Solana CLI tools
Anchor Framework

## Installation

Clone the repository.

```
git clone https://github.com/shri-prakhar/Prediction_market_on_solana.git
cd Prediction_market_on_solana
```

Install dependencies.

```
npm install
```

Build the Solana program.

```
anchor build
```

## Testing

Run the test suite using Anchor.

```
anchor test
```

Tests validate market creation, order placement, matching behavior, and settlement logic.

## Deployment

Update the target Solana cluster in the Anchor configuration file.

Deploy the program.

```
anchor deploy
```

## Design Philosophy

The protocol prioritizes explicit state transitions, deterministic execution, and transparent accounting. All logic is implemented on chain to minimize trust assumptions and maximize composability with other Solana programs.

The architecture is intentionally modular to support future extensions such as oracle integrations, alternative settlement mechanisms, or liquidity abstractions.

Inspired by existing prediction markets such as Polymarket and by broader research into decentralized financial market infrastructure on Solana.

---

