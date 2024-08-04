<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Transaction Payment Pallet

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a pallet that helps to pay for transactions.

The pallet provides the basic logic needed to pay the absolute minimum amount needed for a
transaction to be included. This includes:
  - _weight fee_: A fee proportional to amount of weight a transaction consumes.
  - _length fee_: A fee proportional to the encoded length of the transaction.
  - _tip_: An optional tip. Tip increases the priority of the transaction, giving it a higher
    chance to be included by the transaction queue.

Additionally, this pallet allows one to configure:
  - The mapping between one unit of weight to one unit of fee via [`Config::WeightToFee`].
  - A means of updating the fee for the next block, via defining a multiplier, based on the
    final state of the chain at the end of the previous block. This can be configured via
    [`Config::FeeMultiplierUpdate`]

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_transaction_payment).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
