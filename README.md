# 🛰️ Terra Crash Course
Beginner Tutorial and Resource for Terra Developer

## Beginner Resource

- [Terra Academy Smart Contracts Video](https://academy.terra.money/courses/cosmwasm-smart-contracts-i)

- [Official Terra Developer Guide](https://docs.terra.money/Tutorials/Smart-contracts/Overview.html#developer-tools)

- [Guide for Solidity Developer -> Rust Developer](https://twitter.com/wencol5/status/1478697964071624706?s=20)

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

If you want to store large number of items keep it minds that vector has hard limit around 128 bits 
So bucket -> vector
```
/// Max key length for db_write/db_read/db_remove/db_scan (when VM reads the key argument from Wasm memory)
const MAX_LENGTH_DB_KEY: usize = 64 * KI;
/// Max value length for db_write (when VM reads the value argument from Wasm memory)
const MAX_LENGTH_DB_VALUE: usize = 128 * KI;
```

## Audit Report (Oaks & Halborn) 

- [Oaks](https://github.com/oak-security/audit-reports)
- [Halborn](https://halborn.com/resources/)

## VSCODE Setup (Useful Extension)

- [Rust](https://marketplace.visualstudio.com/items?itemName=rust-lang.rust)
- [Cargo](https://marketplace.visualstudio.com/items?itemName=panicbit.cargo)
- [Crates](https://marketplace.visualstudio.com/items?itemName=serayuzgur.crates)

## Code Example (Good One IMO)

