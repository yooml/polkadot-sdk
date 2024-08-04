<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Substrate Basic Authorship

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains basic implementation of block-authoring logic.

## Example

```rust
// The first step is to create a `ProposerFactory`.
let mut proposer_factory = ProposerFactory::new(client.clone(), txpool.clone(), None);

// From this factory, we create a `Proposer`.
let proposer = proposer_factory.init(
	&client.header(client.chain_info().genesis_hash).unwrap().unwrap(),
);

// The proposer is created asynchronously.
let proposer = futures::executor::block_on(proposer).unwrap();

// This `Proposer` allows us to create a block proposition.
// The proposer will grab transactions from the transaction pool, and put them into the block.
let future = proposer.propose(
	Default::default(),
	Default::default(),
	Duration::from_secs(2),
);

// We wait until the proposition is performed.
let block = futures::executor::block_on(future).unwrap();
println!("Generated block: {:?}", block.block);
```

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sc_basic_authorship).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [GPL 3.0 licensed](https://spdx.org/licenses/GPL-3.0-or-later.html) with [Classpath-exception-2.0](https://spdx.org/licenses/Classpath-exception-2.0.html).
