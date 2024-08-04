<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Aura Consensus

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains Aura (Authority-round) consensus in Substrate.

Aura works by having a list of authorities A who are expected to roughly
agree on the current time. Time is divided up into discrete slots of t
seconds each. For each slot s, the author of that slot is A[s % |A|].

The author is allowed to issue one block but not more during that slot,
and it will be built upon the longest valid chain that has been seen.

Blocks from future steps will be either deferred or rejected depending on how
far in the future they are.

NOTE: Aura itself is designed to be generic over the crypto used.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sc_consensus_aura).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [GPL 3.0 licensed](https://spdx.org/licenses/GPL-3.0-or-later.html) with [Classpath-exception-2.0](https://spdx.org/licenses/Classpath-exception-2.0.html).
