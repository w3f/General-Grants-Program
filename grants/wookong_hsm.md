# Wookong open source HSM for validators

## Project Description
Wookong open source HSM is designed to provide a HSM solution for validators and community which has exciting features about network form,  inline risk control and code could be reviewed and modified by developers if needed.

There are two troubles of traditional HSM:
* It is difficult to work with the cloud servers due to the cloud server provide is not allowed to place the device beside their servers or plug  something into their servers.
* They are just sign machines. Hacked need not to steal the keys inside but just call them to sign by illegal access. 

So Wookong open source HSM will try to fix there issues. The system will contain three modules. A network protocol to connect the HSM in local with cloud server tightly, a risck control system to defense the illegal call and a key management module using secure element.

Here is the plan:
* 1.Using one hardware system(RPi and soft router), called NAT-front, for network connection. Stay connected to your cloud server with heartbeat socket or something like Ngrok.
* 2.Using second hardware, called Core-back, to store the keys, make a signature and risk control. 
* 3.Make the connection between NAT-front and Core-back by using serial interface (SPI/UART). This will be simplest way but pretty useful to isolate attacks from the network. A protocol with communication encryption is needed.
* 4.The Core-back will store the keys in secure element.
* 5.Implement risk control in Core-back with part of Polkadot’s code and a strategy engine.
* 6.Implement secret management in Core-back for backup the seed or private keys.

For validators or any users, the benefits will be:
1. Get the devices in more reasonable price.
2. Easy to work with their nodes on cloud server.
3. Have the similar secure level although there is no certificate from FIPS or NIST. No back door neither since no one force you to do that and the code could be reviewed.
4. Risk control inside to protect themselves using their own wisdom if the config and modify the strategy.


## Team member
* Chester Lee
* Yanxiang Hua

## Team Website	
* https://wooko.ng

## Legal Structure 
China, LLC

Name: sBeijing Extropies technoloy Co.LTD

Address: s3008-103 Floor3, Building B, Tower 1, No.2 Yongcheng North Rd, Haiding district, Beijing, PR.China

## Team's experience
Our team has 3 years experiences in design crypto currency hardware wallet and  Hardware Security Module. The core members of team have background in financial security, blockchain technology and integrated circuit industry for more then 8 years. Our products are widely used in market both for individual private key protection and enterprise digital asset management.
Chester has hardware design experience and could do RUST development.
Yanxiang is C programmer for more then 10 year and fimiliar with crypto and communications.

## Team Code Repos
* https://github.com/extropiescom/bladeX
* https://github.com/extropiescom/wookong-solo-tutorial-node
* https://github.com/extropiescom/wookong-solo-rust
* https://github.com/chesterliliang/schnorrkel-c

## Team LinkedIn Profiles
* https://www.linkedin.com/in/良-李-231a34b0
* https://www.linkedin.com/in/燕翔-华-879791187

## Intended language of development
```
C and RUST
```
## Development Roadmap

We will require about 4 months to complete this project. We intend to hav 3 developers full-time and 1 part-time, at a total cost of $80,000.

### Tasks
* T1.Decide the hardware platform. RPi3 and Soft router are considering as first two choices.
* T2.Install and run the polkadot on the aimed platform to prove it has enough computing power and right environment to run plokadot's code.
* T3.Develop the network module which is to make the HSM work with cloud server.
* T4.Develop the risk control module using part of node's code to analyse the attack before making the signature.
* T5.Develop the keystore module which could manage the private key for operations like backup or re-setup.
* T6.Develop the communication protocol between the network part and keystore part.

### Time schedule
T1 and T2 could be done with two weeks.
The average module developing time in T3-6 is about 4 weeks include the testing.
3 Weeks will be reserved for system debuging and bug fixed. And few more time should be spend on hardware issues such as the power supply, wire connection and cooler setup.  So the plan is:
* Week 1-2: T1 T2
* Week 3-6: (T3 T4) || (T5 T6) || (Hardware)
* Week 7-9: Debug and bug fix.

### Milestones
* T1 and T2 is the 'evaluation step'. Some hardware will be bought. Hareware  and software engineer take two weeks do the basic research. Step cost: 16K USD.
* Development tasks will last two months, 3 engineer full time at least. Step cost: 48K USD.
* Debug, fix and demo. About 1 month, two engineer full time. Step cost: 16K USD.

Team prefer DOTs of course and we think this kind of HSM is the right form for blockchain application, comparing traditional ones which's code is not open and the not easy to customization.


## Additional Information
We did some evalution works of to install polkadot on RPi3. It works but there is performance and concern since the hardware is not for the heavy work. No other team financed the project yet and this is the first time we try to find grant.

We found yubiHSM companies including securosys try to provide traditional server form HSM for validators and call it BC HSM. They are all good products to enhance the security level but there are still some issues such as will the Amazon or Google allow the YubiHSM connected to there cloud server? Or how to discover and defend the illegal sign request, which obey the entire calling rules but still do something bad? Further more, hardware provided by special vendor with customized firmware may slow down the progress of blockchain projects because projects always run fast and vendors products hard to follow.

Wookong open source HSM is designed to answer all these questions. It could work with cloud server. Risk control systems could defense most of illegal calls using inline strategy. And the developer could modify the codes if they have requirements.
