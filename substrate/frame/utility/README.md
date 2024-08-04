<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Utility Module

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a stateless module with helpers for dispatch management which does no re-authentication.

- [`utility::Config`](https://docs.rs/pallet-utility/latest/pallet_utility/pallet/trait.Config.html)
- [`Call`](https://docs.rs/pallet-utility/latest/pallet_utility/pallet/enum.Call.html)

## Overview

This module contains two basic pieces of functionality:
- Batch dispatch: A stateless operation, allowing any origin to execute multiple calls in a
  single dispatch. This can be useful to amalgamate proposals, combining `set_code` with
  corresponding `set_storage`s, for efficient multiple payouts with just a single signature
  verify, or in combination with one of the other two dispatch functionality.
- Pseudonymal dispatch: A stateless operation, allowing a signed origin to execute a call from
  an alternative signed origin. Each account has 2 * 2**16 possible "pseudonyms" (alternative
  account IDs) and these can be stacked. This can be useful as a key management tool, where you
  need multiple distinct accounts (e.g. as controllers for many staking accounts), but where
  it's perfectly fine to have each of them controlled by the same underlying keypair.
  Derivative accounts are, for the purposes of proxy filtering considered exactly the same as
  the origin and are thus hampered with the origin's filters.

Since proxy filters are respected in all dispatches of this module, it should never need to be
filtered by any proxy.

## Interface

### Dispatchable Functions

#### For batch dispatch
- `batch` - Dispatch multiple calls from the sender's origin.

#### For pseudonymal dispatch
- `as_derivative` - Dispatch a call from a derivative signed origin.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_utility).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
