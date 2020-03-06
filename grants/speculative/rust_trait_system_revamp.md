# Rust Trait System Revamp

## Project Description
We want to improve the Rust trait system, to offer more profiling insight and remove redundant work, in order to ultimately increase its performance.

This will help speed up compilation of Substrate / Polkadot crates, as they rely a lot on Rust traits, including type-level metaprogramming with associated types.

Our team has previously investigated Polkadot compile times, which resulted in [`rust-lang/rust#66821`](https://github.com/rust-lang/rust/pull/66821) being merged upstream, giving the `polkadot-runtime` crate an almost 3x speed-up for release mode compilation.

## Team members
* Eduard-Mihai Burtescu
* Ana-Maria Mihalache
* Ioan-Valentin Lazureanu

## Team Website
* https://lyken.rs

## Legal Structure
"Lyken Software Solutions SRL", a LLC registered in Romania.
Full details shared via the associated Google Form.

## Team's experience
Eduard-Mihai Burtescu has been working the Rust Compiler for the past 6 years, and [is a top contributor](https://github.com/rust-lang/rust/graphs/contributors?type=d#contributors) to [`rust-lang/rust`](https://github.com/rust-lang/rust).

In 2017 he founded Lyken Software Solutions, which has been offering Rust-adjacent software consultancy services, with a specialization in the Rust Compiler. We have since worked with Mozilla and others to improve various aspects of Rust, including speeding up Polkadot compilation for Web3 Foundation, in late 2019.

## Team Code Repos
* [@LykenSol](https://github.com/LykenSol)

## Team LinkedIn Profiles
* https://www.linkedin.com/in/eduard-mihai-burtescu-74a7bb69/
* https://www.linkedin.com/in/ana-maria-mihalache-5071081a4/
* https://www.linkedin.com/in/valentin-l%C4%83zureanu-a6563712b/

## Development Roadmap

### Milestone 1 — Low-overhead trait system profiling — 1 month — $10,000
We will implement `-Z self-profile`/[`measureme`](https://github.com/rust-lang/measureme) support for the Rust compiler's trait system operations, using proven techniques to record detailed information without introducing timing inaccuracies.

This kind of fine-grained accurate profiling information will be essential to understanding where time is being spent on redundant work, and where we should focus all further efforts.

### Milestone 2 — Improved trait system caching — 1 month — $10,000
We will increase the effectiveness of caches in the Rust compiler's trait system in a variety of ways, which may include:
* precomputing "type flags" for type/trait system lists, not just types
* introducing fast paths for common simple cases
* distinguishing bounds that mention generic parameters from those that do not
* removing non-global (i.e. per-inference-context) caches
* replacing obsolete "freshening" with the newer "canonicalization"
* caching more of the "trait (impl) selection" process

The above list is not exhaustive, as other opportunities may present themselves.

We will provide measurements across Polkadot and Substrate demonstrating the reduction in compile times from these changes.

### Milestone 3 — Global caching for associated type projection — 1 month — $10,000
We will extend the existing associated type projection caching in the Rust compiler to be shared across the entire compilation, similarly to the rest of the trait system, and including any applicable advances from **Milestone 2**.

We will provide measurements across Polkadot and Substrate demonstrating the reduction in compile times from these changes.

## Future Plans
Long-term, we may contribute to the Chalk project, especially its integration into the Rust compiler and the performance of the resulting system.
But in the meanwhile we will continue to look for potential improvements in the current Rust compiler codebase.

## Additional Information
We have already done some quick and approximate data gathering, which suggests that up to a quarter of `polkadot-runtime-common`'s checking time (i.e. comparable with debug mode build times) is spent doing redundant work in the trait system.
However, acquiring more accurate statistics would only be possible after **Milestone 1** is completed.
