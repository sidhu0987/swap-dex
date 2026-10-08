# swap.dex

Self-custodial Stellar DEX front end: live prices, orderbook, path-payment swaps, trustlines,
wallet login (Albedo, Freighter, xBull, LOBSTR, HOT, Ledger, Trezor, WalletConnect) and secret-key login.

Single static file: `public/index.html` (wallet libraries are bundled inside, no build step).

## Deploy on Render
1. Push this folder to a GitHub repo (keep `render.yaml` at the repo root).
2. Render Dashboard > New > Blueprint > pick the repo > Apply.
   (Or New > Static Site: Publish directory `public`, build command empty.)
3. Settings > Custom Domains > add your domain; Render issues HTTPS automatically.

## Before going live: edit the CFG line near the top of the main script in `public/index.html`
- `wcProjectId`: free Project ID from https://cloud.reown.com (needed for WalletConnect / LOBSTR mobile)
- `trezorEmail`: your real contact email (Trezor Connect manifest)

## Notes
- Data comes straight from https://horizon.stellar.org (mainnet). Swaps and orders are real transactions.
- Wallets such as Albedo, xBull and Ledger (WebUSB) need to be served over HTTPS.
