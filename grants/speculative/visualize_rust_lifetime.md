# General Grant Proposal

* **Project:** Avoiding Rust Deadlocks via Visualizing Lifetime

## Project Overview :page_facing_up: 

### Overview

Rust is a new programming language designed to provide both safety guarantees like high-level languages and performance guarantees like low-level languages. To achieve this design purpose, Rust leverages static compiler checks to rule out severe memory and thread safety issues during compilation. At runtime, Rust behaves like C/C++ and provides performance as good as C/C++. Due to its safety and performance, Rust is increasingly adopted to build safety-critical software, such as OSes and browsers. Rust is also used to implement many software systems in the Web3 technology stack (e.g., substrate, polkadot, ink!).

Rust’s compiler checks are based on a suite of ownership and lifetime rules. The basic rule allows one value to only have one owner variable, and the value is dropped (freed) when its owner variable ends its lifetime. Rust extends the basic rule to allow ownership to be moved and borrowed, but still guarantees all accesses to a value are within its owner variable’s lifetime scope. Besides safety checks, lifetime is also used for automated resource management. For example, there is no explicit Unlock() in Rust. A locking function call returns a reference of the protected variable, and when the reference ends its lifetime, Rust automatically releases the acquired lock (by implicitly calling Unlock()) to avoid lock-without-unlock bugs in C/C++. 

However, Rust’s lifetime rules are unique and complex. It is challenging for Rust programmers to infer where a variable’s lifetime ends. Therefore, it is not uncommon for them to incorrectly identify the location where an implicit unlock is called. When a lock is held longer than programmers’ expectation, the same lock may be acquired again or a different lock may be acquired before releasing the acquired lock, leading to double-lock deadlocks or deadlocks due to acquiring locks in conflicting orders. 

In our previous work, we conducted an empirical study on real-world Rust concurrency bugs. We inspected GitHub commit logs for five Rust applications and five Rust libraries to collect previously fixed concurrency bugs. In total, we found 37 deadlocks due to misunderstanding where the implicit unlock is called, including 30 double locks and seven deadlocks caused by acquiring locks in conflicting orders. Those deadlocks constitute almost all lock-related concurrency bugs (37/38) in our collection. They are from famous Rust software systems (e.g., Servo, Parity-Ethereum, TiKV, Redox), and severely hurt the reliability of those systems before being fixed. 

  
<ins>A brief description of the project.</ins>
  * An indication of how you will integrate this project into Substrate / Polkadot / Kusama.
  * An indication of why your team is interested in creating this project.

### Project Details 
We expect the teams to already have a solid idea about the project's expected final state.

Therefore, we ask the teams to submit (where relevant):
* Mockups/designs of any UI components
* API specifications of the core functionality
* An overview of the technology stack to be used
* Documentation of core components, protocols, architecture etc. to be deployed
* PoC/MVP or other relevant prior work or research on the topic

### Ecosystem Fit 
Are there any other projects similar to yours? If so, how is your project different?

## Team :busts_in_silhouette:

### Team members
* Name of team leader
* Names of team members	

### Team Website	
* https://<your_domain>

### Legal Structure 
Please provide the name and registered address of the legal entity executing the project. When applying via the General Grants program, these details can also be shared privately via the Google Form used for your application.

### Team's experience
Please describe the team's relevant experience.  If the project involves development work, then we'd appreciated if you can single out a few interesting code commits made by team members on their past projects. For research-related grants, references to past publications and projects in a related domain are helpful.  

### Team Code Repos
* https://github.com/<your_repo_1>
* https://github.com/<your_repo_2>

### Team LinkedIn Profiles
* https://www.linkedin.com/<person_1>
* https://www.linkedin.com/<person_2>

## Development Roadmap :nut_and_bolt: 

This section should break out the development roadmap into a number of milestones. Since the milestones will appear in the grant contract, it helps to describe the functionality we should expect, plus how we can check that such functionality exists in the product. Whenever milestones are delivered, we refer to the contract to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions it should be clear how the project is related to Substrate and/or Polkadot. We recommend that the scope of the work can fit within a 3 month period and that teams structure their roadmap as 1 month = 1 milestone. 

For each milestone:
* Please be sure to include a specification of the software. The level of detail must be enough so that we are able to verify that the software meets the specification.
* Please include total amount of funding requested per milestone.
* Please note that we require documentation (e.g. tutorials, API specifications, architecture details) in each milestone. This ensures that the code can be widely used by the community.
* Please provide a test suite, comprising unit and integration tests, along with a guide on how to run these.
* Please commit to providing a dockerfiles for the delivery of your project. 
* Please indicate the milestone duration, as well as number of Full-Time Employees working on each milestone, and include the number of days along with their cost per day.

### Overview
* **Total Estimated Duration:** Duration of the whole project
* **Full-time equivalent (FTE):**  Workload of an employed person ([see](https://en.wikipedia.org/wiki/Full-time_equivalent)) 
* **Total Costs:** Amount of Payment for the whole project. The total amount of funding needs to be below $100k.

### Milestone 1 Example — Implement Substrate Modules 
* **Estimated Duration:** 1 month
* **FTE:**  1
* **Costs:** $5,000

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- |
| 0a. | License | Apache 2.0 / MIT / Unlicense |
| 0b. | Documentation | We will provide both inline documentation of the code and a basic tutorial that explains how a user can (for example) spin up one of our Substrate nodes. Once the node is up, it will be possible to send test transactions that will show how the new functionality works. |
| 0c. | Testing Guide | The code will have proper unit-test coverage (e.g. 90%) to ensure functionality and robustness. In the guide we will describe how to run these tests | 
| 1. | Substrate module: X | We will create a Substrate module that will... (Please list the functionality that will be coded for the first milestone) |  
| 2. | Substrate module: Y | We will create a Substrate module that will... |  
| 3. | Substrate module: Z | We will create a Substrate module that will... |  
| 4. | Substrate chain | Modules X, Y & Z of our custom chain will interact in such a way... (Please describe the deliverable here as detailed as possible) |  
| 5. | Docker | We will provide a dockerfile to demonstrate the full functionality of our chain |

### Milestone 2 Example — Additional features
...

### Community engagement

As part of the Program, we require that you produce an article/tutorial and publish it (for example on [Medium](https://medium.com/)). It should explain your work done as part of the grant. 

Normally, we ask you to submit the write-up upon the completion of your grant, although for larger projects it might make sense to publish multiple articles after the completion of different milestones.

## Future Plans
Please include the team's long-term plans and intentions.

## Additional Information :heavy_plus_sign: 
Any additional information that you think is relevant to this application that hasn't already been included.

Possible additional information to include:
* What work has been done so far?
* Are there are any teams who have already contributed (financially) to the project?
* Have you applied for other grants so far?
