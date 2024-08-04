<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Aura Pallet

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains the Aura pallet, which extends Aura consensus by managing offline reporting.

## Interface

- [`aura::Config`](https://docs.rs/pallet-aura/latest/pallet_aura/pallet/trait.Config.html)
- [`Pallet`](https://docs.rs/pallet-aura/latest/pallet_aura/pallet/struct.Pallet.html)

### Public Functions

- `slot_duration` - Determine the Aura slot-duration based on the Timestamp module configuration.

## Related Modules

- [Timestamp](https://docs.rs/pallet-timestamp/latest/pallet_timestamp/): The Timestamp module is used in Aura to track
consensus rounds (via `slots`).

## References

If you're interested in hacking on this module, it is useful to understand the interaction with
`substrate/primitives/inherents/src/lib.rs` and, specifically, the required implementation of
[`ProvideInherent`](https://docs.rs/sp-inherents/latest/sp_inherents/trait.ProvideInherent.html) and
[`ProvideInherentData`](https://docs.rs/sp-inherents/latest/sp_inherents/trait.ProvideInherentData.html) to create and
check inherents.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_aura).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
