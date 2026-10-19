# Verified build

This tree is program `8NFhuHepc1fFPCZfu2tgPymtruihdSrmFBvjCLjq89g4`.
The closed program `6ste36Y7fcbzJXkVQj3ApEqYb3wFZsZX63gT6wymhy3s` is not this build and is not upgraded.

Build and verify with platform-tools v1.51:

```bash
solana-verify verify-from-repo -um \
  --program-id 8NFhuHepc1fFPCZfu2tgPymtruihdSrmFBvjCLjq89g4 \
  https://github.com/4626fun/monorepo \
  --mount-path programs/share-oft \
  --library-name oft \
  --cargo-build-sbf-args="--tools-version v1.51"
```

Do not pass `-- --tools-version v1.51`. That flag is consumed by plain cargo.

Local `cargo-build-sbf --tools-version v1.51 --manifest-path programs/oft/Cargo.toml` of `target/deploy/oft.so`:

- bytes: `579848`
- sha256: `1af792f4ebf7fe56ddad1727864e232c783bf30c7d08e8fe8690785fd794551a`
- deploy: `--max-len 579848`
- payer at broadcast: `5.893805840` SOL
- locked after the buffer closes: `2.947339800` SOL

Mainnet rent exemption is 2540 lamports per byte-year for two years. The onchain program data account holds `2.946506680` SOL and the program account holds `0.000833120` SOL.

Deployed on Solana mainnet in slot `458655648`. Program data `mtq57nTj7bTxPm23RQ9w5LSU6bQRqj1arzLEgkTxpau`. Upgrade authority `7Qi3WW7q4kmqXcMBca76b3WjNMdRmjjjrpG5FTc8htxY`. Deploy signature `2fku7PFrjQ1JNFJVcFPe16XLbWJrx4hKJSoEBHs8Y91kMKMg1BeLZtxaDNKxVaPsgqJQkDiLPHUdXJVqqffRaVPt`. The dumped program matches the local sha256. This is not the closed program.
