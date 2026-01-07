# Stream and Feistel Ciphers (CS 419)

This project implements three encryption utilities as part of a computer security assignment:

- **scrypt**: stream cipher using a password-derived seed and linear congruential keystream
- **vcrypt**: stream cipher with an initialization vector (IV)
- **feistel**: 10-round Feistel block cipher with PKCS#7 padding

## Build
```bash
make

## Testing
Correctness is verified by encrypting and decrypting files and comparing results using `cmp` to ensure byte-for-byte equality.
