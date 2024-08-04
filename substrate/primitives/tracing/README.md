<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Substrate Timestamp Primitives

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains Substrate tracing primitives and macros.

To trace functions or individual code in Substrate, this crate provides [`within_span`]
and [`enter_span`]. See the individual docs for how to use these macros.

Note that to allow traces from wasm execution environment there are
2 reserved identifiers for tracing `Field` recording, stored in the consts:
`WASM_TARGET_KEY` and `WASM_NAME_KEY` - if you choose to record fields, you
must ensure that your identifiers do not clash with either of these.

Additionally, we have a const: `WASM_TRACE_IDENTIFIER`, which holds a span name used
to signal that the 'actual' span name and target should be retrieved instead from
the associated Fields mentioned above.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sp_tracing).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
