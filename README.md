# SOL Vault — Your First Anchor Program

A personal SOL vault on Solana. Deposit, withdraw, and close your vault using PDAs and CPIs.

## What This Is

This is the foundational Anchor program from the Solana Bootcamp vault tutorial. It teaches:
- Program Derived Addresses (PDAs)
- Cross-Program Invocations (CPIs)
- System Program transfers
- PDA signing with `new_with_signer`

## Instructions

| Instruction | What It Does |
|-------------|--------------|
| `initialize` | Creates your vault state + vault PDA |
| `deposit` | Transfers SOL from your wallet → vault |
| `withdraw` | Transfers SOL from vault → your wallet (PDA signs) |
| `close` | Drains vault + closes state, returns rent |

## Build

```bash
anchor build
```

## Test

```bash
anchor test
```

## Deploy

```bash
solana config set --url devnet
solana airdrop 2
anchor deploy
```

## Key Concepts

- **VaultState**: Stores bumps for the PDAs
- **CpiContext::new**: User signs (deposit)
- **CpiContext::new_with_signer**: PDA signs (withdraw, close)
- **close = user**: Anchor closes state and returns rent

## Next Steps

After mastering this, move to `token_vault` (same patterns, but for SPL tokens).
