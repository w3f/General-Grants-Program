## Bidirectional QR code with Universal Offline Signer (UOS) standard

### Project Description
The goal of NGRAVE is to create a fully integrated, end-to-end security solution for all aspects relating to security on the blockchain. From the wallet generation, to wallet management, secure key storage to posthumous recovery and more, NGRAVE's goal is to offer the highest level of security. 

Central to this endeavour is our flagship product, the NGRAVE ZERO. It is a versatile hardware wallet with custom key creation procedure, fingerprint authentication and touchscreen display. It has been given incubator support and is being built by Belgium's high-tech behemoth IMEC. 

Part of our solution to improve security is removing the need for any connection to a networked device, and instead relying only on QR codes to sign transactions. We want to leverage this exciting feature, and help push for a widely-supported industry standard. For this purpose, we found the Parity Signer to be very inspirational. 

After reaching out to Parity Technologies, they came back to us with a proposal for a universal standard: The Universal Offline Signer (UOS). These are its main features:
* Highly efficient data transmission (low overhead on native binary encoding).
* Extensible for any coin, including substrate.
* Multi-part payloads allowing for high data capacity.

A proposed standard can not thrive on technical merits alone. It needs uptake and integration in existing solutions. To that end we also got in touch with metamask, an important Ethereum wallet currently integrated within most dapps (and with an estimated [ 320k visits per week](https://medium.com/metamask/metamask-metrics-fbec0e2ceaa7))

They have been experimenting with adding external account support that would allow the use of QR code signatures. 

Our intention is twofold. 
1. We want this community effort to proceed and be of high quality.
2. We want to integrate this solution into our hardware wallet. 

As it stands, besides the parity signer, we have no knowledge of other hardware wallets that implement a widely used or even open source QR code standard. 

All code we would develop for this project would be open source and reusable for other projects, as our main goal is to increase adoption signing by QR code.

 ## Team Members
* Ruben Merre
* Edouard Vanham
* Xavier Hendrickx

 ## Team Website	
* https://www.ngrave.io

 ## Legal Structure
Incorporated in Belgium as NGRAVE.IO NV
Kloosterstraat 94, 2000 Antwerpen, Belgium. 
Company number: 0700.252.896

 ## Team's Experience
The team is highly complementary, jointly having a worldwide network in crypto, and over 20,000 hours of project management experience in launching new tech projects from ideation to post-go live. 

Our CEO Ruben Merre has a vast background in strategy-, management-, and innovation consulting. Prior to NGRAVE, he led a multi-million-dollar program to build a new group-wide automated investment business unit for a top international financial institution; this consisted of 20 subprojects including all business and ICT tracks. He is well-versed in growth strategies, go to market, marketing & sales, and business development. 

Our COO Edouard Vanham bridges the technical and business aspects, leveraging on his expertise as a former IT and Management consultant, where he led several digitization projects in the banking and insurance industry. 

Our CTO Xavier Hendrickx has been in the crypto space for a long time and was CTO of the Belgo-American top blockchain project SwarmCity, which he ultimately left for a full-time position at NGRAVE. 

NGRAVE advisors include experienced business veterans, including sales & general managers, sales leaders, serial entrepreneurs, company founders, and financial leaders.

Our manufacturing partner in both hardware and firmware is technology giant IMEC. IMEC is the world leader in R&D for nanotechnology and digital technologies (such as battery-, sensor-, IoT-technology) and is a leading micro/nano chip manufacturer. NGRAVE has also been enrolled in their #1 university-linked accelerator in Europe (#4 in the world) since July 2018. 

 ## Team LinkedIn Profiles
* https://www.linkedin.com/in/xavierhendrickx/
* https://www.linkedin.com/in/edouardvanham/
* https://www.linkedin.com/in/ruben-merre/

 ## Intended language of development
* C++ for firmware development
* Javascript for Metamask integration 

 ## Development Roadmap
We will require 3 months to complete this project. We intend to have 1 developer full-time and 2 weeks of outsourcing to Metamask and Parity (spread out over 6 weeks) for a total cost of $ 29,500

#### milestones:
1. Implement External accounts to Metamask 
    * weeks 0 - 3;  8000 USD
2. Finalize UOS and implement on top of Metamask 
    * weeks 3 - 6; 5000 USD
3. Implement UOS for the NGRAVE ZERO firmware  in C++
    * weeks 6 - 10; 8000 USD
4. Integrate all parts together and works as intended
    * weeks 10 - 12; 6000 USD
5. Coordination of efforts, project management
    * continuous; 2500 USD

We can receive payment however it best fits the foundation, but ideally part payment at the end of each milestone. $29,500 / 4.

Once the milestones have been delivered, it is in our interest to continue to provide support far into the future. Our long term plan is to create developer tools that easily integrates QR code signing via the above developed standard.


 ## Additional Information
UOS: https://github.com/maciejhirsz/uos 
Metamask PR: https://github.com/MetaMask/metamask-extension/pull/6267 
 
We are open to discussing the specifics of implimenting substrate support as our next grant application and are hoping to solidify a working relationship with this initial UOS implimentation.
