# Bunziverse
## Project Description
* We are building a parachain on polkadot called Bunziverse. We will migrate the existing Bunz infrastructure including wallets, transactions, keys, value distribution contracts and our stablecoin (BTZ) onto Bunziverse.
    
* Bunziverse will support the over 350,000 existing users with +100,000 wallets holding BTZ today effectively bring over 5M transactions annually on-chain.
    
* There is a need to develop a DAO to govern the entire ecosystem and social communities.

* One interesting feature of Bunz is our **"60% Promise"** - Bunz takes 60% of all revenue generated and gives it directly to users as BTZ. 
 
**The Core Components of Bunziverse Project are:**


1. Copy all past transactions from the existing centralized Bunz application to the Bunziverse chain (this will result in user balances on chain that are exactly equal to those in the app today)
2. Development of custom block explorer to render older transactions with appropriate (original) timestamps (as well as other Bunz app specific enhancements)
3. Development of private key generation, storage, and management functions within the Bunz client apps (including app key backup and possible recovery mechanisms)
4. Enhancements to the client application wallets to sign and submit all transactions (P2P and merchant) to the Bunziverse chain.
5. Enhancements to the Bunz backend API to route all transactions via the Bunziverse chain (we will initially run both the existing centralized system and the Bunziverse chain in parallel - then cut over to rely solely on the Bunziverse chain)
6. Merchant Business Payouts/Settlements will be transitioned from the centralized application to the Bunziverse.
	    

	**Here is a high-level overview of the Bunziverse project**
    
	<div align="center">    
    <img src="https://i.imgur.com/CWGOyVn.png" width="600px">
	</div>
	
	You can find more details around Bunz here:
	https://blog.bunz.com/
	
	## Team Members
	* Sascha Darius Mojtahedi - Product Contributor
	* Paul Chan - Product Contributor
	* Eythan D'Amico - Design Lead
	* Perry Haldenby - Technical Lead 
	* Julian Haldenby - Development
	    * https://github.com/canuc
	* Ed Robinson - Development
	    * https://github.com/earobinson
	* Edie Law  - Development / Data
	    * https://github.com/ArcQ
    * Cameron Eldridge - Development
        * https://github.com/OinkIguana
	
Our team is available and eager to discuss our ability to complete the work. Should you wish to have a deeper conversation around our abilities to develop in RUST or other languages please don't hesitate to get in touch.
	
## Team Website
https://bunz.com 
	
## Legal Structure
Incorporated in Canada
	
## Team's experience
* Bunz is a company with the worlds most widely transacted on stablecoin - BTZ. BTZ are currently being used P2P on the Bunz app and at over 250 partner shops that accept it. In collaboration with ChainSafe Systems, we built a bridge to Ethereum Mainnet from the Bunz app enabling users to transfer in-app BTZ to their Ethereum wallets (ERC223 token). 

* Our CTO (Perry) and COO (Paul) have collectively lead a significant amount of development for TD Bank Financial Group (payments innovation team) before founding Bunz. Both  have started companies in the past, Perry went through Y Combinator in 2016 for one of these (Amulyte). Perry and Paul both hold numerous blockchain and fintech patents. 

* Eythan (CPO) is the reason the Bunz app is so beautiful. He is a UX/UI expert and is exceptionally in tune with the intricacies of leveraging blockchain while keeping things simple and clean for the user. 

* Julian and Ed make up our backend firepwer. They are incredible coders, scaling geniuses and have worked together and separately at many startups in the past (including Kik, Joist, Finaeo, Hubba). They have poured significant thought and code into optimizing the integration of consumer apps with public/permissioned blockchians. They are both Node JS wizards with a new and intense passion for Elixir. Julian co-founded Amulyte with Perry and is also a graduate of Y Combinator.

* Eddie is our master of machine learning. He is constantly analyzing Bunz data and building intelligent features into the system. He is also a rockstar frontend developer currently leading our Web team.

* Cameron is one of the most gifted young developers we've had the privilege of working with. He single-handedly developed the Bunz merchant app and has contributed to almost all of the Bunz codebases (Android, iOS, backend). He is a language master and **Rust** has been his language of choice for the past couple years.


	
	## Team LinkedIn Profiles
	Sascha Darius Mojtahedi
    https://www.linkedin.com/in/sascha-darius-mojtahedi/?originalSubdomain=ca
      
    Paul Chan
    https://www.linkedin.com/in/cerebrous/
      
    Eythan D'Amico
    https://www.linkedin.com/in/eythan/
    
    Perry Haldenby 
    https://www.linkedin.com/in/perryhaldenby/?originalSubdomain=ca
    
    Jullian Haldenby 
    https://www.linkedin.com/in/haldenby/?originalSubdomain=ca
    
    Ed Robinson 
    https://www.linkedin.com/in/earobinson42/
    
    Eddie Law
    https://www.linkedin.com/in/eddie-law/
    
    Cameron Eldridge    
    https://www.linkedin.com/in/cameron-e-5b13b0a6/
    
	## Development Roadmap
	The milestones are spread out over a total of 3 months as follows:
    * M1: Development of Coin Smart Contract (port existing ethereum token contract) (2 weeks)
	* M2: Integration of existing BTZ (centralized) backend wallet infrastructure with Bunziverse chain (2 weeks)
	* M3: Development of private key generation and management instructions+process (frontend) (2 weeks)
	* M4: Development of BTZ distribution/reward functions (2 weeks)
	* M5: Testing in staging environment, running parallel environments, full transition to decentralized (4 weeks)

Please note that the development cost is approximately $600,000 (this includes the cost of several additional resources not listed above - team members required to integrate all required changes across iOS, Android, Web, and more)
	
### Additional Development Considerations    
* We will be researching zero knowledge identity verification for transactions that require age verification on purchase of goods.
* Bunz includes significant value distribution functionality (BTZ bonuses which are issued constantly for contributions to the platform). When we launch on Bunziverse all bonuses will be paid from Bunz Official wallets (on-chain transactions signed and submitted from our backend), but we are investigating converting these functions to smart contracts that pay users automatically. This will involve tracking more application data on chain.
 
We have not included these considerations in the above milestones as they will significantly increase timelines and we have not finalized the specifications.
	
## Additional Information
### What work has been done so far?
* The Bunz application has been live on iOS, Android, and Web since 2016 and has over 350,000 users
* Tens of thousands of BTZ transactions take place on Bunz everyday
* The architecture was designed to support a transition from the current centralized system to a blockchain solution from day 1
* We have completed significant work in partnership with ChainSafe to build a parity bridge for facilitating trustless transfers of BTZ from a private Ethereum chain to Ethereum mainnet.

### Have you applied for other grants so far?
No
	
### Are there any other projects similar to yours?
* In terms of the data economy - BAT/Brave  
* In terms of stable coins - DAI/Facebook's Global Coin
