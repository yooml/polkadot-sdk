<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Substrate State Database

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains functionality related to state database maintenance.

It handles canonicalization and pruning in the database. The input to
this module is a `ChangeSet` which is basically a list of key-value pairs (trie nodes) that
were added or deleted during block execution.

## Canonicalization

Canonicalization window tracks a tree of blocks identified by header hash. The in-memory
overlay allows to get any node that was inserted in any of the blocks within the window.
The tree is journaled to the backing database and rebuilt on startup.
Canonicalization function selects one root from the top of the tree and discards all other roots and
their subtrees.

## Pruning

See `RefWindow` for pruning algorithm details. `StateDb` prunes on each canonicalization until pruning
constraints are satisfied.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/sc_state_db).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [GPL 3.0 licensed](https://spdx.org/licenses/GPL-3.0-or-later.html) with [Classpath-exception-2.0](https://spdx.org/licenses/Classpath-exception-2.0.html).
