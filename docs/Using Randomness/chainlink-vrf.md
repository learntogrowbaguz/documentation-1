---
layout: nodes.liquid
section: ethereum
date: Last Modified
title: 'Introduction to Chainlink VRF'
permalink: 'docs/vrf/v2/introduction/'
whatsnext: { 'Method 1 : Subscription': '/docs/vrf/v2/subscription/', 'Method 2 : Wrapper': '/docs/vrf/v2/wrapper/' }
metadata:
  title: 'Generate Random Numbers for Smart Contracts using Chainlink VRF'
  description: 'Learn how to securely generate random numbers for your smart contract with Chainlink VRF (an RNG). This guide uses Solidity code examples.'
---

![Chainlink](/files/a4c6c80-85d09b6-19facd8-banner.png)

> 📘 You are viewing the VRF v2 guide.
>
> If you are using v1, see the [VRF v1 guide](/docs/chainlink-vrf/v1/).

Chainlink VRF (Verifiable Random Function) is a provably fair and verifiable random number generator (RNG) that enables smart contracts to access random values without compromising security or usability.

**Table of contents**

- [Overview](#overview)
- [Two methods to request randomness](#two-methods-to-request-randomness)
- [Choosing the right method](#choosing-the-right-method)
- [Supported networks](#supported-networks)

## Overview

For each request, Chainlink VRF generates one or more random values and cryptographic proof of how those values were determined. The proof is published and verified on-chain before any consumer applications can use it. This process ensures that results cannot be tampered with or manipulated by any single entity including oracle operators, miners, users, or smart contract developers.

Use Chainlink VRF to build reliable smart contracts for any applications that rely on unpredictable outcomes:

- Building blockchain games and NFTs.
- Random assignment of duties and resources. For example, randomly assigning judges to cases.
- Choosing a representative sample for consensus mechanisms.

To learn more about the benefits of Chainlink VRF v2, see our blog post [Chainlink VRF v2 Is Now Live on Mainnet](https://blog.chain.link/vrf-v2-mainnet-launch/). For help with your specific use case, [contact us](https://chainlinkcommunity.typeform.com/to/OYQO67EF?page=docs-footer) to connect with one of our Solutions Architects. You can also ask questions about Chainlink VRF on [Stack Overflow](https://stackoverflow.com/questions/ask?tags=chainlink).

## Two methods to request randomness

Chainlink VRF v2 offers two methods for requesting randomness:

- [Subscription](/docs/vrf/v2/subscription/): Users create a subscription account and fund its balance with LINK tokens. Users can then link one or several consumer contracts to the subscription account. When the consumer contracts request randomness, the transaction costs are calculated once the randomness requests are fulfilled and the subscription balance is deducted accordingly. This mode allows the users to fund their use of Chainlink VRF from a single location.
- [Wrapper](/docs/vrf/v2/wrapper/): Very similar to [Connect ANY API](/docs/request-and-receive-data/): Consuming contracts directly pay with LINK when they request for randomness. Hence users have to directly fund their consumer contracts and ensure there are enough LINK tokens to pay for randomness requests.

## Choosing the right method

Depending on your use case, one method might be more suitable than another. The recommendations are the following:

- If your use case requires to regularly request for randomness then choose the subscription method. Otherwise , choose the wrapper method. The wrapper method is more suitable to one-off/seldom requests.
- If you have several VRF consumer contracts then choose the subscription method.
- If you want more control on the maximum gas price to be paid and less gas overhead then choose the subscription method. You can read the [Subscription](/docs/vrf/v2/subscription/) and [Wrapper](/docs/vrf/v2/wrapper/) explanation pages to understand how the transaction costs are calculated.
- Due the wrapper overhead, you can request up to 10 random words in a single request. While with the subscription method, you can request up to 200 random words depending on the network.

## Supported networks

Chainlink VRF v2 is currently available on the following networks:

- Ethereum:
  - Mainnet
  - Rinkeby testnet
- BNB Chain:
  - Mainnet
  - Testnet
- Polygon (Matic):
  - Mainnet
  - Mumbai Testnet
- Avalanche:
  - Avalanche Mainnet
  - Avalanche Fuji Testnet
- Fantom:
  - Fantom Mainnet
  - Fantom Testnet

Depending on the method method that you choose: See the [Subscription Configuration](/docs/vrf/v2/subscription/configuration/) or the [Wrapper Configuration](/docs/vrf/v2/wrapper/configuration/) pages for a complete list of contract addresses and gas price limits.

To learn when VRF v2 becomes available on more networks, follow us on [Twitter](https://twitter.com/chainlink) or sign up for our [mailing list](/docs/developer-communications/).
