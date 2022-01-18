# 🛰️ Terra Crash Course
Beginner Tutorial and Resource for Terra Developer

## Beginner Resource 

- 📚 [Terra Academy Smart Contracts Video](https://academy.terra.money/courses/cosmwasm-smart-contracts-i)

- 👨‍💻 [Official Terra Developer Guide](https://docs.terra.money/Tutorials/Smart-contracts/Overview.html#developer-tools)

- 🧙‍♂️ [Guide for Solidity Developer -> Rust Developer](https://twitter.com/wencol5/status/1478697964071624706?s=20)


## How to ตกเขา By Somnus



## Useful Command Line

### Generate New Project Template 
```rust
cargo generate --git https://github.com/CosmWasm/cosmwasm-template.git --branch 0.16 your-project-name
```
### Building Project (Run in the file that has cargo.toml)
```rust
cargo build
```
### Compile to WASM
```rust
docker run --rm -v "$(pwd)":/code \
  --mount type=volume,source="$(basename "$(pwd)")_cache",target=/code/target \
  --mount type=volume,source=registry_cache,target=/usr/local/cargo/registry \
  cosmwasm/workspace-optimizer:0.11.5
```

## Pitfall

### Memory Limit in Array (128 bits)
```
/// Max key length for db_write/db_read/db_remove/db_scan (when VM reads the key argument from Wasm memory)
const MAX_LENGTH_DB_KEY: usize = 64 * KI;
/// Max value length for db_write (when VM reads the value argument from Wasm memory)
const MAX_LENGTH_DB_VALUE: usize = 128 * KI;
```

### Terra Read Limit (1000 Element)
Keep in mind the terra blockchain has gas limit for read so that pose limitation
for reading/writing large element.


## Audit Report (Oaks & Halborn) 

- 🌳 [Oaks](https://github.com/oak-security/audit-reports)

- [Halborn](https://halborn.com/resources/)

## VSCODE Setup (Useful Extension)

- [Rust (Rust Language Extension)](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust) 

- [Cargo (Package Control)](https://marketplace.visualstudio.com/items?itemName=panicbit.cargo)

- [Crates (Package Control Versioning)](https://marketplace.visualstudio.com/items?itemName=serayuzgur.crates)

## Code Example (Good One IMO)

- [⚓ Anchor(Lending Protocol)](https://github.com/Anchor-Protocol)

- [🪞 Mirror(DEX with Liquidity Mining)](https://github.com/Mirror-Protocol)

- [🌈 Spectrum(Yield Optimizer)](https://github.com/spectrumprotocol)

- [Contract Template (Like OpenZepplin for Terra)](https://github.com/CosmWasm/cw-plus)

- [🌌 Astroport (DEX, LBP, StableSwap)](https://github.com/astroport-fi)

