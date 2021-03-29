# Front-End for Staking Rewards Collector

* **Status:** Open 
* **Proposer:** JonasW3F
* **Your Project(s):** -
* **Projects you think this work could be useful for** Staking operations of all nominators and validators.
* **Teams/People that could deliver the RFP** -

## Project Description :page_facing_up: 

The [staking-rewards-collector](https://github.com/w3f/staking-rewards-collector) is a tool to gather staking rewards for given addresses and cross-reference those with daily price data. This is a very useful tool for every validator and nominator in the ecosystem. However, since it has currently a CLI and requires some technical knowledge to set up (git, nodejs, yarn). A front-end hosted on a website could help many users getting access to this tool and enjoy the benefits. 

The backend is already written in javascript, this should make it quite easy to host as a website and develope a front-end. 

## Deliverables :nut_and_bolt:

- **Implementation of a user interface**:
  - **Query input parameters (from the users)**:
    - Addresses (multiple ones are supported by the code).
    - Start and end date 
    - Does the user want price data linked to staking rewards?
    - What are the startBalances of each address?

  - **Data output viewer**:
    - The code produces a .csv and .json file which should be displayed in the browser.
    - Visualization for the varying number of input addresses.
    - Some sorting based on network / amount.
    - Search for specific entries like dates.
    - Option to download to local storage.
  - **Help page / buttons:**
    - Both the input query and output viewer should have several help buttons to give explanations for all users. 

- **Compatibility**:
  - It should be easy to extend the underlying script and the UI should be flexible enough to incorporate that (e.g., adding another column in the data output).
- **Hosting**
    - Centralized and preferably decentralized (IPFS).
- **Testing**
    - Test if the code behaves as expected.

* **Total Estimated Duration:** 3 Weeks
* **Full-time equivalent (FTE):**  15 days
* **Total Costs:** 3600 USD

### Milestone 1 (Planning)

* **Estimated Duration:** 3 days
* **FTE:**  3
* **Costs:** 720 USD


| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Mockups | Mocking the UI and the user flow. |  
| 2.  | Adjustments | Reach out for feedback to the Grants Team. Based on feedback, make adjustments. | 

### Milestone 2 (Implementation)

* **Estimated Duration:** 9 days
* **FTE:**  9
* **Costs:** 2160 USD


| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | UI for user input | Develop an UI to request necessary data from the users. |  
| 2.  | UI for data visualizer  | Develop an environment to display the output (.csv and .json) for the end user in a pleasurable way. | 
| 3.  | Help pages / comments  | Implement help texts and descriptions for users. | 
| 4.  | Internal testing  | Unit tests covering the functionality and logic | 


### Milestone 3 (Testing)

* **Estimated Duration:** 3
* **FTE:**  3 days
* **Costs:** 720 USD


| Number | Deliverable | Specification | 
| ------------- | ------------- | ------------- |
| 1. | Deployment | Deploy the code on a centralized server and IPFS. |  
| 2. | Test live environment | Test the homepage with various different OS and browsers and provide a report | 
| 3. | Polishing | Reach out for feedback to the Grants Team. Integrate final feedback on functional, as well as cosmetic changes like font size, colors, typos etc. | 


