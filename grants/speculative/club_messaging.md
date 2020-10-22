# Club - An Instant Messaging Protocol and Network

* **Project:** Club Instant Messaging Protocol and Network

## Project Overview : 

### Overview

  * Club is an instant mesaging protocol that enables real time audio/vedio communication and file transfer.
  It is a decentralized, censorship free messaging network with enconomic incentives on blockchain. 
  * Club supports easy implement of realtime audio and vedio communication as well as file transfer in decentralized application.
  In fact such kind of functions are not found in most messaging protocol such as hopr, status, ally/scrumble, etc. 
  + Offline messaging notification for mobile application is another built-in features in CLUB protocol.
  * Comparing to most instant messenger app today which is centralized, there is no central account system for users, 
  it uses DID(Decentralized Identifier) as the indentity and signature to secure.  
  There is no server either, it will be the blockchain nodes for the messaging relay and route, so there is no service nor maintenance team needed to keep the system running. 
 + There is no single point failure.
 + Privacy, Security and Censorship-resustance is our goal.
  Censorship-resistance is considered to be one of the main value propositions of Bitcoin. 
  The idea is that no nation-state, corporation, or third party has the power to control who can use the network. 
  Censorship-resistance ensures that the laws that govern the network are set in advance and can’t be retroactively altered to fit a specific agenda.
  + We are also developing the front end app based on the background technologies.

 Our target is to make it used by people in crypto world. 

### An indication of how you will integrate this project into Substrate / Polkadot / Kusama.
   + As Gavin Wood pointed out messaging is one of the four components to the post-Snowden Web
  (static content publication, dynamic messages, trustless transactions and an integrated user-interface).
   + As Gavin suggested an identity-based pseudonymous low-level messaging system is used for communicating between people on the network.
    It uses strong-cryptography in order to make a number of guarantees about the messages; 
    they can be encrypted with an identity's public key in order to guarantee only that identity can decode it. 
    They can be signed by the sender's private key to guarantee that it does indeed come from the sender and provide the receiver with a secure receipt of communication. A shared secret can provide the opportunity to communicate securely, including between groups, without the necessity of proof of receipt.
   * We will use the address in Substrate/Polkadot as the identity of the messaging part.
  We are going to use the peer to peer messaging technologies provided by substrate.
   + The CLUB network will not be owned by any individuals or third party.
   Instead, we want to reply on the community of Polkadot to grow our network.
   The CLUB network relies on multiple individuals running CLUB nodes over publicly available infrastructure.
   CLUB nodes can run on the substate nodes in multiple devices and operating systems over the Internet.
   Beyond the Polkadot and Substrate, CLUB provides the important features neeed by distributed application.
   + The CLUB token will be issued on Polkadot. It will be used as the incentive to run CLUB node as well as the use of CLUB.
  Nodes participating in the CLUB network get paid for their services via blockchain payment channels in the form of CLUB tokens. 
  These CLUB tokens can be used within the CLUB network as a means of payment for requesting services from other CLUB nodes.
  
### An indication of why your team is interested in creating this project.
   * Messaging is needed in every application, so does in cryto world. As dapp grow, the need of realtime audio/vedio communication as found in most instant meseenger today
     should be the basic feature of wallet or other kind of decentralized application 
   * In the past few years, the technology and infrastructure of decentralization have made considerable progress,
   but the crypto world is still using traditional communication tools such as WeChat Communication. 
   *  Encouraged by uniswap which build pure decentralized exchange on Ethereum, we are going to build decentralized instant messenger 
   on top of the existing peer to peer network exsited in most blockchain.
   *  As most people still reply on centralized exchanges to trade cryptocurrencies, 
   we are facing the same problem and difficulty as most instant messenger are domanated by single platform and commercial company.
   * In stead of chalendge most existing instant messenger, we are going to use the technologies developed by cryto workd and serve people in crtpto world. 
   the user scale of encrypted currency is at least hundreds of thousands or even millions, it is big enough for us at this stage. 
   * Technically, the messaging technologies is the underline technologies in every blockchain such as Substrate in Polkadot, 
    Whishper in Ethereum, Carrier in Elastos carrier and it can be used to implement peer to peer messaging.
   Based on cryptography, smart contracts, and peer-to-peer communication technologies, it is possible to build a decentralized instant messaging system with ensorship-resistance, which means it can not regulated and 
   controlled by any commercial organization. 

