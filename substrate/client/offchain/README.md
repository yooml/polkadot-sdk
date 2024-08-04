<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Substrate Offchain

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains Substrate offchain workers.

The offchain workers is a special function of the runtime that
gets executed after block is imported. During execution
it's able to asynchronously submit extrinsics that will either
be propagated to other nodes or added to the next block
produced by the node as unsigned transactions.

Offchain workers can be used for computation-heavy tasks
that are not feasible for execution during regular block processing.
It can either be tasks that no consensus is required for,
or some form of consensus over the data can be built on-chain
for instance via:
1. Challenge period for incorrect computations
2. Majority voting for results
3. etc

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sc_offchain).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [GPL 3.0 licensed](https://spdx.org/licenses/GPL-3.0-or-later.html) with [Classpath-exception-2.0](https://spdx.org/licenses/Classpath-exception-2.0.html).
