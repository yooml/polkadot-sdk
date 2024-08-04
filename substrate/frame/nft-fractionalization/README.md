<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# NFT Fractionalization Pallet

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a pallet to convert non-fungible to fungible tokens.

## Lock NFT

Lock an NFT from `pallet-nfts` and mint fungible assets from `pallet-assets`.

The NFT gets locked by putting a system-level attribute named `Locked`. This prevents the NFT from being transferred
further. The NFT becomes unlocked when the `Locked` attribute is removed. In order to unify the fungible asset and
unlock the NFT, an account must hold the full issuance of the asset the NFT was fractionalised into. Holding less of the
fungible asset will not allow the unlocking of the NFT.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_nft_fractionalization).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
