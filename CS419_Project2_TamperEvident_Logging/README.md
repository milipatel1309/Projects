# ⛓️ Tamper-Evident Logging with Proof-of-Work (CS 419)

Blockchain-based network logging service that uses proof-of-work to rate-limit clients and provides a validation tool to detect tampering.

## Components

- **logserver**: accepts log messages from clients, appends entries to a hash-chained log (blockchain-style), and enforces proof-of-work before accepting messages.
- **log**: client utility to submit messages to the server with required proof-of-work.
- **checklog**: validates the integrity of the log by verifying the hash chain and detecting modifications.

## Key Ideas Implemented

- Hash-chained (tamper-evident) log entries
- Proof-of-work to prevent message flooding / abuse
- Validation utility to confirm log integrity end-to-end

## Build

```bash
make


Usage (example)
./logserver
./log "example message"
./checklog

