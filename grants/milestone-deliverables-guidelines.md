# Milestone Deliverables Guidelines

These are the guidelines to be followed for milestones submitted for evaluation. 
Please submit your milestones by email to grants@web3.foundation.

The submission should contain the following information: 
 * **Name of the grant project**
 * **Link to the open-source code/delivery** 
 * **[License](#license)**
 * **[Documentation](#documentation)**
 * **[Formatted code](#formatted-code), according to a set of guidelines**
 * **[Testing Guide](#testing-guide)**
 * **A list of the [milestone deliverables](#milestone-deliverables)**
 * **Any [additional information](#additional-information)**

## License

In order to successfully receive grant funding for your application it is necessary for the project to have open source code. 
We prefer Apache 2.0, but MIT or Unlicense are also acceptable.

If your delivery comprises multiple repositories, make sure to include the license for them all.

## Documentation

We value high-quality open source code, but even the most performant code is of little use if it lacks proper documentation.

We require that you document (where applicable):
- API calls
- Architecture overview and individual component details
- Algorithms and protocols that are core to your project
- Any other fundamental building blocks to your technology

Note: Only focus on your **own** contributions. Do not write detailed explanations of already existing components, e.g. IPFS. 

## Formatted code
A codebase that is easy to read is also easy to use.

We suggest adopting one style from Day 1 and adhering to it across the entire team.
This helps to keep the commit history clean and facilitates any reviews of the introduced changes.

### Substrate
We strongly recommend formatting your code according to the [official guidelines](https://github.com/paritytech/substrate/blob/master/docs/STYLE_GUIDE.md)

### Rust
We encourage formatting any additional support libraries or helpers by following the [Style Guidelines](https://doc.rust-lang.org/1.0.0/style/README.html).

### Other
For non-Rust deliveries, please commit to a particular style & let us know which official guidelines you adopt.

## Testing Guide

We require that each milestone delivery includes a comprehensive test suite, consisting of:

### Steps demonstrating how your code achieves the milestones.
Please provide documentation on how to install, compile, run and test the deliverable. Make sure to include all necessary pre-requisites.

Depending on the deliverable, this could include (but is not limited to):
- How to embed your library in another application
- How to make example API calls to your service
- Running your web app
- Steps to complete some desired action in your mobile app

### Unit tests
As with any quality software project, each logical code component should be testable. 
 
### Integration tests
We prefer dockerfiles to avoid problems with versions and dependencies.


Documentation must be publicly available, such as a readme file or similar. 
This will make it easier for the community to use or adapt this project.

Note: In some cases, if you are not delivering code as part of your project, such a test suite is not applicable, for example: design, research or hardware. 
If that is the case, please provide detailed instructions on how else we can test your code.

## Milestone Deliverables

Please provide a list of milestone deliverables. This list should closely reflect the list of deliverables shown in Annex 1 of the grant contract.
 
Each item in the list should include a link to the deliverable itself, e.g.:
- Google Doc link - make sure anyone with the link has View access
- GitHub repository - include the appropriate file/folder in the link

If necessary, please highlight anything that deviates from the contract and include further information that you think is relevant to the deliverable.

Please ensure the repo has the correct open-source license.

| Number | Deliverable | Link | Notes |
| ------------- | ------------- | ------------- | ------------- |
| 0a. | License | https://github.com/.../LICENSE | ... | 
| 0b. | Documentation | ... | ... | 
| 0c. | Testing Guide | ... | ... | 
| 1. | ... | ... | ... | 
| 2. | ... | ... | ... | 

## Additional Information

Please add any additional comments that you consider relevant for the evaluation.
