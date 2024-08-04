<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Glutton Pallet

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

# WARNING

**DO NOT USE ON VALUE-BEARING CHAINS. THIS PALLET IS ONLY INTENDED FOR TESTING USAGE.**

## About

This crate contains the `Glutton` pallet, which gets the name from its property to consume vast amounts of resources.
It can be used to push para-chains and their relay-chains to the limits.
This is good for testing out theoretical limits in a practical way.

The `Glutton` can be set to consume a fraction of the available block length and unused weight of a chain. It
accomplishes this by filling the block length up to a ration and utilizing the `on_idle` hook to consume a
specific ration of the remaining weight. The rations can be set via `set_compute`, `set_storage` and `set_block_length`.
Initially the `Glutton` needs to be initialized once with `initialize_pallet`.
## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_glutton).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
