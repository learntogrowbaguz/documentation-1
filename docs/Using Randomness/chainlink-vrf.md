---
layout: nodes.liquid
section: ethereum
date: Last Modified
title: 'Introduction to Chainlink VRF'
permalink: 'docs/chainlink-vrf/'
whatsnext: { 'Get a Random Number': '/docs/get-a-random-number/', 'Contract Addresses': '/docs/vrf-contracts/' }
metadata:
  title: 'Generate Random Numbers for Smart Contracts using Chainlink VRF'
  description: 'Learn how to securely generate random numbers for your smart contract with Chainlink VRF (an RNG). This guide uses Solidity code examples.'
---

![Chainlink](/files/a4c6c80-85d09b6-19facd8-banner.png)

> 📘 You are viewing the VRF v2 guide.
>
> If you are using v1, see the [VRF v1 guide](./v1).

Chainlink VRF (Verifiable Random Function) is a provably fair and verifiable random number generator (RNG) that enables smart contracts to access random values without compromising security or usability.

**Table of contents**

- [Overview](#overview)
- [Supported networks](#supported-networks)

## Overview

For each request, Chainlink VRF generates one or more random values and cryptographic proof of how those values were determined. The proof is published and verified on-chain before any consuming applications can use it. This process ensures that results cannot be tampered with or manipulated by any single entity including oracle operators, miners, users, or smart contract developers.

Use Chainlink VRF to build reliable smart contracts for any applications that rely on unpredictable outcomes:

- Building blockchain games and NFTs.
- Random assignment of duties and resources. For example, randomly assigning judges to cases.
- Choosing a representative sample for consensus mechanisms.

To learn more about the benefits of Chainlink VRF v2, see our blog post [Chainlink VRF v2 Is Now Live on Mainnet](https://blog.chain.link/vrf-v2-mainnet-launch/). For help with your specific use case, [contact us](https://chainlinkcommunity.typeform.com/to/OYQO67EF?page=docs-footer) to connect with one of our Solutions Architects. You can also ask questions about Chainlink VRF on [Stack Overflow](https://stackoverflow.com/questions/ask?tags=chainlink).

## Supported networks

Chainlink VRF v2 is currently available on the following networks:

- Ethereum:
  - [Mainnet](/docs/vrf-contracts/#ethereum-mainnet)
  - [Rinkeby testnet](/docs/vrf-contracts/#rinkeby-testnet)
- BNB Chain:
  - [Mainnet](/docs/vrf-contracts/#bnb-chain)
  - [Testnet](/docs/vrf-contracts/#bnb-chain-testnet)
- Polygon (Matic):
  - [Mainnet](/docs/vrf-contracts/#polygon-matic-mainnet)
  - [Mumbai Testnet](/docs/vrf-contracts/#polygon-matic-mumbai-testnet)
- Avalanche:
  - [Avalanche Mainnet](/docs/vrf-contracts/#avalanche-mainnet)
  - [Avalanche Fuji Testnet](/docs/vrf-contracts/#avalanche-fuji-testnet)
- Fantom:
  - [Fantom Mainnet](/docs/vrf-contracts/#fantom-mainnet)
  - [Fantom Testnet](/docs/vrf-contracts/#fantom-testnet)

See the [Contract Addresses](/docs/vrf-contracts) page for a complete list of coordinator addresses and gas price limits.

To learn when VRF v2 becomes available on more networks, follow us on [Twitter](https://twitter.com/chainlink) or sign up for our [mailing list](/docs/developer-communications/).
