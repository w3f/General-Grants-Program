# Functional correctness verification of core Substrate modules for Polkadot

## Project Description

This grant proposal is in response to the following RFP: <https://medium.com/polkadot-network/apply-to-audit-polkadots-runtime-86c988ced31b>.

The W3F is looking for auditors of the PR (Polkadot Runtime), focusing on the subset of Substrate modules used to implement Polkadot.

-   This includes modules from the Substrate Runtime Module Library (SRML) and some Polkadot specific modules.
-   The modules are written in Rust, and are compiled to Wasm.
-   Of particular interest are authorization/code-execution attacks and denial-of-service attacks on the modules themselves (and thus on Substrate and potentially the network).

An audit at the Rust level will focus on high-level security properties of the code, but will not catch any build-time errors introduced or low-level functional correctness bugs.
We propose formally verifying the generated Wasm code to guard against these bugs and to provide the security auditors with a complete specification of the behaviors of the generated Wasm.
The verification artifacts (K specifications) can be integrated directly into Polkadot’s CI system so that on changes to behavior action must be taken to either fix the code or update the specification.

Our goal with this project is to "cut our teeth" on Wasm verification using KWasm.
Until now we have been focused on EVM verification with KEVM, and need to develop the expertise and (open source) tooling to do the same with Wasm.
For the ecosystem this means a more robust KWasm semantics ready for use in verification tasks, as well as higher-level specification notations to make specification easier.

## Team members

-   Daejun Park: Verification Team Lead
-   Denis Bogdanas: Verification Team Engineer
-   Everett Hildenbrandt: KWasm Semantics Engineer

## Team Website

-   <https://runtimeverification.com/>

## Legal Structure

Runtime Verification, Inc.
102 E. Main Street, Suite 500
Urbana, IL 61801 USA

## Team's experience

-   Developed and maintained KEVM, a formal specification of EVM suitable for both execution and verification: <https://github.com/kframework/evm-semantics>.
-   Verified many EVM smart contracts: <https://github.com/runtimeverification/verified-smart-contracts>.
-   Developed a DSL for making KEVM smart-contract specifications higher-level: <https://github.com/kframework/evm-semantics/blob/master/edsl.md>.

## Team Code Repos

All repos under <https://github.com/kframework> and <https://github.com/runtimeverification> are owned and maintained by Runtime Verification, Inc.

Of particular note are:

-   <https://github.com/kframework/k>: K Framework frontend, enables specifying systems, programming languages, and VMs in a formal notation and deriving tooling from it (eg. interpreter, verification engine).
-   <https://github.com/kframework/evm-semantics>: KEVM, a formal semantics of EVM written in K.
-   <https://github.com/kframework/wasm-semantics>: KWasm, a formal semantics of Wasm written in K.
-   <https://github.com/runtimeverification/verified-smart-contracts>: A repository of EVM smart contracts and their (verified) K specifications.

## Team LinkedIn Profiles

**TODO**

## Development Roadmap

### Deliverables

-   K specifications of one core Substrate runtime module for Polkadot which is <100 lines of Rust.
-   Integration of the K specifications into the Polkadot CI system.
-   Transfer of knowledge on how to maintain and write K specifications to Polkadot developers.

### Milestones

-   *(2 weeks)*
    Meet with Polkadot devs to learn about the core Polkadot modules and select one module which:
    
    a.  is important from a security standpoint due to widespread use,
    b.  is largely frozen in its intended behavior, and
    c.  is ideally <100 lines of Rust source code.

    Agree on the behaviors that need to be specified (as semi-formal English spec).

-   *(6 weeks)*
    Develop the K specification of the selected runtime module, weekly meetings (or more frequently) with Polkadot devs to keep them updated and have them learn how to maintain and write K specifications.

-   *(1 week)*
    Integrate the developed specifications into the Polkadot CI system.
    Note that we will setup the CI integration, then we will discuss with the Polkadot devs how it should be enabled.
    It may be prudent to minimize maintenance overhead by updating the specification less frequently than every PR (instead updating it on a larger release cycle).

## Additional Information

-   What work has been done so far?

    None.

-   Are there are any teams who have already contributed (financially) to the project?

    No.

-   Have you applied for other grants so far?

    No.

-   Are there any other projects similar to yours?

    Security audits are binned in a similar category, but are complementary.
    Verification focuses on making sure the code meets the specification, security audits focus more on making sure that higher-level properties are implied by the implementation.
    Having verified specifications of the code makes a security auditor's job easier because they can reason about the specifications instead of the code itself.

-   How is your project different?

    Security audits don't make sure the code conforms to a correctness specification.
    Instead they inspect the code for potential attack vectors (which is arguably a violation of a correctness specification).
    Auditors equipped with specifications of the code can ignore the code and reason using the specification instead (allowing them to focus on higher-level security properties).

