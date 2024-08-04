<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# XCM Emulator

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

XCM-Emulator is a tool to emulate XCM program execution using
pre-configured runtimes, including those used to run on live
networks, such as Kusama, Polkadot, Asset Hubs, et cetera.
This allows for testing cross-chain message passing and verifying
outcomes, weights, and side-effects. It is faster than spinning up
a zombienet and as all the chains are in one process debugging using Clion is easy.

## Limitations

As the messages do not physically go through the same messaging infrastructure
there is some code that is not being tested compared to using slower E2E tests.
In future it may be possible to run these XCM emulated tests as E2E tests (without changes).

As well as the XCM message transport being mocked out, so too are areas around consensus,
in particular things like disputes, staking and iamonline events can't be tested.

## Alternatives

If you just wish to test execution of various XCM instructions
against the XCM VM then the `xcm-simulator` (in the Polkadot
repo) is the perfect tool for this.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/xcm_emulator).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
