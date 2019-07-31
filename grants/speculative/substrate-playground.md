# Substrate playground

## Project Description

This project will create a web-based playground allowing people
interested in Substrate to quickly make tweaks and test out ideas.
Having such a playground lowers the barrier to entry — a user
doesn't need to spend hours compiling code to perform their first
code modification. It's also invaluable for collaborative debugging
and communication when requesting help.

## Team members

* [Jake Goulding](https://github.com/shepmaster)

## Team Website

* https://integer32.com/

## Legal Structure

Integer 32, LLC.

## Team's experience

I am the creator and primary maintainer of the Rust Playground,
for the last 3 years. I have been using Rust for about 5 years and
web technologies for 10.

## Team Code Repos

* https://github.com/integer32llc/rust-playground

## Development Roadmap

### Milestone 1

The playground will allow end-users to modify Substrate's
`new_module.rs` and `chainspec.json` and a list of extrinsics.
Upon submission, these files will be combined with a pre-built
copy of Substrate. These files will be compiled and the blockchain
started on success. Compilation failures will be reported to
the user. The blockchain will be allowed to run for a fixed amount
of time and the resulting generated blocks will be shown to the user.

#### Details

- I will use Substrate 1.0
- The server is written in Rust and the code runs in a Docker image
- Initial editing templates for the three files will be provided
- The user will have a request-response experience; submitting
  the configuration will compile the code and run it, returning the
  results to the user

#### Schedule

As I am starting from the open source Rust Playground code base,
it is anticipated that this should move rapidly. Major differences
include:

- Differing libraries to pre-build
- Editing of multiple input files
- Differing executables to run after the code is compiled

15 workdays should allow stripping down the existing Rust
Playground to remove superfluous configuration, adding new UI for
multiple files, and plumbing together all of the data.

### Milestone 2

Allow user to modify version of Substrate to use.

#### Schedule

I assume that the relevant versions of Substrate have similar command
line APIs, so this should not take much time.

3 workdays.

### Long term

Our hope is that the Web3 Foundation will take over the day-to-day
maintenance of the playground and improve it to meet the needs of
the community as they use it more and more.

We would love to continue to be involved with the Web3 Foundation
for other Rust-related work!

## Additional Information

I have the unique ability to work closely with Bill Laboon,
a W3 member who is keen to see this playground functional.
They are likely to be a good source of feedback and guidance.

I am able to start work from the Rust Playground, an open
source project that greatly mirrors the Substrate Playground in
architecture.

Hosting of the service is done via Amazon EC2 and has been very
cost-effective for the Rust Playground.
