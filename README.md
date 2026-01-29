# WExplorer

**WExplorer (Wallet Explorer)** is a low-level wallet analysis tool written entirely in **C++**, designed to inspect and decode Bitcoin Core wallet files at a binary level.

It is conceptually similar to tools like **pywallet**, but implemented natively in C++ and intended to run on **Windows**.  
The focus of WExplorer is **forensic-style analysis**, data inspection, and structural validation of wallet files.

---

## Project Status

> **Under Development**
>
> This project is still experimental — no stable release or complete documentation yet.  
> Functions, internal structures, and output format may change frequently.
>
> Run `wexplorer -h` to check available options and newly added features.

---

## Overview

WExplorer scans and decodes wallet data, exploring transactions, addresses, scripts, and keys in a **human-readable form**, while preserving access to the underlying raw binary data.

At the moment, **only Bitcoin wallets are fully decoded**, but the tool already includes mechanisms to **identify wallets belonging to other coins**.

---

## Features

### Wallet Analysis
- Decode **Bitcoin Core wallet files** (`wallet.dat` or extracted dumps)
- Automatically **detect which coin a wallet belongs to**
- Automatically **rename wallet files** if they are not Bitcoin wallets
- Detect **fake wallets** (artificially created wallets using fake keys)
- Analyze **wallet data distribution** to determine whether it is consistent with real Bitcoin Core wallets

### Key & Data Inspection
- Perform **low-level scanning** to locate all private keys inside the wallet file  
  - Encrypted keys are detected and shown in encrypted form
- Analyze raw wallet data using **hex + ASCII visualization**

### Script & Transaction Decoding
- Decode and display Bitcoin scripts:
  - `scriptSig`
  - `scriptPubKey`
  - coinbase input scripts
- Identify standard script types:
  - P2PKH
  - P2SH
  - SegWit
  - Taproot
- Decode **ASN.1 values** used in signatures
- Decode and inspect transaction-related data structures

---

## Supported Coins

- **Bitcoin** — fully supported and decoded
- Other coins — detection only (no full decoding yet)

---

## Requirements

- Bitcoin Core wallet files:
  - `wallet.dat`
  - or extracted wallet dumps

## Online functionality (available from 0.16)

To use the online features of this tool, **OpenSSL libraries must be available at runtime**. The required OpenSSL DLLs must be present either in the **system PATH** or in the **current application directory**.
If OpenSSL is not available, online functionality will be disabled.

OpenSSL for Windows can be downloaded from: https://slproweb.com/products/Win32OpenSSL.html

---

## Usage

```bash
./wexplorer -i [path_to_wallet]
./wexplorer -h
