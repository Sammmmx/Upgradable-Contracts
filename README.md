Upgradeable Smart Contracts (Proxy Pattern)

This repository demonstrates a basic upgradeable smart contract architecture using the Proxy Pattern in Solidity.

The project includes:

Logic.sol — Initial implementation contract
Logic2.sol — Upgraded implementation contract
Proxy.sol — Upgradeable proxy contract

This setup allows upgrading smart contract logic without changing the proxy address or losing state.

Contracts Overview
1. Logic.sol (Implementation V1)

The initial logic contract contains:

Functions
increment() — Increases stored value
getValue() — Returns stored value

This contract represents Version 1 of the logic.

2. Logic2.sol (Implementation V2)

This contract extends Logic.sol functionality.

Functions
increment() — Increases stored value
decrement() — Decreases stored value (New Feature)
getValue() — Returns stored value

This contract demonstrates upgrading logic while keeping storage intact.

3. Proxy.sol

The proxy contract:

Features
Stores implementation address
Delegates calls using delegatecall
Owner can upgrade implementation
Preserves contract storage across upgrades

Functions
upgrade(address newImplementation)
Only owner can call
Updates implementation contract

How It Works
Logic.sol (V1)
     ↓
Deploy Proxy
     ↓
Interact via Proxy
     ↓
Deploy Logic2.sol (V2)
     ↓
Upgrade Proxy
     ↓
Use New Features

Tech Stack
Solidity
Hardhat
Proxy Pattern
Delegatecall

Purpose

This project demonstrates:

Upgradeable smart contracts
Proxy pattern implementation
Contract upgrade mechanism
Storage persistence across upgrades
