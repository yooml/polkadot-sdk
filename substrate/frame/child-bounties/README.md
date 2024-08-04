<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Child Bounties Pallet

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a pallet to manage child bounties.

## Child Bounty

> NOTE: This pallet is tightly coupled with `pallet-treasury` and `pallet-bounties`.

With child bounties, a large bounty proposal can be divided into smaller chunks,
for parallel execution, and for efficient governance and tracking of spent funds.
A child bounty is a smaller piece of work, extracted from a parent bounty.
A curator is assigned after the child bounty is created by the parent bounty curator,
to be delegated with the responsibility of assigning a payout address once
the specified set of tasks is completed.

## Interface

### Dispatchable Functions

Child Bounty protocol:

- `add_child_bounty` - Add a child bounty for a parent bounty to for dividing the work in
  smaller tasks.
- `propose_curator` - Assign an account to a child bounty as candidate curator.
- `accept_curator` - Accept a child bounty assignment from the parent bounty curator,
  setting a curator deposit.
- `award_child_bounty` - Close and pay out the specified amount for the completed work.
- `claim_child_bounty` - Claim a specific child bounty amount from the payout address.
- `unassign_curator` - Unassign an accepted curator from a specific child bounty.
- `close_child_bounty` - Cancel the child bounty for a specific treasury amount
  and close the bounty.

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_child_bounties).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
