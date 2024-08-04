<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Substrate Utils

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains utility primitives for Substrate.

This crate provides `mpsc::tracing_unbounded` function that returns wrapper types to
`async_channel::Sender<T>` and `async_channel::Receiver<T>`, which register every
`send`/`received`/`dropped` action happened on the channel.

Also this wrapper creates and registers a prometheus vector with name `unbounded_channel_len`
and labels:

| Label        | Description                                   |
| ------------ | --------------------------------------------- |
| entity       | Name of channel passed to `tracing_unbounded` |
| action       | One of `send`/`received`/`dropped`            |

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sc_utils).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
