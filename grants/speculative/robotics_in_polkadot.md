Robotics integration in Polkadot
================================

Objective: to improve the integration of robotics with parachains of the Polkadot network.

Project Description
-------------------

The Polkadot network is useful for robotics developers. Installing the network client will help engineers to engage capabilities of decentralized technologies in a robotic system. For example, to control an autonomous robot through a decentralized application.
The best way for that is creating a bridge between the Polkadot client and the ROS framework. ROS ([Robot Operating System](http://ros.org)) is the most popular open source framework for robotics development. Stats of ROS usage: http://download.ros.org/downloads/metrics/metrics-report-2018-07.pdf. Now ROS supports more than 100 different models of existing robots.

I am one of the core developers of the Robonomics project ([robonomics.network](https://robonomics.network)). Since 2015, we have been experimenting with the use of decentralized technologies, in particular we use the Ethereum platform for managing cyber-physical systems (CPSs). A CPS performs its work providing a service to the end user on signal that contains both financial and technical information. Such an approach seems to be useful in the concepts of Smart cities and Industry 4.0. In these concepts, Cyber-physical systems are often presented as autonomous services that provide services directly to the user: drone delivery, a 3D-printer in a subway station, a smart factory, an autonomous sensor network and inter-machine services.

Today we are expanding support for Robonomics towards the Polkadot network, so that the robotics community will have an opportunity to use not only Ethereum, but also the closest alternatives. You can see the current results in the [repository on GitHub](https://github.com/airalab/substrate-node-robonomics).

In this application, I propose to add two features, which will be useful for the Polkadot ecosystem, to the existing development:

1. to use a token from any parachain in the signal to launch the robot;
2. to use meta-information about the task performed by the robot in other parachains.

Today Robonomics on Substrate allows you to run a ROS-compatible robot using a signal in the [Robonomics substrate-chain](https://telemetry.polkadot.io/#/Robonomics). Also, according to the result of task execution, the robot publishes a log of operations in IPFS and settles the hash of the saved log in the Robonomics substrate-chain as a result of the program execution. As part of the grant, I will extend the runtime module of the robot launch in order to implement the paragraphs (1) and (2).

Team members
------------

* Alexander Krupenkin

Team Website
------------

* https://aira.life
* https://robonomics.network

Legal Structure
---------------

Individual

Team's experience
-----------------

* ITMO MSc, Mechatronics and Robotics (Saint-Petersburg, Russia)
* Open-source contributions: ros_comm, roshask, haxr, hs-web3
* Since 2015 - Ethereum application developer

Team Code Repos
---------------

* https://github.com/airalab/substrate-node-robonomics
* https://github.com/airalab/substrate-node-robonomics/tree/parachain

Team LinkedIn Profiles
----------------------

* https://www.linkedin.com/in/krupenkin/

Development Roadmap
-------------------

* Inter-chain communication:
    - using asset transfer proof from another parachain (weeks 0-4);
    - transfer proof adoption for robot liability execution process (weeks 4-6);
    - share liability metadata with another parachains (weeks 6-9).
* Add `ros-integration` feature to polkadot node (weeks 9-12).
* Integrate all parts together and works as intended (weeks 12 - 14).

Ideally, we can receive part payment at the end of each milestone: $2400. 
Total cost: $12000

We would be willing to consider part payment in DOTs, up to 100%.

Additional Information
----------------------

* Robonomics Whitepaper: https://robonomics.network/robonomics_white_paper_en.pdf
* Robonomics on Substrate demo: https://github.com/airalab/substrate-node-robonomics/tree/master/examples/turtlesim_liability
