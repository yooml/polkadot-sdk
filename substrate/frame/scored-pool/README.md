<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Scored Pool Module

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

## About

This crate contains a module for a membership pool.

The module maintains a scored membership pool. Each entity in the
pool can be attributed a `Score`. From this pool a set `Members`
is constructed. This set contains the `MemberCount` highest
scoring entities. Unscored entities are never part of `Members`.

If an entity wants to be part of the pool a deposit is required.
The deposit is returned when the entity withdraws or when it
is removed by an entity with the appropriate authority.

Every `Period` blocks the set of `Members` is refreshed from the
highest scoring members in the pool and, no matter if changes
occurred, `T::MembershipChanged::set_members_sorted` is invoked.
On first load `T::MembershipInitialized::initialize_members` is
invoked with the initial `Members` set.

It is possible to withdraw candidacy/resign your membership at any
time. If an entity is currently a member, this results in removal
from the `Pool` and `Members`; the entity is immediately replaced
by the next highest scoring candidate in the pool, if available.

- [`scored_pool::Trait`](https://docs.rs/pallet-scored-pool/latest/pallet_scored_pool/trait.Config.html)
- [`Call`](https://docs.rs/pallet-scored-pool/latest/pallet_scored_pool/enum.Call.html)
- [`Module`](https://docs.rs/pallet-scored-pool/latest/pallet_scored_pool/struct.Module.html)

## Interface

### Public Functions

- `submit_candidacy` - Submit candidacy to become a member. Requires a deposit.
- `withdraw_candidacy` - Withdraw candidacy. Deposit is returned.
- `score` - Attribute a quantitative score to an entity.
- `kick` - Remove an entity from the pool and members. Deposit is returned.
- `change_member_count` - Changes the amount of candidates taken into `Members`.

## Usage

```rust
use pallet_scored_pool::{self as scored_pool};

#[frame_support::pallet]
pub mod pallet {
    use super::*;
    use frame_support::pallet_prelude::*;
    use frame_system::pallet_prelude::*;

    #[pallet::pallet]
    pub struct Pallet<T>(_);

    #[pallet::config]
    pub trait Config: frame_system::Config + scored_pool::Config {}

    #[pallet::call]
    impl<T: Config> Pallet<T> {
        #[pallet::weight(0)]
        pub fn candidate(origin: OriginFor<T>) -> DispatchResult {
            let who = ensure_signed(origin)?;

            let _ = <scored_pool::Pallet<T>>::submit_candidacy(
                T::RuntimeOrigin::from(Some(who.clone()).into())
            );
            Ok(())
        }
    }
}
```

## Dependencies

This module depends on the [System module](https://docs.rs/frame-system/latest/frame_system/).

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_scored_pool).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
