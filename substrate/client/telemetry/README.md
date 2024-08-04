<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Substrate Telemetry

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains client telemetry, that allows ingesting telemetry data
with for example [Polkadot telemetry](https://github.com/paritytech/substrate-telemetry).

It works using Tokio's [tracing](https://github.com/tokio-rs/tracing/) library. The telemetry
information uses tracing's logging to report the telemetry data which is then retrieved by a
tracing `Layer`. This layer will then send the data through an asynchronous channel to a
background task called [`TelemetryWorker`] which will send the information to the configured
remote telemetry servers.

If multiple Substrate nodes are running in the same process, it uses a `tracing::Span` to
identify which Substrate node is reporting the telemetry. Every task spawned using sc-service's
`TaskManager` automatically inherit this span.

Substrate's nodes initialize/register with the [`TelemetryWorker`] using a [`TelemetryHandle`].
This handle can be cloned and passed around. It uses an asynchronous channel to communicate with
the running [`TelemetryWorker`] dedicated to registration. Registering can happen at any point
in time during the process execution.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sc_telemetry).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [GPL 3.0 licensed](https://spdx.org/licenses/GPL-3.0-or-later.html) with [Classpath-exception-2.0](https://spdx.org/licenses/Classpath-exception-2.0.html).
