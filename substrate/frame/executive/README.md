<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Executive Module

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a module that acts as the orchestration layer for the runtime. It dispatches incoming extrinsic calls to the
respective modules in the runtime.

## Overview

The executive module is not a typical pallet providing functionality around a specific feature. It is a cross-cutting
framework component for the FRAME. It works in conjunction with the [FRAME System
module](https://docs.rs/frame-system/latest/frame_system/) to perform these cross-cutting functions.

The Executive module provides functions to:

- Check transaction validity.
- Initialize a block.
- Apply extrinsics.
- Execute a block.
- Finalize a block.
- Start an off-chain worker.

### Implementations

The Executive module provides the following implementations:

- `Executive`: Type that can be used to make the FRAME available from the runtime.

## Usage

The default Substrate node template declares the
[`Executive`](https://docs.rs/frame-executive/latest/frame_executive/struct.Executive.html) type in its library.

### Example

`Executive` type declaration from the node template.

```rust
/// Executive: handles dispatch to the various modules.
pub type Executive = executive::Executive<
    Runtime,
    Block,
    Context,
    Runtime,
    AllPalletsWithSystem,
>;
```

### Custom `OnRuntimeUpgrade` logic

You can add custom logic that should be called in your runtime on a runtime upgrade. This is done by setting an optional
generic parameter. The custom logic will be called before the on runtime upgrade logic of all modules is called.

```rust
struct CustomOnRuntimeUpgrade;
impl frame_support::traits::OnRuntimeUpgrade for CustomOnRuntimeUpgrade {
    fn on_runtime_upgrade() -> frame_support::weights::Weight {
        // Do whatever you want.
        frame_support::weights::Weight::zero()
    }
}

pub type Executive = executive::Executive<
    Runtime,
    Block,
    Context,
    Runtime,
    AllPalletsWithSystem,
    CustomOnRuntimeUpgrade,
>;
```

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/frame_executive).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
