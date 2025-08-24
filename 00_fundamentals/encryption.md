# Encryption Fundamentals

## Digital Signatures

Digital signatures are electronic signatures that uses cryptography techniques to verify the authenticity and integrity of a message or file : 
- **Authentication**: The identity of the signer is verified
- **Non-repudiation**: The signer cannot deny having signed
- **Integrity**: Ensures the content hasn't been modified since signing

### How Digital Signatures Work

1. **Key Generation**: Create a public/private key pair
2. **Signing**: Use the private key to create a signature of the message hash with a signing algorithm because it is simpler to sign a 256 bits hash than the whole message
3. **Verification**: Use the public key to verify the signature matches the message, we will see this part further in the ECDSA section

### Digital Signature Process

```
Message → Hash Function (Sha256 for example) → Message Digest 
Message Digest → encryption with Private Key → Digital Signature
Message + Digital Signature + Public Key → Verification (Valid/Invalid)
```

## Encryption Types

### Symmetric Encryption
- Uses the same key for encryption and decryption
- Fast and efficient for large amounts of data
- Short keys (128 or 256 bits are the most common)
- Key distribution challenge: how to securely share the key
- Examples: AES, DES, 3DES

### Asymmetric Encryption (Public Key Cryptography)
- Uses a pair of keys: public key and private key
- Slower than symmetric encryption but solves key distribution
- Longer keys
- Can be used for signing and authentication
- Examples: RSA, ECDSA

