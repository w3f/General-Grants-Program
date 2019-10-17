# ink! Remix Plugin

## Project Description
Implementing fully-fledged IDE with React frontend inside Remix (as a remix plugin) and backend (Node.js) with websocket connection between the two. 

The backend will then connect to multiple instances of ink! CLI running on multiple hosts all managed by Kubernetes. 

The whole backend and CLI part would be built on kubernetes with autoscaling as the most performance consuming part are ink! CLI’s themselves. Both backend and ink! CLI will be dockerized. 

Standard REST API requests can’t be used here as timeout would often happen on long build times and that is not a feasible solution. Usage of websockets solves this problem.

Further on deploy command to multiple networks would be built at the top when ink! team implements this inside CLI.

## Team members
* Edi Sinovčić
* Darko Mačešić

## Team Website
* https://blockchain-it.hr/

## Legal Structure
Company in Republic of Croatia

## Team's experience
* Edi is a blockchain architect and technical writer working on multiple projects in the blockchain space with previous experience working for both RChain and Ethereum. Similar tool that he has built is https://rchain.cloud/ where he learned a lot about scalling solutions like this and UX. Also a DevOps guy that is fascinated by power of modern tools like Kubernetes. (https://github.com/edisinovcic)
* Darko is a senior full-stack developer specialized in Spring, Node.js and React development with extensive knowledge of linux systems. (https://github.com/dark64)

Companies Github: https://github.com/blockchain-it-hr

We've also previously built ZoKrates as a Remix plugin (zkSNARKs on Ethererum) that is wasm based and it runs all inside React plugin and rchain.cloud which is a IDE built on the same principle as our proposition.

## Team Code Repos
* https://github.com/blockchain-it-hr/ink-remix-plugin

## Team LinkedIn Profiles
* https://www.linkedin.com/in/edi-sinovcic/
* https://www.linkedin.com/in/darko-macesic/

## Development Roadmap

Milestone 1: Building base Remix plugin and backend separately (4 weeks)

* Building base React project as a Remix plugin 
* Compile button to compile code (in the future deploy button will also be added as other commands become available inside CLI)
* Building Node.js backend with websockets connection to frontend
* Building docker containers for frontend, backend and ink! CLI
* Setting up CI using GitHub actions
* Deploying on development environment on develop.ink-remix.blockchain-it.hr

Milestone 2: (4 weeks)

* CD part of the CI/CD pipeline with Kubernetes template for backend and CLI
* Running testnet on development, staging and later production environments (testnets can be restarted periodically)
* On frontend Download button for .wasm and ABI will be added
* Stress testing CLI and backend on a staging server
* Setting up staging environment staging.ink-remix.blockchain-it.hr
* Adding tests for backend
* Adding tests for frontend
* Showing error output to the user on the frontend
 
Milestone 3: (3 weeks)

* Writing documentation for the frontend, backend, and kubernetes part
* Creating a production environment and geo-distributing Kubernetes nodes so it’s a more resilient environment and stress testing it

Future plans:
In the future version control and using local compiler (that runs on host machine) will be available. Also standalone option for the plugin as fully-fledged IDE is an option.

## Additional Information.

### Are there are any teams who have already contributed (financially) to the project?
Currently we are looking for other means of financing the project as well.

### Have you applied for other grants so far?
No

### Are there any other projects similar to yours?
Polkadot-js - https://github.com/polkadot-js/apps
Remix - https://remix.ethereum.org/

## How is your project different?
* We are integrating with the most used IDE in the Ethereum ecosystem and would gain a lot by using well knows ecosystem most Ethereum developers know with no need to transfer to something new and by that gain tracktion and usage of this tool by that.
