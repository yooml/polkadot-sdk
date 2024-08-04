<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Asset Conversion Pallet

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains the Asset Conversion pallet, which allows assets to be converted from one type to another
by means of a constant product formula.
The pallet based is based on [Uniswap V2](https://github.com/Uniswap/v2-core) logic.

## Overview

This pallet allows you to:

  - create a liquidity pool for 2 assets
  - provide the liquidity and receive back an LP token
  - exchange the LP token back to assets
  - swap 2 assets if there is a pool created
  - query for an exchange price via a new runtime call endpoint
  - query the size of a liquidity pool.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_asset_conversion).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
