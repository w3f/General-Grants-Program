# P.A.N.I.C. by Simply VC

## Project Description

P.A.N.I.C. by Simply VC is a powerful and lightweight open source monitoring and alerting solution for validators. It keeps an eye on the state of one or more nodes and swiftly sends relevant alerts via the multiple alerting channels supported, including email, Telegram, and Twilio phone calls. P.A.N.I.C. is built with user friendliness in mind and a modular design, making it appealing not just for users, but also for developers that wish to unlock its full potential. 

P.A.N.I.C. runs as a standalone app that reads and analyses data from a running validator or node using the available data endpoints exposed by Substrate or otherwise and forwards alerts via the alerting channels that were set up by the user, when appropriate.

The current version of [P.A.N.I.C.](https://github.com/simplyvc/panic) supports monitoring of nodes running on Cosmos chains. Following the positive feedback that we have received from users of P.A.N.I.C, we wish to develop something similar for Substrate-based nodes. Our aim is that P.A.N.I.C. becomes an indispensable tool in the arsenal of serious as well as novice validators. For Simply VC, this project will serve as an opportunity to become more familiar with the ecosystem and as a stepping stone for further contributions. We also hope to raise awareness on the importance of having a suitable monitoring and alerting setup.

## Team members
* Isaac Zarb (Lead)
* Miguel Dingli (Dev)
* Mark Said Camilleri (UX/UI)
* Francesco Cremona (QA)

## Team Website	
* https://simply-vc.com.mt/

## Legal Structure 
Provided in the Google Form.

## Team's experience
- Simply VC is a team of security, cryptocurrency & business experts passionate about supporting the blockchain ecosystem.
- Already built and open-sourced [P.A.N.I.C. for Cosmos validators](https://github.com/SimplyVC/panic).
- In-house experience with UX/UI obtained through the development of [our website](https://simply-vc.com.mt) and internal projects.
- Winners in the Berlin Cosmos hackaton with a [Cosmos-SDK module](https://github.com/ixofoundation/cosmic) that we developed during the hackaton on a very tight schedule.
- Operate validators and nodes for multiple networks from our own data center, including Polkadot (Alexander and Kusama), Cosmos, Chainlink, and Elixxir.

## Team Code Repos
https://github.com/SimplyVC

## Team LinkedIn Profiles
* https://www.linkedin.com/in/isaaczarb
* https://www.linkedin.com/in/migueldingli
* https://www.linkedin.com/in/markscamilleri
* https://www.linkedin.com/in/francescocremona

## Specification and Development Roadmap

## Specification

The resultant P.A.N.I.C. tool written in Python will include:
1. An interactive and user-friendly command-line **setup and re-configuration process**, serving as a guided way of getting the tool up and running, especially for beginners.
2. **Three alerting channels**: email (SMTP), Telegram bots, Twilio calls.
3. A collection of **useful alerts**, possibly including alerts about uptime, peers, slashing, validator sets, referendums, and statistics and changes therein.
4. **Four alert severity levels**, namely INFO, WARNING, CRITICAL, ERROR.
5. A **monitor** (or multiple monitors, if it makes sense to do so) that is able to alert based on the current state, changes in the state, consecutive events, and timed events. The monitor will gather and analyse data about the node, such as the number of peers.
6. **Redis integration** for an in-memory copy of the alerter’s state, to enable querying the alerter’s status or for when the alerter software restarts or gets restarted. Steps on how to run a secure Redis instance will be provided in the documentation.
7. **Interaction with the tool via Telegram bots** to (i) run manual queries, such as for a specific block, (ii) get a live status of the tool, such as the latest update from its components, and (iii) have some control over the tool, such as to snooze phone calls.
8. **A configuration web UI** to facilitate (re-)configuration, such as to add a new node to the alerting, and for fine-tuning of alerts, such as to turn on and off specific alerts.
9. **A dashboard web UI** to visualise alerts (as a form of log), the status of the node, and the status of the alerter itself using the data being held in Redis.

The above specifications fall into three categories:
1. Already a part of the existing tool and require no further work: 2, 4
2. Require adapting from Cosmos to Substrate: 1, 3, 5, 6, 7
3. Completely new features to be built from scratch: 8, 9

## Development Roadmap
To build a tool compliant with the above specifications, the below milestones will be set:
* **Milestone 1 - Adapt P.A.N.I.C. to Substrate (23 MDs)**:
  * Research about data sources and what can be alerted on. This includes reaching out to other users to target the specific needs of the community. The result is a list of alerts, such as “No. of peers decreased from x to y”
  * Implement monitors and alerts, including a data source wrapper with the necessary parsing of data to make querying cleaner and reusable
  * Adapt Telegram interaction to Substrate-based nodes
  * Adapt Redis integration to Substrate-based nodes
  * Implement setup and re-configuration process
  * Unit, integration, and system testing and optimisations
  * Package the working product as a docker container
  * Basic documentation on design and setup
* **Milestone 2 - Implement web UIs (19 MDs)**:
  * Design and mockups
  * Implementation and connections to P.A.N.I.C. for the configuration UI
  * Implementation and connections to P.A.N.I.C. for the dashboard UI
  * Testing and optimisations
  * Add the two web UIs to the docker container
  * Basic documentation on design and setup
* **Milestone 3 - Documentation and Further Testing (11 MDs)**:
  * Security assessment
  * Documentation equivalent in detail to that in v1.0.0 of the current P.A.N.I.C on the design and features of its various components of the tool
  * Documentation equivalent in detail to that in v1.0.0 of the current P.A.N.I.C on the setup and running of the tool, including steps on how to set up the tool’s requirements, such as installing Python and creating Telegram bots
  * Closed beta system testing
  * Community acceptance testing
  * Video showcasing setup and usage of the tool

The following deliverables will be available once the milestones are reached:
* At milestone 1:
  * List of alerts that the alerter is able to monitor for and send to the user.
  * Working and tested alerter that satisfies points 1 to 7 of the specification.
  * The alerter packaged as a docker container.
  * Report outlining the results of the testing and any optimisations applied.
  * Basic documentation on design and setup.
* At milestone 2:
  * Working configuration web UI that satisfies point 8 of the specification.
  * Working dashboard web UI that satisfies point 9 of the specification.
  * The two UIs packaged in the same docker container as the alerter.
  * Report outlining the results of the tests and any optimisations applied.
  * Basic documentation on design and setup.
* At milestone 3:
  * Documentation on design and features of the tool and its components.
  * Documentation on setup and running of the tool and its requirements.
  * Report outlining the results of the security assessment.
  * Report outlining the results of the beta system testing.
  * Report outlining the results of the community acceptance testing.
  * Video showcasing setup and usage of the tool.

## Longer-Term
In general, we would like to make further contributions to Substrate and Polkadot, especially through development projects.

Our long-term vision for P.A.N.I.C. specifically is that it focuses more on monitoring and becomes a hub for all of a validator's monitoring and alerting needs, across any blockcain network that the validator is operating on. This would require extending the reach of P.A.N.I.C. to even more networks, gathering all the necessary data that directly or indirectly impacts a validator, and presenting this in a single global interface that allows a validator to visualise the status of their operation and to easily and intuitively set up any alert.

## Additional Information
* What work has been done so far?
  - We have already built and open-sourced [P.A.N.I.C. for Cosmos validators](https://github.com/SimplyVC/panic). Thus, the core components of P.A.N.I.C. have already been thought out and we will be able to focus on the Substrate specific portion of the project.
* Are there are any teams who have already contributed (financially) to the project?
  - No
* Have you applied for other grants so far?
  - No
* Are there any other projects similar to yours? If so, how is your project different?
  - The current monitoring and alerting solutions, such as [Polkabot](https://gitlab.com/Polkabot/polkabot) work from an outside perspective, similar to explorers, whereas P.A.N.I.C. serves as an internal tool for the validator's operator to get informed quickly and directly whenever an important event has taken place, especially ones that might undermine the validator's availability.
