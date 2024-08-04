<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Proxy Module

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a module allowing accounts to give permission to other accounts to dispatch types of calls from
their signed origin.

The accounts to which permission is delegated may be required to announce the action that they
wish to execute some duration prior to execution happens. In this case, the target account may
reject the announcement and in doing so, veto the execution.

- [`Config`](https://docs.rs/pallet-proxy/latest/pallet_proxy/pallet/trait.Config.html)
- [`Call`](https://docs.rs/pallet-proxy/latest/pallet_proxy/pallet/enum.Call.html)

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_proxy).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
