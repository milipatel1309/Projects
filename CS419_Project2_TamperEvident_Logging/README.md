# Tamper-Evident Logging with Proof-of-Work (CS 419)

This project implements a blockchain-based network logging system designed to detect log tampering and prevent message flooding using proof-of-work. The system consists of a logging client, a logging server, and a verification utility.

## Components

- **log**  
  Client utility that submits log messages to the server. Each message includes a proof-of-work value to rate-limit submissions and deter spam.

- **logserver**  
  Server that accepts client messages and stores them in an append-only log structured as a blockchain. Each entry includes a hash of the previous entry to ensure tamper evidence.

- **checklog**  
  Verification tool that scans a log file and validates hash chaining and proof-of-work to detect modification or corruption.

## Implementation Details

- Each log entry contains:
  - Timestamp
  - Message data
  - Previous block hash
  - Proof-of-work nonce
- Cryptographic hashing is used to link log entries.
- Proof-of-work enforces computational cost per log entry.
- Any alteration to the log invalidates subsequent hashes.

## Build

```bash
make
