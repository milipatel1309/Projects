# 🔒 Stream & Feistel Ciphers (CS 419)

This project implements three encryption utilities as part of a Computer Security assignment, focusing on stream ciphers, initialization vectors, and block cipher design.

## Overview

The project includes the following programs:

- **scrypt**: Stream cipher using a password-derived seed and a linear congruential keystream generator  
- **vcrypt**: Stream cipher with an initialization vector (IV) to prevent keystream reuse  
- **feistel**: 10-round Feistel block cipher operating on 128-bit blocks with PKCS#7 padding  

Each program supports file-based encryption and decryption and is designed to behave consistently across platforms.

## Implementation Details

- Passwords are converted to numeric seeds using the **sdbm hash function**
- Keystream generation uses a **linear congruential generator (LCG)**
- Initialization vectors are written in **little-endian format**
- The Feistel cipher derives round keys using an LCG-based key schedule
- Padding follows the **PKCS#7** specification
- Correctness is validated using byte-for-byte comparison via `cmp`

## Language & Environment

- **Language**: C  
- **Build System**: Makefile  
- **Platform**: POSIX-compatible (tested on Linux/macOS)