### Project Details 
* Mockups/designs of any UI components
* API specifications of the core functionality
  + IOS and Android CLUB SDK
  + it is a java api set for webrtc connection using peer to peer messaging protocol. 
With the Android CLUB SDK, it is possible to build voip applications for mobile phones, tablets, wearables, TVs and car media systems 
that run on the Android Operating System (OS) while utilizing the functionalities of the Elastos Carrier and WebRTC protocol.

  * WebRTC replys on sigaling protocol to connect peers to build WebRTC connection.
We define and implement a simple protocol to build audio/vedio conversation and send data between peers.
This protocal can be implemented by underline peer to peer messaging protocol such as mixnet, tor, carrier in Elastos and whisper in Ethereum.
It can be implemeneted using the function provided by substrate as well.

### WebRTC Sigaling Protocol

| type               | sdp      | candidates | reason   | options  |
|--------------------|----------|------------|----------|----------|
| offer              | required | -          | -        | required |
| answer             | required | -          | -        | -        |
| candidate          | -        | required   | -        | -        |
| removal-candidates | -        | required   | -        | -        |
| bye                | -        | -          | required | -        |

### Example
#### 1. Offer

```json
{
	"type":"offer",
	"sdp":"rtc_session_description_generated_by_webrtc",
	"options":["audio","video","data"]
}
```
### 2. Answer
```
{
	"type":"answer",
	"sdp":"rtc_session_description_generated_by_webrtc"
}
```
### 3. Candidate

```
{
	"type":"candidate",
	"candidates": [{
		"sdp": "candidate:684496083 1 udp 1685855999 112.65.48.165 17465 ...",
		"sdpMLineIndex": 0,
		"sdpMid": audio
	}]
}
```
### 4. Removal-Candidate

```
{
	"type":"remove-candidates",
	"candidates": 
	[
		{
			"sdp": "candidate:684496083 1 udp 1685855999 112.65.48.165 17465 ...",
			"sdpMLineIndex": 0,
			"sdpMid": audio
		}, 
		{
			"sdp": "rtc_candiate_desciption",
			"sdpMLineIndex": 0,
			"sdpMid": audio
		}, 
		...
	]
}
```
### 5. Bye

```
{
	"type":"bye"
	"reason": "reject"
}
```

### 6. Send Data by datachannel
```
{
	"fileId": UUID,  //created from the UUID, such as "E621E1F8-C36C-495A-93FC-0C247A3E6E5F"
	"index": Int, //当前发送文件的切片索引
	"mime": String, //Multipurpose Internet Mail Extensions，
	"data": String, //data Base-64 encoded string.
}
```

### An overview of the technology stack to be used
+ DID is used as the address of the instant messenger, it is generated on the user's device in stead of central server.
It can also be any address in a Ethereum wallet and it need the signature of the walller.
+ The Audio/Vedio and Data communicate is done by WebRTC, which is an open source project from Google.
With WebRTC, you can add real-time communication capabilities to your application that works on top of an open standard.
 It supports video, voice, and generic data to be sent between peers, allowing developers to build powerful voice- and video-communication solutions. 
 + The technology is available on all modern browsers as well as on native clients for all major platforms. The technologies behind WebRTC are implemented as an open web standard and available as regular JavaScript APIs in all major browsers. For native clients, like Android and iOS applications, a library is available that provides the same functionality. The WebRTC project is open-source and supported by Apple, Google, Microsoft and Mozilla, amongst others.
