<div align="center">

<img src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png" alt="Polkadot logo" width="200">

# Treasury Pallet

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a pallet, which provides a "pot" of funds that can be managed by stakeholders in the system and
a structure for making spending proposals from this pot.

## Overview

The Treasury Pallet itself provides the pot to store funds, and a means for stakeholders to propose,
approve, and deny expenditures. The chain will need to provide a method (e.g.inflation, fees) for
collecting funds.

By way of example, the Council could vote to fund the Treasury with a portion of the block reward
and use the funds to pay developers.

### Terminology

- **Proposal:** A suggestion to allocate funds from the pot to a beneficiary.
- **Beneficiary:** An account who will receive the funds from a proposal if the proposal is
  approved.
- **Deposit:** Funds that a proposer must lock when making a proposal. The deposit will be returned
  or slashed if the proposal is approved or rejected respectively.
- **Pot:** Unspent funds accumulated by the treasury pallet.

## Interface

### Dispatchable Functions

General spending/proposal protocol:
- `spend_local` - Propose and approve a spend of treasury funds, enables the
  creation of spends using the native currency of the chain, utilizing the funds
  stored in the pot
- `spend` - Propose and approve a spend of treasury funds, allows spending any
  asset kind managed by the treasury
- `remove_approval` - Force a previously approved proposal to be removed from
  the approval queue
- `payout` - Claim a spend
- `check_status` - Check the status of the spend and remove it from the storage
  if processed
- `void_spend` - Void previously approved spend

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_treasury).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
