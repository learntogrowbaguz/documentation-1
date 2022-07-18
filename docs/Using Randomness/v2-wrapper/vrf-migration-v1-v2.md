---
layout: nodes.liquid
section: ethereum
date: Last Modified
title: 'Migrating to VRF v2'
permalink: 'docs/vrf/v2/wrapper/migration-v1-v2/'
---

> ℹ️ You are viewing the VRF v2 guide.
>
> If you are using v1, see the [VRF v1 guide](/docs/chainlink-vrf/v1/).

## Comparison between VRF v1 and VRF v2 (Wrapper Model)

The main similarity between VRF v1 and VRF v2 Wrapper Model is that consuming contracts have to be funded with LINK in order to pay to request randomness. However, Chainlink VRF v2 includes several improvements.

- **Variable Callback Gas Limit:** Chainlink VRF v2 lets you adjust the callback gas limit when your smart contract application receives verifiable randomness. Consuming contracts can execute more complex logic in the callback request function that receives the random values. Tasks involving the delivered randomness are handled during the response process. The new gas limits are higher than the VRF V1 limit, and vary depending on the underlying blockchain you use. See the gas limits on the [Configuration](/docs/vrf/v2/wrapper/configuration/) page.

- **More configuration capability:** You can define how many block confirmations must pass before verifiable randomness is generated and delivered on-chain when your application makes a request transaction. The range is from 3 to 200 blocks. VRF V1 always waited 10 blocks on Ethereum before delivering on-chain randomness. Select a value that protects your application from block re-organizations while still providing sufficiently low latency from request to response. See the [Security Considerations](/docs/vrf-security-considerations/) page to learn more.

- **Multiple Random Outputs in a Single Request:** The [VRF Wrapper contracts](/docs/vrf/v2/wrapper/configuration/) in VRF v2 allow you to request multiple random numbers (multi-word) in a single on-chain transaction, which reduces gas costs. The fulfillment is also a single transaction, which reduces the latency of responses.

## Updating your applications to use VRF v2

To modify your existing smart contract code to work with VRF v2, complete the following changes. See the [Get a Random Number](/docs/vrf/v2/wrapper/get-a-random-number/) guide for an example.

1. Import and inherit the new [`VRFV2WrapperConsumerBase.sol` contract](https://github.com/smartcontractkit/chainlink/blob/develop/contracts/src/v0.8/dev/VRFV2WrapperConsumerBase.sol) and remove the v1 `VRFConsumerBase.sol` import. This contract includes the `fulfillRandomWords` function.

1. Add a `VRFV2WrapperConsumerBase` constructor as shown in the [Get a Random Number](/docs/vrf/v2/wrapper/get-a-random-number/) example and pass the Wrapper address.

1. You can still call `requestRandomness` function. However, the v2 `requestRandomness` function requires several different parameters (`callbackGasLimit` , `requestConfirmations` , `numWords`). See the [Configuration](/docs/vrf/v2/wrapper/configuration/) page to adjust them for your own needs.

1. Change `fulfillRandomness` function calls to `fulfillRandomWords`. Update the call to handle the returned `uint256[]` array instead of the single `uint256` variable.
