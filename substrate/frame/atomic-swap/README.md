<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Atomic Swap Pallet

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains the Atomic Swap pallet, for atomically sending funds from an origin to a target.

- [`atomic_swap::Config`](https://docs.rs/pallet-atomic-swap/latest/pallet_atomic_swap/trait.Config.html)
- [`Call`](https://docs.rs/pallet-atomic-swap/latest/pallet_atomic_swap/enum.Call.html)
- [`Module`](https://docs.rs/pallet-atomic-swap/latest/pallet_atomic_swap/struct.Module.html)

## Overview

A module for atomically sending funds from an origin to a target. A proof
is used to allow the target to approve (claim) the swap. If the swap is not
claimed within a specified duration of time, the sender may cancel it.

## Interface

### Dispatchable Functions

- `create_swap` - called by a sender to register a new atomic swap
- `claim_swap` - called by the target to approve a swap
- `cancel_swap` - may be called by a sender after a specified duration

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_atomic_swap).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
