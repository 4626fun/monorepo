# Security policy

## Reporting a vulnerability

If you discover a security issue in the 4626 Solana LZ OFT program
(`8NFhuHepc1fFPCZfu2tgPymtruihdSrmFBvjCLjq89g4`, deployed on Solana mainnet),
please report it privately:

- Email: hello@4626.fun

Please do not open public GitHub issues for security vulnerabilities and do not
exploit issues on mainnet beyond the minimum needed to demonstrate impact.

We will acknowledge reports as quickly as possible and coordinate a fix and
disclosure timeline with you.

## Scope

- This program (LayerZero V2 OFT for the 4626 Base ↔ Solana share mesh) and its
  on-chain accounts (OFT store, peer configs, enforced options).

## Verified build

The built `target/deploy/oft.so` is reproducible from this repository. See the
[README](./README.md) for the build command, byte length, and sha256. The program
is on Solana mainnet. See [VERIFY.md](./VERIFY.md).
