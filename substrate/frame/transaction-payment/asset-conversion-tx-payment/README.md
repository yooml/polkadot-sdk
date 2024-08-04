<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Asset Conversion Transaction Payment Pallet

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a pallet, that allows runtimes that include it to pay for transactions in assets other than the
native token of the chain.

## Overview

It does this by extending transactions to include an optional `AssetId` that specifies the asset
to be used for payment (defaulting to the native token on `None`). It expects an
[`OnChargeAssetTransaction`] implementation analogously to [`pallet-transaction-payment`]. The
included [`AssetConversionAdapter`] (implementing [`OnChargeAssetTransaction`]) determines the fee
amount by converting the fee calculated by [`pallet-transaction-payment`] into the desired
asset.

## Integration

This pallet wraps FRAME's transaction payment pallet and functions as a replacement. This means
you should include both pallets in your `construct_runtime` macro, but only include this
pallet's [`SignedExtension`] ([`ChargeAssetTxPayment`]).

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_asset_conversion_tx_payment).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
