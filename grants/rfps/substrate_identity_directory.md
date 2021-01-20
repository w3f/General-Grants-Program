# General Grant Proposal

* **Project:** Substrate Identity Directory

## Project Overview
This proposal is in response to a RFP identity directory. Identity Directory is a proposal of a fully client-side web application that would read and display registered identities on Substrate-based chains which implement the Identity pallet. By browsing a specific link, a user would be able to see beautifully rendered identity data of an on-chain identity along with all the metadata in the identity entry, an avatar if provided, and any verifications from the registrars on-chain. Users would be able to match and verify identities and also have access to sending tokens directly to another user.

### Overview

GOALS
  * Create a web service to query on-chain identities. The service accepts and reads input parameter as address, index, or XXX and:
  * If the input parameter is address or index create a single page view for a specific identity
  * If the input parameter is neither address nor index create a list page view 

A web service would have a way of reading the following links:
https://polkadot.polkaperson.com/<identity>
https://kusama.polkaperson.com/<identity>
Web service would read the <identity> parameter and make a query to the corresponding chain and retrieve identity data of the requested identity. 
Web UI would have two ways of viewing data. A list view and a single page view. A list view would be a way for users to query the chain and display all registered identities on the Kusama and Polkadot chains. This view would be the default view if no specific identity is queried and provided in the URL. By clicking on the specific identity in the list, a user would be redirected to a single page view for the chosen identity. A single page view would be a way for users to query a specific identity data of the on-chain identity. This view would be a way for users to see identity activities indicative of a member’s reputation containing identity card of an on-chain identity along with all the metadata in the identity entry, an avatar if provided, any verifications from registrars in the chain, and buttons that allow you to send tokens directly to the user. Single-page view UI will contain multiple closable and re-orderable columns so users can order them as they choose. The order will be remembered across the app with the option to toggle and freeze a layout for a specific user. It would support a plug-in ecosystem for different sub-views of identities. On-line version would come with some default plug-ins deactivated and an off-line version would support simple installation of other plug-ins. Default plug-ins would be basic info, governance, treasury and validator, and optional plug-in would be transaction history, identity history, remark history and society plug-ins.

## Team 

### Team members
-	Darko Macesic (https://www.linkedin.com/in/darko-macesic/)
-	Karlo Majer (https://www.linkedin.com/in/karlomajer/)
-	Ana Milic Strkalj (https://www.linkedin.com/in/ana-milic-strkalj/) 


### Team Website	
* https://shardlabs.io

### Legal Structure 
Shard Labs d.o.o., Kroz Smrdečac 19, 21000 Split, Croatia

### Team's experience
-	Ink! Remix Plugin (https://github.com/Shard-Labs/ink-remix-plugin)
-	ZoKrates (https://github.com/Zokrates/ZoKrates)
-	ZoKrates Remix Plugin (https://github.com/Shard-Labs/zokrates-remix-plugin)
-	Sourcify (https://github.com/ethereum/sourcify)
-	Kusama Tips Widget (https://github.com/Shard-Labs/kusama-tips-widget)

### Team Code Repos
* https://github.com/dark64
* https://github.com/karlomajer
* https://github.com/anamst

## Development Roadmap 


### Overview
* **Total Estimated Duration:** 19 weeks + 6 months
* **Full-time equivalent (FTE):**  3 + 0.15


### Milestone 1 Designing and design implementation for list page / individual identity page. Support for the offline mode. 
* **Estimated Duration:** 9 weeks
* **FTE:**  3

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- | 
| 1. | Design a list page | Create design mockups in Figma. |  
| 2. | Design an individual identity page | Create design mockups in Figma. |  
| 3. | Implement list page | Build UI components in VueJS used in the identity list page. |  
| 4. | Implement individual identity page | Build UI components in VueJS used in the individual identity page. |  
| 5. | Implement query logic for identity data | Implement query logic which will be used to retrieve identity data. |
| 6. | Query identity activities | Implement query logic which will be used to retrieve activities indicative of a member’s reputation. |  
| 7. | Implement logic for sending tokens | Implement logic for sending tokens; retrieve balance, parse inputs, display transaction fee, create the transfer transaction |
| 8. | Make the web service work offline | Web service can be used in offline mode; the user can specify a local node to which will the service connect. |

After milestone 1 users can utilize the basic application which supports querying by address, index or identity fields. Application has a list page and a single page view with a basic info column fully functional. Users will be able to set their own node endpoint.

### Milestone 2 Implementing default plug-ins (governance and treasury)
* **Estimated Duration:** 5 weeks
* **FTE:**  3

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- | 
| 1. | Governance plug-in | Implementing a column listing all of the account’s governance activities (votes, proposals, etc.) in vertical timeline with related events referencing each other.  |  
| 2. | Treasury plug-in | Implementing a column listing a history of the account’s interactions with treasury (tip proposals, endorsements, treasury proposals, grant wins, votes on tip proposal motions if the account was council member at the time.) Both governance and treasury would clearly indicate if the user was a council member and didn’t uphold their duties. |  
| 3. | Validator plug-in | Implementing a column listing the history/summary of the account’s participation in securing the network. |  

After milestone 2 user will be able to utilize default plug-ins for governance and treasury. Events in each of the columns will be linkable and layouts of the columns can be saved.



### Milestone 3 Optional plug-ins
* **Estimated Duration:** 5 weeks
* **FTE:**  3

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- | 
| 1. | TX history | Implementing a column listing all of the account financial transactions. |  
| 2. | Identity history | Implementing a column listing all of the account’s interactions with identities. |  
| 3. | Remark history | Implementing a column listing all of the account’s past issued remarks. |  
| 4. | Society | Implementing a column listing account’s participation in Society (how much they bid, when they were accepted, how many times they voted etc.). |

After milestone 3 optional plugins will be developed and implemented into the app. The app will support easy installation of plug-ins and have a yarn build step that builds the site for offline or IPFS use.



### Milestone 4 Documentation and project visibility. Maintenance.
* **Estimated Duration:** 6 months
* **FTE:**  0.15

| Number | Deliverable | Specification |
| ------------- | ------------- | ------------- | 
| 1. | Documentation | Delivering comprehensive documentation on developing plug-ins and hosting your own Identity Directory with and without IPDS and other supporting options. |  
| 2. | Article on Medium | After finishing with development and testing we will publish an article on Medium describing our work done for the project to make sure the project gets the initial visibility. |  
| 3. | Maintenance | This includes smaller fixes and updates in the project. Does not include feature requests. |  

After the milestone 4 team will maintain the project for additional 6 months and provide comprehensive documentation on developing plugins.

