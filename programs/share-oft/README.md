# 4626 Solana LZ OFT

Share-mesh program `8NFhuHepc1fFPCZfu2tgPymtruihdSrmFBvjCLjq89g4`.
The closed program `6ste36Y7fcbzJXkVQj3ApEqYb3wFZsZX63gT6wymhy3s` is not upgraded.
Byte length, sha256, rent, and the verify command are in [VERIFY.md](./VERIFY.md).

| | |
|---|---|
| Program ID | `8NFhuHepc1fFPCZfu2tgPymtruihdSrmFBvjCLjq89g4` |
| Framework | Anchor 0.31.1, Rust 1.84.1, platform-tools v1.51 |
| Upstream snapshot | [4626fun/oft-solana-6ste-verifiable](https://github.com/4626fun/oft-solana-6ste-verifiable) |
| LayerZero | [LayerZero-Labs/LayerZero-v2](https://github.com/LayerZero-Labs/LayerZero-v2) rev `c09287a` |

`declare_id!` is this program id. `OFT_ID`, when set, must be the same value. It does not fall back to `6ste36`.

Create the mint and its metadata before mint authority moves to the OFT store. `init_oft` does not set mint authority. `lz_receive` mints only when that authority is the OFT store, or a 1-of-n multisig that includes the store. The launch does not call `admin_set_token_mint_authority`.

A native send burns the bridged amount. A native receive mints it. Token-2022 transfer fee applies to transfers, not to that burn or mint. Init sets the OFT fee to 0 bps.

## Build

```bash
OFT_ID=8NFhuHepc1fFPCZfu2tgPymtruihdSrmFBvjCLjq89g4 \
  cargo-build-sbf --tools-version v1.51 --manifest-path programs/oft/Cargo.toml
```

Deploy `target/deploy/oft.so` only. Do not deploy `target/sbpf-solana-solana/release/oft.so`.

Host tests:

```bash
OFT_ID=8NFhuHepc1fFPCZfu2tgPymtruihdSrmFBvjCLjq89g4 cargo test -p oft
```
