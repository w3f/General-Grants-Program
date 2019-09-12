# Tranquility - smart contract programming language

## Project Description

### A brief description of the project.

Tranquility aims to replace Solidity as the go-to language for smart contract
development. Main goal of the language is to allow for more flexibility, while
at the same time improving security and developer experience. The number one
feature of the language is abstracting storage manipulation in an
object-oriented manner.
[Read more in the blog post](https://medium.com/ethworks/tranquility-a-better-smart-contract-programming-language-3038678ba34d).

### Why this project is good for the ecosystem?

Solidity was created as a language for developing smart contracts on Ethereum.
Time and time again it has proven it lacks the needed security and flexibility
to be the best tool for the job. A new programming language will help
developers fill the need to write secure, flexible code.

### How you will integrate this project into Substrate / Polkadot?

One of the planned compilation targets for Tranquility will be WASM. Since
Polkadot supports this natively, the language is a natural fit. Targeting WASM
will open the gate to making the language a universal tool that allows for smart
contract development across chains and ecosystems. 

### Why your team is interested in creating this project?

Ethworks is a software house that offers blockchain solutions. The existing
programming languages are either insecure or inflexible and make programming
smart contracts needlessly difficult. We aim to use the language ourselves to
improve productivity and offer better services to our clients.

## Team members

- Piotr Szlachciak (Team leader)
- Marek Kierejczyk
- Krzysztof Jelski
- (optionally) other developers at Ethworks

## Team Website	

https://ethworks.io

## Legal Structure 

Ethworks sp z o.o.<br>
VAT ID: PL7010771665.<br>
Ignacego Krasickiego 35<br>
02-611 Warsaw, Poland<br>
Office:<br>
Czeczota 29<br>
02-606 Warsaw, Poland

## Team's experience

We have been actively involved in the Ethereum ecosystem for many years, many of
us even before Ethworks was founded. During this time we had the opportunity to
build many widely used tools such as Ethereum.rb (the ethereum library for the
Ruby language) or Waffle (a library for writing and testing smart contracts).

Additionally members of Ethworks are building Universal Login, a tool for
storing funds and connecting to Ethereum applications, aiming to simplify
on-boarding of new users. We are also interested in building programming
languages, for example, we created a small library for writing parsers using
functional programming in JavaScript.

## Team Code Repos

* https://github.com/Ethworks/Waffle
* https://github.com/EthWorks/ethereum.rb
* https://github.com/UniversalLogin/UniversalLoginSDK/
* https://github.com/sz-piotr/parser-combinators
* https://github.com/sz-piotr/tranquility

## Team LinkedIn Profiles

* https://www.linkedin.com/in/piotr-szlachciak/
* https://www.linkedin.com/in/kirejczyk/
* https://www.linkedin.com/in/krzysztofjelski/

## Development Roadmap

### Milestone 1

- Interpreted subset of the language
- 1 month
- $10,000

We will implement a scanner, parser, and interpreter for a subset of the
language, big enough to implement an ERC20 token.

We will deliver an environment where the user can execute their own code and see
the results in the terminal. The environment will also function as a REPL to
allow the user to play with the contract.

We will provide documentation that describes the subset of the language and how
to use the REPL. The runtime will be able to run the contract and execute
functions on it. We will include a set of automated tests for this
functionality.

End requirements:

1. Documentation
    - installation / setup
    - using the REPL
    - language semantics
    - examples of programs
2. Language
    - a set of automated tests that verify the parser
    - variable declaration
    - variable assignment
    - basic expressions (arithmetic, logic, equality)
    - `if`, `else`, `else if`
    - `throw`
    - `storage` (abstraction over smart contract storage)
    - `contract` (similar to Solidity's `contract`)
    - support for reading `msg.sender`
    - emitting events
    - support for booleans, unsigned integers and addresses
    - `print` function
3. Interpreter
    - a set of automated tests that verify the interpreter
    - can execute Tranquility code
    - can report syntax errors
    - can report runtime errors (type mismatch, throw)

### Milestone 2

- Type checking and intermediate representation
- 1 month
- $10,000

We will build a type checker into the language. We will also add a compilation
step, which will output an intermediate representation form. The IR will be
used in the following step as an input to the WASM/EVM compiler.

We will deliver a set of automated tests that verify the type-checker and
intermediate representation. For testing the IR we might explore interpreting
the IR instead of the core language. The type checker also will be available as
part of the REPL delivered in the previous milestone.

End requirements:

1. Type checker
    - a set of automated tests that verify the type checker
    - reports basic type mismatch in expressions
    - infers types for variable declaration (e.g. `let a = 3`, infers that `a` is `Uint`)
    - can the type information present in `contract` method declarations to decode `msg.data`
2. Intermediate Representation (IR)
    - a set of automated tests that verify the IR compilation
    - a set of automated tests that verify the IR interpreter
    - an interpreter capable of running the IR (possibly replacing the existing, high-level interpreter)
    - able to express all language constructions from milestone 1

### Milestone 3

- Compilation to WASM or EVM (determined later)
- 1 month
- $10,000

We will add WASM or EVM as a compilation target. This step will include research
into WASM and EVM compilation as well as improving the existing IR.

We expect this to be the hardest milestone to achieve as it poses many
challenges connected to the tooling of WASM and EVM ecosystems. At a minimum we
will provide basic logic like calling functions and arithmetics compiled to
WASM / EVM. At best we will deliver an environment in which it is possible to
run compiled WASM / EVM code on a Parity node along with the set of Waffle tests
that deploy and call an ERC20 token smart contract.

End requirements:

1. Compilation
    - WASM / EVM bytecode can be produced by the compiler
    - can express arithmetic operations
    - can call functions
2. Integration tests:
    - deploying the compiled code
    - running Tranquility functions
    - checking function output
    - checking revert conditions

### Long term plans

We intend for Tranquility to become a production ready smart contract
programming language that replaces Solidity, because it will provide superior
feature set and developer experience. The grant will allow us to kickstart work
on the project and through rapid iterations arrive at a stage at which users can
play around with the language and provide feedback. We also plan to use
Tranquility in-house to improve the quality of software we produce.

## Additional Information

### What work has been done so far?

A lot of work has been put into working out how the language should work on
paper. Additionally, work has been started on the language itself. We developed
a lexer, parser and interpreter for a tiny subset of the language.

https://github.com/sz-piotr/tranquility

### Are there are any teams who have already contributed (financially) to the project?

No

### Have you applied for other grants so far?

Yes, for the Bridging RFP (https://github.com/w3f/Web3-collaboration/issues/155#issuecomment-531254920).

### Are there any other projects similar to yours? If so, how is your project different?

Languages like Vyper, Flint or Bamboo. All aim to improve upon Solidity, but do
so in ways that reduce flexibility. Only Vyper has gained any traction, but
compared to Solidity it offers limited functionality. None of the
existing languages targets WASM. We aim to provide more options with Tranquility
rather then restricting the programmer.
