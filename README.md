# better-rune-derive

This is the `rune-macros` crate from [rune](https://github.com/rune-rs/rune), plus some improvements to make integrating Rune into existing codebases easier. Inspired by the [changes made by ModProg](https://github.com/ModProg/rune) in a PR to an older version of Rune.

## New features

-   `#[rune(constructor_fn = Self::rune_construct)]` item attribute allows you to specify a constructor function you write yourself. It must still specify all arguments, the same as an automatically generated constructor.
-   `#[rune(constructor)]` and `#[rune(constructor_fn)]` now support generating constructors for tuple structs and variants.
-   `#[rune_derive(ADD, DISPLAY_FMT)]` item attribute allows you to automatically implement the ADD, DISPLAY_FMT, DEBUG_FMT, PARTIAL_EQ, EQ and CLONE protocols for your struct using their existing Rust implementations.
-   `#[rune_functions(Self::function_a, Self::function_b)]` item attribute allows you to specify a list of functions to be exported to Rune (automatically added to install_with).
-   `#[rune(boxed)]` field attribute lets you automatically handle a `Box<T>` field, transparently boxing/unboxing when passing to Rune.
-   `#[rune(as_into = String)]` field attribute lets you treat a field as a different type on the Rune side using From/Into implementations
