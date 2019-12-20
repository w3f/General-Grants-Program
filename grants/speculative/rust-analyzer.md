# IDE support for Substrate via rust-analyzer

## Project Description

**Area:** Development tooling, IDEs

Rust plays a crucial role in the Substrate ecosystem; anyone who is going to use Substrate or ink! would be effectively working with Rust.
Unfortunately at the moment, Rust IDE support is lacking, especially in comparison with the Go ecosystem, which makes Rust less attractive to developers.
By improving IDE tooling for Rust, we make developing smart contracts, Substrate modules, and Substrate itself easier.
[rust-analyzer] is the next generation IDE infrastructure for Rust, which builds on and improves upon [RLS] and [IntelliJ Rust].

The specific focus of this 3-month project is on integration with Substrate Playground, support for macros, and performance: major problems identified by Substrate users and developers.

## Team Members

Team Lead: Aleksey Kladov (https://github.com/matklad/)
Team: Ferrous Systems (other main contributors to the project are expected to be Florian Gilcher, Valentina Bauman)

## Team Website

https://ferrous-systems.com/

## Legal Structure 

Ferrous Systems GmbH
Boxhagener Straße 79
10245 Berlin

## Team's Experience

Aleksey has many years of experience developing tooling for the Rust language, is a member of Rust IDE team, and a former member of Rust Cargo team.
Aleksey also led development of the [IntelliJ Rust] plug-in at [JetBrains](https://www.jetbrains.com/).

Ferrous Systems is one of the leading Rust consultancies, with numerous Rust team members and world-class experts on the team.

## Team Code Repos

https://github.com/rust-analyzer/rust-analyzer

## Team LinkedIn Profiles

https://www.linkedin.com/company/ferrous-systems/

## Development Roadmap (3 months)

We will require 3 months to complete this project. We intend to have 1 developer full-time and 1 part-time, plus administrative support, at a total cost of 100,000€.

Ideally, we can receive partial payment at the end of each milestone.

We will accept payment in EUR


### Making rust-analyzer More User Friendly (2 weeks) 10,000€

At the moment, [rust-analyzer] is partially an experimental project, and so the onboarding process is complicated for users who are not already rust experts. Providing a one-click setup process removes potential roadblocks.

**Work Items:**
* Provide binary releases of rust-analyzer
* Establish the release process for the VS Code extension
* Review default settings to make them more appropriate for Substrate-scale projects
* Review and improve documentation for new Substrate users

**Deliverables:** correspond to work items

### Adding rust-analyzer to Substrate Playground (5 weeks) 35,000€

The main problem with developing Substrate modules is high compile time.
The initial build of a simple node template takes dozens of minutes.
Rust-analyzer can help alleviate this issue in two ways:
* it provides IDE features *without* building the code, and should be ready significantly faster than the full build
* it can be integrated with Substrate playground to provide IDE support

**Work Items:**
* Analysis of playground architecture
* Changes to rust-analyzer to enabled integeration with Playground
* Playground-specific optimizations for rust-analyzer (such as sharing analysis results among several playground instances)

**Deliverables:** rust-analyzer is integrated with the playground and provides IDE features like completion to users OR A documented delivery of goals that were achieved, and a written report of blockers preventing the above goals, and suggestions for further research on the initial topics.

### Performance improvements: (3 weeks) 30,000€

Substrate is a relatively large Rust project, and users of Substrate suffer from long compile times. 
rust-analyzer at the moment also has some performance issues when working with projects that depend on Substrate. Optimizing rust-analyzer will make Substrate users and developers more productive.

**Work Items:**
* Instrumentation for measuring, narrowing and reproducing of performance problems in specific codebases
* Analysis and optimization of startup time
* Analysis and optimization of memory usage

**Deliverables:** performance measurements on the Substrate repository

### Support for code inside macros: (2 weeks) 25,000€

Substrate API uses Rust's declarative macros. 
At the moment, users of these macros do not have access to some IDE features, which hurts productivity.

**Work Items:**
* Completion
* Syntax highlighting
* Extend selection
* Documentation for new features

**Deliverables:** above features inside macro calls just like they currently work outside of macro calls.

### Misc (distributed throughout the project)

**Work Items:**
* Communication with Substrate team to identify and fix the most important pain-points
* Video tutorial showing how to use rust-analyzer effectively to develop a substrate module

### Timeline

The estimated amount of work here is three months, but there are several independent items of work which can be delivered continuously. The work is scheduled to start somewhere in January. The work will be suspended during the Ferrous all-hands (January 20-24), as well as the Rust all-hands (March 16 - 20).

### Further Plans

rust-analyzer is a long-term project, which will be continued afterwards, with the eventual goal of merging with mainline compiler.

An interesting high-value for Substrate ecosystem goal is full support for procedural macros. It is not included in the present roadmap, because Substrate still mainly uses declarative macros, and not procedural macros, so other areas will have a greater impact on Substrate user's experience.

## Additional Information

* What work has been done so far? 

rust-analyzer already exists and can be installed by following instructions on https://rust-analyzer.github.io/

* Are there are any teams who have already contributed (financially) to the project?

Up to this moment, part-time work on rust-analyzer was sponsored by Ferrous Systems, Mozilla, and via Open Collective. 

* Are there any other projects similar to yours? If so, how is your project different?

At the moment, there are two other "IDE engines" for the Rust language. 

1. IntelliJ Rust, which is specific to IntelliJ platform.
2. RLS, which is the older "official" solution by the rust-team. 

[IntelliJ Rust] at the moment is the most advanced solution, but it can't be used outside of a [JetBrains IDE](https://www.jetbrains.com/opensource/idea/). [RLS] has significant architectural problems and, for example, can't provide correct completions despite being in development for several years. 

[rust-analyzer] builds upon experiences of both projects (@matklad led development of [IntelliJ Rust] and contributed to [RLS]), already has more features than RLS, and can be adapted for Substrate needs.

[RLS]: https://github.com/rust-lang/rls
[IntelliJ Rust]: https://intellij-rust.github.io/
[rust-analyzer]: https://rust-analyzer.github.io/