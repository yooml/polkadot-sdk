<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Multisig Module

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a module for doing multisig dispatch

- [`Config`](https://docs.rs/pallet-multisig/latest/pallet_multisig/pallet/trait.Config.html)
- [`Call`](https://docs.rs/pallet-multisig/latest/pallet_multisig/pallet/enum.Call.html)

## Overview

This module contains functionality for multi-signature dispatch, a (potentially) stateful
operation, allowing multiple signed
origins (accounts) to coordinate and dispatch a call from a well-known origin, derivable
deterministically from the set of account IDs and the threshold number of accounts from the
set that must approve it. In the case that the threshold is just one then this is a stateless
operation. This is useful for multisig wallets where cryptographic threshold signatures are
not available or desired.

## Interface

### Dispatchable Functions

- `as_multi` - Approve and if possible dispatch a call from a composite origin formed from a
  number of signed origins.
- `approve_as_multi` - Approve a call from a composite origin.
- `cancel_as_multi` - Cancel a call from a composite origin.

[`Call`]: ./enum.Call.html
[`Config`]: ./trait.Config.html

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_multisig).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
