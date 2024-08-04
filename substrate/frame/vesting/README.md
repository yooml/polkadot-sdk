<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Vesting Module

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a pallet for linear vesting.

- [`Config`](https://docs.rs/pallet-vesting/latest/pallet_vesting/pallet/trait.Config.html)
- [`Call`](https://docs.rs/pallet-vesting/latest/pallet_vesting/pallet/enum.Call.html)

## Overview

A simple module providing a means of placing a linear curve on an account's locked balance. This
module ensures that there is a lock in place preventing the balance to drop below the *unvested*
amount for reason other than the ones specified in `UnvestedFundsAllowedWithdrawReasons`
configuration value.

As the amount vested increases over time, the amount unvested reduces. However, locks remain in
place and explicit action is needed on behalf of the user to ensure that the amount locked is
equivalent to the amount remaining to be vested. This is done through a dispatchable function,
either `vest` (in typical case where the sender is calling on their own behalf) or `vest_other`
in case the sender is calling on another account's behalf.

## Interface

This module implements the `VestingSchedule` trait.

### Dispatchable Functions

- `vest` - Update the lock, reducing it in line with the amount "vested" so far.
- `vest_other` - Update the lock of another account, reducing it in line with the amount
  "vested" so far.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_vesting).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
