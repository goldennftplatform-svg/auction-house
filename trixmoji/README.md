# TRIXMOJI Ethscriptions auction integration

This fork is preserved as the auction design reference. Its original `PhunksAuctionHouse.sol` uses ERC-721 transfer/ownership APIs and **must not be pointed at the existing TRIXMOJI Ethscriptions minter**. That minter is not an ERC-721 contract.

The compatible adaptation and the shared fixed-price/auction test harness live in our companion fork:

https://github.com/goldennftplatform-svg/ethereumphunks.com/tree/market/trixmoji

Clone that repository and run in its `trixmoji` directory:

```sh
npm ci --ignore-scripts
npm test
npm run sandbox
```

Then open http://127.0.0.1:8895. It uses generated accounts and fake ETH on a disposable local chain. No real wallet is connected and no real Ethscription is moved.

The adaptation supports multiple seller auctions, reserve prices, 5% increments, 5-minute anti-sniping extensions, outbid withdrawal credits, no-bid returns, and permissionless settlement. It replaces ERC-721 transfer calls with ESIP-2 Ethscriptions transfer events and requires a trusted indexer-signer approval before an auction starts. See the companion README for the trust model and remaining mainnet launch work.

The original GPL-3.0 Solidity notices (including Zora/Nounders/ogkenobi attribution) remain intact. The new adapted contract is GPL-3.0. The top-level CC0 license must not be interpreted as removing those file-level notices.

This fork is not a deployed auction marketplace. Do not run the original ERC-721 deployment script for these Ethscriptions.