+ WebRTC does not work alone and it needs a signaling protocol to help the peer to find each other
and build the initial connection.
+ There is peer to peer messaging system in most blockchain system so we can use it
to be the signaling platform for WebRTC peers. 
### Core components, protocols, architecture etc. to be deployed
### 1. Messaging network
#### requirement of instant messaging 
1. broadcasting
2. offline messaging
3. online peer to peer messaging
4. realtime audio/vedio communication
5. file transmition 

While Ethereum Whisper support number 1 and 2 in the above list; 
Number 3 needs something like ElastOS Carrier or something similar, such as lower API like The RLPx Transport Protocol.
Peer to peer offline messaging and storage server can be implemented on top of Number 3.
Number 4 and 5 is handled by WebRTC while the WebRTC connection is setup by on line peer to peer messaging.

### 2. Turn server
The term stands for Traversal Using Relay NAT, and it is a protocol for relaying network traffic.
### 3. Push Notification Server
Since most apps are forced to be offline when it is switched to background, we need to use
the messaging channel of the Phone device. On IOS it is APNS and Voice Push Notification service,
on Android it is called FCM, Firebase Cloud Messaging 
### 4. Token
The Club token is a modular utility token that fuels the Club Chat network. 
This includes a Decentralized Push Notification and Advertise Market, Governance of the Club client, Incentives of Messaging, Turn Server and Notification Nodes.
the Club Token will leverage our economic attention to build the network effect of an open platform.

### 5. App
#### App for IOS and Android, a web client with a metamask plugin or dapp in wallet which supports WebRTC.
+ Those app is heavyly reply on WebRTC. The WebRTC standard covers, 
on a high level, two different technologies: media capture devices and peer-to-peer connectivity.
Media capture devices includes video cameras and microphones, but also screen capturing "devices".
 For cameras and microphones, we use navigator.mediaDevices.getUserMedia() to capture MediaStreams. 
 For screen recording, we use navigator.mediaDevices.getDisplayMedia() instead.
+ The peer-to-peer connectivity is handled by the RTCPeerConnection interface. 
This is the central point for establishing and controlling the connection between two peers in WebRTC.
+ The App replies on peer to peer messaging to communication;
+ The App is offline for most of time and it replies on the offline push messaging to get online when needed.


### Ecosystem Fit 
+ There are many project in the space of decentralized communication, such as status, topnetwork, yeecall.
While most projects are building the infrastructure from ground and replying on communities to provide different kinds of communication related application,
it still very hard to implement an instant messenger since most backend features required by an instant messenger are still missing.
+ We are going to build an easy integrated decentralized messaging app for end user and api for developer in cryto world by integrating many technologies in different blockchain.
we want to serve the whole blockchain world. 

## Team :busts_in_silhouette:

### Team members
* Name of team leader: Wei Li, Master Degree of Computer Science, Nanjing University
* Names of team members: Yi Wang, Master Degree of Computer Science, University of Chinese Academy of Sciences
* Names of team members: Xianghuan Li, BS of Computer Science, Shanghai University
* Names of team members: Tomas Shao, BS of Computer Science, Southwest Minzu University

### Team Website	
* http://t.callt.net
* https://www.callpass.cn/metamask

### Legal Structure 
```
Shanghai Allcom Network Technologies
Pudong Software Park
Suite 11-205, 498 Guoshoujing Road,
PuDong, 
Shanghai, PRC 201203
```
### Team's experience
+ Wei Li,over 20 years experiences in email,voip and instant messaging software development.
+ Wang Yi,5 years experiences in blockchain technoliges and 2 years in RUST development.
+ Xianghuan Li, 7 years experiences in fullstack software development, Java, Javascript, Rest, Android & IOS, Voip, SIP
+ Tomas Shao, 10 years experiences in IOS development, Swift, Objective-C, C/C++ 
+ Experience in WebRTC and Blockchain:
  + WebRTC Java/Android SDK: https://github.com/elastos/Elastos.NET.WebRTC.Android.SDK/releases/tag/release-v1.0.0 
  + WebRTC Swift/iOS SDK: https://github.com/elastos/Elastos.NET.WebRTC.iOS.SDK/releases/tag/release-v1.0.0 
  + WebRTC with metamask: https://www.callpass.cn/metamask
