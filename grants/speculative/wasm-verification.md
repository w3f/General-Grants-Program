# KPolkadot: K Specification of the Polkadot Runtime

## Project Description

This grant proposal is in response to the following RFP: <https://medium.com/polkadot-network/apply-to-audit-polkadots-runtime-86c988ced31b>.

The W3F is looking for auditors of the PR (Polkadot Runtime), focusing on the subset of Substrate modules used to implement Polkadot.

-   This includes modules from the Substrate Runtime Module Library (SRML) and some Polkadot specific modules.
-   The modules are written in Rust, and are compiled to Wasm.
-   Of particular interest are authorization/code-execution attacks and denial-of-service attacks on the modules themselves (and thus on Substrate and potentially the network).

Our proposal is to specify the behavior of the Polkadot Runtime modules in K.
The specification of the Polkadot Runtime will be combined with that of Wasm (KWasm) to make a specification of the Runtime (KPolkadot).
Because K specifications are executable, the result can be run against the test-sets for the Polkadot Runtime to enusre conformance of the implementation.

For this project, we propose making K specifications of the core Polkadot modules.
We'll focus on a core set of modules (to be discussed) and on transferring knowledge to a selected Polkadot dev about how to write K specifications.
The resulting K specifications can be used both as documentation and as an alternate implementation of the Polkadot Runtime.

Potential extensions of the project (beyond the scope of this grant) include:

-   Finishing the remainder of the modules which are not completed by the end of the project period,
-   Verifying that the compiled Polkadot modules conform to the K specifications, and
-   Instrumenting KPolkadot to run as a full-node on the Polkadot network.

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
-   Hooked KEVM up to the Mantis client to make a full node from the KEVM specification: <https://github.com/kframework/evm-semantics/blob/master/evm-node.md>.

## Team Code Repos

All repos under <https://github.com/kframework> and <https://github.com/runtimeverification> are owned and maintained by Runtime Verification, Inc.

Of particular note are:

-   <https://github.com/kframework/k>: K Framework frontend, enables specifying systems, programming languages, and VMs in a formal notation and deriving tooling from it (eg. interpreter, verification engine).
-   <https://github.com/kframework/evm-semantics>: KEVM, a formal semantics of EVM written in K.
-   <https://github.com/kframework/wasm-semantics>: KWasm, a formal semantics of Wasm written in K.
-   <https://github.com/runtimeverification/verified-smart-contracts>: A repository of EVM smart contracts and their (verified) K specifications.

## Team LinkedIn Profiles

-   <https://www.linkedin.com/company/runtime-verification/>.

## Development Roadmap

### Deliverables

-   K specifications of selected core Substrate runtime modules for Polkadot.
-   Integration with KWasm to be able to execute Wasm transactions on the Polkadot network.
-   Setup a conformance testing harness between Substrate implementation of Polkadot and KPolkadot.
-   Transfer of knowledge to Polkadot devs regarding writing and maintaining K specifications.

### Milestones

-   *(2 weeks)*
    Meet with Polkadot devs to learn about the core Polkadot modules and select several modules which:
    
    a.  are important from a security standpoint due to widespread use, and
    b.  are largely frozen in their intended behavior.

    Agree on the behaviors that need to be specified (as semi-formal English spec).

-   *(6 weeks)*
    Develop the K specification of the selected runtime modules, weekly meetings (or more frequently) with Polkadot devs to keep them updated and have them learn how to maintain and write K specifications.
    Produce documentation describing the specification, including the high-level English specification and arguments that the K specification is a refinement of the English specification.

-   *(1 week)*
    Set up testing harness for ensuring conformance between Substrate and KPolkadot.
    We will setup CI integration on the KPolkadot repository, so that it will run on updates to KPolkadot.
    This will provide some guarantee that the specification is "correct" (that is, that it agrees with the Substrate implementation).

## Additional Information

-   What work has been done so far?

    Most of the KWasm specification (finishing underway).

-   Are there are any teams who have already contributed (financially) to the project?

    No.

-   Have you applied for other grants so far?

    No.

-   Are there any other projects similar to yours?

    Specification often uncovers bugs as the devs work to understand the original implementation.
    Security audits are binned in a similar category, but are complementary.

-   How is your project different?

    We are focused on providing a high-level executable specification of Polkadot, not an audit of the existing implementation.
    The specification can be used by auditors in assessing whether Substrate meets the Polkadot specification.

