# QFORGE — The Quantum Computing Marketplace

Quantum computing, accessible to everyone. A Solana-based marketplace where developers, researchers and AI agents run quantum jobs and pay per compute.

The whole site is one self-contained file: `index.html` (styles, scripts and logo are built in). No build step, no dependencies.

## Files

```
index.html    The website
404.html      Not-found page
vercel.json   Vercel headers
robots.txt
```

## Deploy to Vercel

1. Put these files at the **root** of your GitHub repo on the `main` branch.
2. Vercel → Add New → Project → import the repo.
3. Framework preset **Other**; leave Root Directory, Build Command and Output Directory empty.
4. Deploy. Every push to `main` redeploys.

## Configuration

Near the bottom of `index.html`, find `window.QFORGE_CONFIG`:

| Key       | Purpose                                                              |
|-----------|----------------------------------------------------------------------|
| `cluster` | `mainnet-beta`, `devnet` or `testnet`                                |
| `rpcUrl`  | RPC endpoint for that cluster (use a dedicated provider on mainnet)  |
| `apiBase` | Job API base URL; `POST {apiBase}/jobs` receives `{ backend, shots, payWith, wallet }` |
| `qrngUrl` | Endpoint returning `{ "seed": "<hex>" }` from a quantum RNG job      |

It ships on **devnet** so you can test the coin launch safely. Switch to `mainnet-beta` with a mainnet RPC to go live.

## Run locally

```bash
npx serve .
```

## Disclaimer

Quantum advantage is not guaranteed for any workload. Nothing on this site is an offer to sell tokens or investment advice.
