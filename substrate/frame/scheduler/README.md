<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Scheduler Pallet

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a module for scheduling dispatches.

- [`scheduler::Config`](https://docs.rs/pallet-scheduler/latest/pallet_scheduler/trait.Config.html)
- [`Call`](https://docs.rs/pallet-scheduler/latest/pallet_scheduler/enum.Call.html)
- [`Module`](https://docs.rs/pallet-scheduler/latest/pallet_scheduler/struct.Module.html)

## Overview

This module exposes capabilities for scheduling dispatches to occur at a
specified block number or at a specified period. These scheduled dispatches
may be named or anonymous and may be canceled.

**NOTE:** The scheduled calls will be dispatched with the default filter
for the origin: namely `frame_system::Config::BaseCallFilter` for all origin
except root which will get no filter. And not the filter contained in origin
use to call `fn schedule`.

If a call is scheduled using proxy or whatever mechanism which adds filter,
then those filter will not be used when dispatching the schedule call.

## Interface

### Dispatchable Functions

- `schedule` - schedule a dispatch, which may be periodic, to occur at a
  specified block and with a specified priority.
- `cancel` - cancel a scheduled dispatch, specified by block number and
  index.
- `schedule_named` - augments the `schedule` interface with an additional
  `Vec<u8>` parameter that can be used for identification.
- `cancel_named` - the named complement to the cancel function.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_scheduler).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
