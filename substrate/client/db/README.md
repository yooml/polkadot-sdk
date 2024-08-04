<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Substrate Client Database

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a client backend that is backed by a database.

## Canonicality vs. Finality

Finality indicates that a block will not be reverted, according to the consensus algorithm,
while canonicality indicates that the block may be reverted, but we will be unable to do so,
having discarded heavy state that will allow a chain reorganization.

Finality implies canonicality but not vice-versa.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sc_client_db).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [GPL 3.0 licensed](https://spdx.org/licenses/GPL-3.0-or-later.html) with [Classpath-exception-2.0](https://spdx.org/licenses/Classpath-exception-2.0.html).
