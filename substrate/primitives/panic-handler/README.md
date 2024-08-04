<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Substrate Panic Handler

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a custom panic hook with bug report link.

The crate provides the [`set`] function, which wraps around [`std::panic::set_hook`] and
sets up a panic hook that prints a backtrace and invites the user to open an issue to the
given URL.

By default, the panic handler aborts the process by calling [`std::process::exit`]. This can
temporarily be disabled by using an [`AbortGuard`].

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sp_panic_handler).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
