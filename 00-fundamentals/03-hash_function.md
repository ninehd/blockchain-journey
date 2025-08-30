# SHA-256 and hash functions

The blockchain is a technology that allows information to be stored in a secure, tamper-proof, and distributed way
We are going to talk about one of the key elements that makes it work: hash functions

## What is a hash function?

A hash function is a mathematical function that takes an input (text, file, image, etc.) and produces an output called a hash.
The standard length of a hash is 256 bits but it can be shorter or longer.
Usually, the hash is displayed in hexadecimal format so it can be easily read by humans.

| Hex | Bin  | Hex | Bin  |
|-----|------|-----|------|
| 0   | 0000 | 8   | 1000 |
| 1   | 0001 | 9   | 1001 |
| 2   | 0010 | A   | 1010 |
| 3   | 0011 | B   | 1011 |
| 4   | 0100 | C   | 1100 |
| 5   | 0101 | D   | 1101 |
| 6   | 0110 | E   | 1110 |
| 7   | 0111 | F   | 1111 |

A SHA-256 hash is 64 hexadecimal characters long.

It exists a lot of hash functions (MD5, SHA-1, SHA-256, SHA-512), but the most popular one is SHA-256.

### Main properties

- It is deterministic: given the same input, it always produces the same output
- It is collision-resistant: given two different inputs, it is very unlikely that they produce the same output (However, MD5 and SHA-1 are considered now obsolete because they are not collision-resistant)
- It is fast: it takes a very short time to compute the hash
- It is irreversible: it is not possible to reverse the hash to get the original input


### Usage

- As a digital signature
- As a password, we don't store the password in plain text, only their hash. we store their hashes. Additionally, we use a salt (a random character chain that is appended to the original password before hashing it) to make brute-force attacks more difficult.
- As a unique identifier for a file so we can verify the integrity of the file
- As a secure way to ensure immutability of data for blockchain

### How it works
It is an algorithm that pads the message, splits it into blocks of fixed size of 512 bits, and then uses a combination of logical operations and mathematical functions to produce a hash of 256 bits.
You can read more about it [here](https://en.wikipedia.org/wiki/SHA-2)

### Example

SHA-256("Hello world") = 64ec88ca00b268e5ba1a35678a1b5316d212f4f366b2477232534a8aeca37f3c

SHA-256("Hello world!") = c0535e4be2b79ffd93291305436bf889314e4a3faec05ecffcbb7df31ad9e51a

You can see that a little change in the message produces a completely different hash.

### Limitations
In the future quantum computers will be able to break SHA-256.