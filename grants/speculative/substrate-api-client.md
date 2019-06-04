# Substrate API client

## Project Description

This application is a side-effect of our [grant for developing substraTEE](https://github.com/w3f/Web3-collaboration/pull/66). During the implementation of [substraTEE](https://github.com/scs/substraTEE)  we also implemented a Rust websocket client for substrate, released as [substrate-api-client](https://github.com/scs/substrate-api-client). That client is kept very simple and serves its purpose for substaTEE, but at the current state it is more of a code sample than of a production library for general use. [Examples](https://github.com/scs/substrate-api-client/tree/master/src/examples) show how to query chain state, send transfers and listen to events.

On riot, we realized that there's a substantial interest in the dev community for a substrate client written in Rust.

Features to be added to the existing code base

* dynamic API, parsing runtime metadata (current API is static)
  * automatically chose correct signature for accounts based on metadata (Edwards or Schnorr)
  * request list of modules and their functions (i.e. for printing these to stdout for debugging)
* generic type arguments for runtime types like Balances, AccountId aso.
  * the library shall support composing extrinsics to custom runtime modules
* deploy and call ink contracts
* support custom structs for runtime

While we will aim to provide similar support like polkadot-js-api, we're not building a UI nor an interactive shell. So there will be no interactive browsing of state, modules, functions. As account creation and management is already provided by parity's `subkey`, we won't add that to our library neither. 

### Benefit for ecosystem

* Devs can easily write Rust clients for their custom chains. (Today, oo7 and Polkadot-API-js are the quasi standards for web browsers but there is no standard yet for native applications)

Our team is interested in continuing the development of substrate-api-client because we see interest in the community for our value proposition. Moreover, it accelerates Alain Brenzikofer's private not-for-profit cryptocurrency&DID project [encointer.org](https://encointer.org).

## Team members

* Alain Brenzikofer: @brenzi on github, Department Head, Developer
* Marcel Frei: @electronix on github, Project Manager for substraTEE, Developer
* Christian Langenbacher: @clang on github, Developer
* Sabine Proll: @sabinep, Developer
* Juraj Skripsky: @jskripsky on github, Rust-Guru, Reviewer

## Team Website

* https://www.scs.ch/en/about-scs/departments/decentralized-systems/

## Legal Structure

Swiss AG

## Team's experience

As an engineering services company SCS AG has more than 25 years of experience in the fields of electronics, software and system design. Profound know-how, solid methodological competence as well as efficient project management are the foundation of our success.

Most programming experience in the following languages: C/C++, C#, Java, Python and VHDL.

Alain Brenzikofer follows Blockchain developments since 2011. He works for SCS since 2012 where he started working on blockchain projects in 2016 and was appointed to lead a new department for "Decentralized Systems" in summer 2018. As a private initiative, he designed a new cryptocurrency ecosystem [encointer - An Ecological, Egalitarian and Private Cryptocurrency and Self-Sovereign Identity System](https://encointer.org) . A project he currently intends to realize based on Substrate (including this privacy extension).

Our team is part of the [Quartierstrom project](https://quartier-strom.ch), implementing and currently field-testing a decentralized P2P energy market in Switzerland together with ETHZ, Bosch IoT Lab, HSLU and others.
SCS is in charge of the development of a dynamic grid usage-tariff smart contract as well as privacy-by-design concepts for the decentralized energy auction, thereby investigating and evaluating Zero-Knowledge Proofs, Linkable Ring Signatures, Multi-Party Computation as well as Trusted Execution Environments.

Moreover, we've developed a PoC for Electric Vehicle charging process on blockchain based on Parity Ethereum: https://youtu.be/xJUKNlV79pg

For trusted sensor oracles, Alain wrote a [whitepaper on decentralized trusted timestamping](https://www.scs.ch/wp-content/uploads/2017/01/trusted-sensor-whitepaper.pdf).

Alain, Marcel and Christian are the core developers for substraTEE.

A few further blockchain projects are subject to NDAs.

## Team Code Repos

* https://github.com/scs/substraTEE
* https://github.com/scs
* https://github.com/brenzi
* https://github.com/encointer

## Team LinkedIn Profiles

(Not all on LinkedIn)

https://www.linkedin.com/in/alain-brenzikofer-9a4480165/

https://www.linkedin.com/in/christian-langenbacher-baa629182/

https://www.linkedin.com/in/juraj-skripsky-4338a217/

https://www.linkedin.com/in/sabine-proll-5a7118153/

## Development Roadmap

We intend to base this work package on [substrate-api-client](https://github.com/scs/substrate-api-client).

Tasks have been described above.

As substrate isn't stable yet, we will deliver based on recent upstream commit. Ongoing integration work is not part of the requested budget.

### Timeline

- T0: Project start: favorably by end of July 2019
- M1: T0 + 4 weeks (subject to holiday plans, TBD when start date is known)
