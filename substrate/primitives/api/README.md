<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Substrate Runtime API Primitives

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains the primitives related to the Substrate Runtime API.

The Substrate runtime api is the crucial interface between the node and the runtime.
Every call that goes into the runtime is done with a runtime api. The runtime apis are not fixed.
Every Substrate user can define its own apis with
[`decl_runtime_apis`](https://docs.rs/sp-api/latest/sp_api/macro.decl_runtime_apis.html) and implement them in
the runtime with [`impl_runtime_apis`](https://docs.rs/sp-api/latest/sp_api/macro.impl_runtime_apis.html).

Every Substrate runtime needs to implement the [`Core`] runtime api. This api provides the basic
functionality that every runtime needs to export.

Besides the macros and the [`Core`] runtime api, this crates provides the [`Metadata`] runtime
api, the [`ApiExt`] trait, the [`CallApiAt`] trait and the [`ConstructRuntimeApi`] trait.

On a meta level this implies, the client calls the generated API from the client perspective.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sp_api).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
