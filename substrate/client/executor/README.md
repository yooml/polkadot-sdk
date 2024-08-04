<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Substrate Executor

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate provides means of executing/dispatching calls into the runtime.

There are a few responsibilities of this crate at the moment:

- It provides an implementation of a common entrypoint for calling into the runtime, both
wasm and compiled.
- It defines the environment for the wasm execution, namely the host functions that are to be
provided into the wasm runtime module.
- It also provides the required infrastructure for executing the current wasm runtime (specified
by the current value of `:code` in the provided externalities), i.e. interfacing with
wasm engine used, instance cache.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sc_executor).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [GPL 3.0 licensed](https://spdx.org/licenses/GPL-3.0-or-later.html) with [Classpath-exception-2.0](https://spdx.org/licenses/Classpath-exception-2.0.html).
