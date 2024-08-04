<div align="center">

<img
alt="Polkadot logo" width="200"
src="https://raw.githubusercontent.com/paritytech/polkadot-sdk/rzadp/readmes/docs/images/Polkadot_Logo_Horizontal_Pink_BlackOnWhite.png">

# Randomness Module

This crate is part of the [Polkadot SDK](https://github.com/paritytech/polkadot-sdk/).

</div>

# DO NOT USE IN PRODUCTION

The produced values do not fulfill the cryptographic requirements for random numbers. Should not be used for high-stake
production use-cases.

## About

This crate contains The Randomness Collective Flip module, which provides a
[`random`](https://docs.rs/pallet-insecure-randomness-collective-flip/latest/pallet_insecure_randomness_collective_flip/struct.Module.html#method.random)
function that generates low-influence random values based on the block hashes from the previous `81` blocks.
Low-influence randomness can be useful when defending against relatively weak adversaries. Using this pallet as a
randomness source is advisable primarily in low-security situations like testing.

## Public Functions

See the
[`Module`](https://docs.rs/pallet-insecure-randomness-collective-flip/latest/pallet_insecure_randomness_collective_flip/struct.Module.html)
struct for details of publicly available functions.

## Usage

### Prerequisites

Import the Randomness Collective Flip module and derive your module's configuration trait from the system trait.

### Example - Get random seed for the current block

```rust
use frame_support::traits::Randomness;

#[frame_support::pallet]
pub mod pallet {
    use super::*;
    use frame_support::pallet_prelude::*;
    use frame_system::pallet_prelude::*;

    #[pallet::pallet]
    pub struct Pallet<T>(_);

    #[pallet::config]
    pub trait Config: frame_system::Config + pallet_insecure_randomness_collective_flip::Config {}

    #[pallet::call]
    impl<T: Config> Pallet<T> {
        #[pallet::weight(0)]
        pub fn random_module_example(origin: OriginFor<T>) -> DispatchResult {
            let _random_value = pallet_insecure_randomness_collective_flip::Pallet::<T>::random(&b"my context"[..]);
            Ok(())
        }
    }
}
```

## Documentation

The reference about this crate can be found [here](https://paritytech.github.io/polkadot-sdk/master/pallet_insecure_randomness_collective_flip).

In order to learn about Polkadot SDK, head over to the [Polkadot SDK Developer Documentation](https://paritytech.github.io/polkadot-sdk/master/polkadot_sdk_docs/index.html).

To learn about Polkadot, visit the [Polkadot.network](https://polkadot.network/) website.

## License

This crate is [Apache 2.0 licensed](https://spdx.org/licenses/Apache-2.0.html).
