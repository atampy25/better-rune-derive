# better-rune-derive

This is the `rune-macros` crate from [rune](https://github.com/rune-rs/rune), plus some improvements to make integrating Rune into existing codebases easier. Inspired by the [changes made by ModProg](https://github.com/ModProg/rune) in a PR to an older version of Rune.

## New features

-   `#[rune(constructor_fn = Self::rune_construct)]` attribute allows you to specify a constructor function you write yourself. It must still specify all arguments, the same as an automatically generated constructor.
-   `#[rune_derive(ADD, DISPLAY_FMT, DEBUG_FMT)]` attribute allows you to automatically implement the ADD, DISPLAY_FMT, and DEBUG_FMT protocols for your struct using their existing Rust implementations.
-   `#[rune_functions(Self::function_a, Self::function_b)]` attribute allows you to specify a list of functions to be exported to Rune (automatically added to install_with).
