# ZKM-Proof-Playground - SHA256 Hash Verification

## Introduction

This project demonstrates the lifecycle of a zero-knowledge proof generation process using ZKM (Zero-Knowledge Machine). It showcases a simple program that verifies a SHA256 hash without revealing the original input.

## Requirements
Go needs to 1.22.5
Rust
   rustup install nightly
   rustup default nightly
build-essential
pkg-config
libssl-dev

## Project Overview

The main components of this project are:

1. A Rust program that performs SHA256 hash verification
2. A proof generation process using ZKM
3. A verifier contract (to be generated)

## Proof Generation Process

The proof generation process consists of 6 main steps:

1. Writing the program (already provided in Rust)
2. Compiling the program using MIPS
```
GOOS=linux GOARCH=mips GOMIPS=softfloat go build -C zkm/prover/examples/sha2-go
```
This produces an ELF binary in prover/examples/sha2-go/sha2-go
```
export ELF_PATH=$BASEDIR/prover/examples/sha2-go/sha2-go
```
   
4. Running the program through a prover with inputs
```
cd zkm
HOST_PROGRAM=sha2_go \
    cargo run --release --example zkmips prove_host_program
```
6. Receiving the proof as output
7. Generating a verifier contract from the ImageID of the program
8. Posting the proof to the verifier contract

## The Rust Program

The core of this project is a Rust program that:

1. Accepts two inputs: a public SHA256 hash and a private input value
2. Computes the SHA256 hash of the private input
3. Verifies that the computed hash matches the public input
4. Commits the result to the proof

## Test SDIN
We will test SHA256 of the word BUILDH3R
```
0a0deb40efbe68c236dcefca9bf0891afff84ccd6e0b62eaea18db84e388112b
```

## How to Use This Project

1. Review the Rust code in `HellowWorld.rs`
2. Use the provided interface to input values:
   - Public input: The known SHA256 hash
   - Private input: The value that, when hashed, should produce the public input
3. Click "Generate Proof" to run the proof generation process
   - Note: This process takes about a minute to complete
4. Examine the generated proof


