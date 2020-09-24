# Easy Deal

## Project Overview
Easy Deal is a decentralized "Deal Guarantee Service" platform, it's built with Substrate.

I think, blockchain wants to be known to the public, it must be useful - everyone can use it.

I'm trying to make a world-wide platform, everyone can make deal on it easily. In this "real decentralized" world, it's up to all users to decide what is good or not.

## Project Details

#### Easy Deal aims to solve these problems:

* **Deal Guarantee:** There will be trust issues in the various trade scenarios for whoever comes first. Alibaba solved the problem in the e-commerce field with Alipay, but there is no universal solutionoutside the e-commerce field;

* **Cross-border Trade Settlement:** Buyers and sellers in different countries make a deal, and when paying, they need to use foreign exchange in exchange for settlement currency;

* **Information Classification:** A Chinese needs the help of Koreans (such as registering a Korean exchange and needs to receive text messages on behalf of him). At this time, a Korean can provide this service, but there is no special platform to make a match for this service.

#### The core concepts are as below:

* Everyone can post information on the platform (Maybe he needs to lock some funds first). 

* If the information is not good for the platform, other users can submit a proposal to delete it.

* When someone interested in the information, he will make a deal, and his funds equal to the price will be locked.

* Until the seller delivers it, and the buyer confirms that, the funds will transfer to seller's account.

* When there is a dispute between the two sides of the deal, they can submit a proposal for vote. 

### Storage

We use [Arweave](https://arweave.org) for file storage currently. 

There's an [endpoint](https://substrate.easydeal.io/arweave) to upload file to Arweave. The role of endpoint is to use AR to pay for the storage cost, and to improve the user experience of decentralized storage on blockchain. 

When the info is successfully posted, the endpoint will generate a cache of image(If there are pictures of the info). Then, when users view the image, it gets the data from cache. If there is no cache data, endpoint will retrieved data from Arweave network. In this way, users can switch endpoints at any time without losing data, and their experience will be better.

Anybody can submit a proposal to be an endpoint, and set a price of it. If people use the service, they will pay some ESD for it. Finally, users will choose the endpoint with the cheapest price and the most stable service.

**The storage part may migrate to some Polkadot parachains, like [Crust](https://github.com/crustio/crust). Maybe we will implement decentralized storage on the platform itself, users will pay ESD for storage service.**

### Information Search

If someone wants more users to find his information, he will provide as many keywords as possible for it, and pay for the keywords (The cost will be determined by the number of informations under the keyword). Then other users can find this information by the hash of search keyword.

### Payment

In the current version, Easy Deal use its own currency (ESD) for deal. It will interact with Polkadot's parachains in the next release, use statble coins for deal.

### Advertising

There are many advertising spaces on the platform, anyone can bidding for use it. 

## Team members
* Long Chen - Front-End Engineer/Product Manager

## Team Website	
* https://substrate.easydeal.io

## Legal Structure 
Individual developer

## Team's experience
I have built a [Tron-network dApp](http://tron.easydeal.io) in 2019 summer, and an Ethereum Wallet in 2019 winter.

I've studied substrate and Rust lang in recent months.

## Team Code Repos
* https://github.com/easydeal-io

## Team LinkedIn Profiles
* https://www.linkedin.com/in/czl1378

## Development Roadmap

### Milestone 1 — 1 month — $10,000
* Find more people to join in our team.
* Complete the deal logic.
* Done the comment feature.
* Complete deal management and other management features.

### Milestone 2 — 1 month — $10,000
* Integrate block explorer features.
* Implement info search feature.
* Support advertising bidding.

### Milestone 3 — 2 month — $10,000
* Migrate data storage to parachains.
* Documents and websites.
* Mobile/App version, maybe.
* More unit-test.
* Public testnet.

To be continue...

## Additional Information

* **What work has been done so far?**

  I've built a [MVP version](https://substrate.easydeal.io)

* **Have you applied for other grants so far?**

  No.

* **Are there any teams who have already contributed (financially) to the project? Are there any other projects similar to yours?**

  Not to our knowledge.