+ Experience in Rust
  + https://github.com/AngoraFuzzer/Angora 
 
### Team Code Repos
* https://github.com/allcomsh
* https://github.com/gxyzwangyi
* https://github.com/Tomas-Shao

### Team LinkedIn Profiles
* https://www.linkedin.com/in/wei-li-24329451/
* https://www.linkedin.com/in/patrick-wang-b1950678/

## Development Roadmap :nut_and_bolt: 

### Milestone 1 Realtime chat using Substrate address
* **Total Estimated Duration:** 1 month
* **Full-time equivalent (FTE):**  2
* **Total Costs:** $10,000
* Deliverables: IOS and Android APP which can demostrate the audio/vedio communication
* Specification:
* support vedio call using SS58 address format and extrinsic signature and verification
* still use elastos carrier as the messaging platform

### Milestone 2 A token and smart contract system immplemented in Substrate 
* **Estimated Duration:** 1 month
* **FTE:**  2
* **Costs:** $10,000
* Deliverables: White paper of the token destibution, token and smart contact
* Specification:
* issue of CLUB tokens
* smart contract for client communication
* smart contract for miner who run messaging, notification and turn server;

### Milestone 3 Messaging network 
* **Estimated Duration:** 2 month
* **FTE:**  2
* **Costs:** $20,000
* **Deliverables:** messaging node software, architecture, implementation and documentation detailed publicly on GitHub 
* **Specification:**
* fork of whisper 
* move devp2p over to libp2p, as it'll provide us with multiple transports, better protocol negotiation, NAT traversal,
* smart contract for miner who run messaging nodes;
* a c++ mixnet messaging and port to WASM

### Milestone 4 Add turn server into substrate network
* **Estimated Duration:** 1 month
* **FTE:**  2
* **Costs:** $10,000
* **Deliverables:** downloadanle turn sever, install instruction, source code
* **Specification:**
* Add token incentive of a open source turn server 

### Milestone 5 Implement push notification server into substrate network
* **Estimated Duration:** 1 month
* **FTE:**  2
* **Costs:** $10,000
* **Deliverables:** downloadanle push notification sever, install instruction, source code
* **Specification:**
* push notification server node to accept and store notification, device token from application
* SDK for mobile application to integrate push notification;
* push notifocation gateway to deliver push notification to IOS or Android messaging center

### Milestone 6 Implement WebRTC singaling messaging 
* **Estimated Duration:** 1 month
* **FTE:**  8
* **Costs:** $40,000
* **Deliverables:** protocol of peer to peer communication,implemented the rust and substrate
* **Specification:**
* Distributed Peer Table (DPT) / Node Discovery: peer could be any substrate address, Maintain/manage a list of peers, also includes node discovery. 
* Offline messaging

### Community engagement

## Future Plans
Please include the team's long-term plans and intentions.

In the next two years, We are going to implement the decentralized messaging protocol and build the messaging network and an instant messaging app on top of it(a dicentralized Zoom kind of app) for cryto world and we will continue to improve the user experience.

It will also be a real time communication SDK (a dicentralized communication development toolkit like Twillio, Agora, Jigou, a communication version of Chainlink) for app application development, especially wallet application.

## Additional Information :heavy_plus_sign: 
* What work has been done so far?
  + We have developed an IOS and Android app with Audio and Vedio chat. Those apps relies on Elastos's carrier as backend protocol for peer to peer signaling messaging.
  + We have integrate WebRTC Audio/Vedio communication with metamask waller. 
https://www.callpass.cn/metamask
  + We have implemetd peer to peer and group text messaging chat using Ethereum's whisper and swarm.
http://t.callt.net
It relys on a private side chain to do messaging routing and offline messaging.
* Are there are any teams who have already contributed (financially) to the project?
  + No
* Have you applied for other grants so far?
  + No