# ZKM-Proof-Playground - SHA256 Hash Verification

## Introduction

This project demonstrates the lifecycle of a zero-knowledge proof generation process using ZKM (Zero-Knowledge Machine). It showcases a simple program that verifies a SHA256 hash without revealing the original input.

## Project Overview

The main components of this project are:

1. A Rust program that performs SHA256 hash verification
2. A proof generation process using ZKM
3. A verifier contract (to be generated)

## Proof Generation Process

The proof generation process consists of 6 main steps:

1. Writing the program (already provided in Rust)
2. Compiling the program using MIPS
3. Running the program through a prover with inputs
4. Receiving the proof as output
5. Generating a verifier contract from the ImageID of the program
6. Posting the proof to the verifier contract

## The Rust Program

The core of this project is a Rust program that:

1. Accepts two inputs: a public SHA256 hash and a private input value
2. Computes the SHA256 hash of the private input
3. Verifies that the computed hash matches the public input
4. Commits the result to the proof

```rust
// Rust code snippet (see full code in src/main.rs)
```

## How to Use This Project

1. Review the Rust code in `src/main.rs`
2. Use the provided interface to input values:
   - Public input: The known SHA256 hash
   - Private input: The value that, when hashed, should produce the public input
3. Click "Generate Proof" to run the proof generation process
   - Note: This process takes about a minute to complete
4. Examine the generated proof
5. (Optional) Generate a verifier contract using the program's ImageID
6. (Optional) Post the proof to the verifier contract for on-chain verification

## Pre-generated Proof

A pre-generated proof is included in this project, allowing you to explore the output without waiting for the proof generation process.

## Customization

Feel free to modify the input values to generate new proofs and experiment with the system.

## Technical Details

- The program runs as a "guest" program within the ZKM "host" environment
- The ZKM runtime provides functions for input/output and committing results to the proof

## Next Steps

- Experiment with different input values
- Try to generate your own proofs
- Explore the creation and use of a verifier contract

## Resources

- [ZKM Documentation](https://docs.zkm.io) (replace with actual documentation link)
- [Rust SHA256 crate](https://docs.rs/sha2/latest/sha2/)
