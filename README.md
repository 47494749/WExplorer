# WExplorer

**WExplorer (Wallet Explorer)** is a low-level Bitcoin Core wallet analysis tool written in C++.  
It scans and decodes wallet data, exploring transactions, addresses, and scripts in a human-readable form.

---

## Project Status

> **Under Development**
>
> This project is still experimental — no stable release or documentation yet.  
> Functions, structures, and output format may change frequently.

---

## Features (Current & Planned)

- Explore Bitcoin Core wallet contents  
- Decode and display Bitcoin scripts (`scriptSig`, `scriptPubKey`, etc.)  
- Identify standard script types (P2PKH, P2SH, SegWit, Taproot…)  
- Decode coinbase input scripts 
- Hex + ASCII visualization of raw wallet data  
- Analyze keys, addresses, and transactions  

---

## Requirements

- Bitcoin Core wallet files (`wallet.dat` or extracted dumps)

---

## Usage

```bash
./wexplorer -i [path_to_wallet]
./wexplorer -h
