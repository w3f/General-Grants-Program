# Hardware wallet for Polkadot with sr25519

## Project Description 

We are building next generate hardware wallet called Wookong Dot. It is aimed for Polkadot and para chains based on Substrate such as ChainX. There will be some basic tokens like BTC, ETH and USDT in the wallet as well.

### SR25519

The break through in technology is we have already porting schnorr 25519 to the chip, the secure element we use, by compiling the schnorrkel, RUST version written by Jeff in W3F into a static library with RUST embedded to chain and then linked with other embedded C code. The signature made by the chip could be verified by standard lib. https://github.com/extropiescom/schnorr-cortex

Meanwhile, we are try to reduce the code size using suggestion from Jeff and other developer in community. The binary of schnorr in embedded is under 100KB. We are keeping to verify every version of schnorrkel on embedded environment from 0.6.0. 

### Accomplished

The schematic and PCB(Printed Circuit Board) layout has been accomplished, as well as the basic firmware such as the USB-HID U2F protocol, which means the device could be accessed by Chrome browser directly for web application with JS-api.

The ID(ndustrial Design, design the appearance of product) and MD(Mechanic Design, design the inside structure of product) is ordered the most famous design company LKK-design(http://www.lkkdesign.com/en-index). Functional mock up is ready.

![Image text](https://raw.githubusercontent.com/extropiescom/ma/master/pic/blue.jpeg)

### System Architecture

Wookong Dot uses a secure element as the core of system. With ARM’s anti-tamper technology, code and data could not be modified illegally or steal from it. Side channel attack won’t work at all. Comparing with Ledger, the secure element in Bule, has faster speed and rich IO, controlling everything include the USB interface, the OLED screen and the button. This architect is more secure than using common MCU as the assist chip.

![Image text](https://raw.githubusercontent.com/extropiescom/ma/master/pic/sys.jpeg)

#### The spec of secure element is

ARM SC300, cortex M3 level
192MHz RAM:384KB  FLASH:512KB
IO:USB/SPI/UART/GPIO/ADC, secure boot,OTP and MPU

#### General features
OLED: 128x84px, 4 Buttons, USB-TypeC

### Our Target

We think to make Wookong Dot a secure and early hardware wallet for Polkadot is a great idea. Both the timing and the design are perfect for the community. The USB interface could be connected to CLI and JS client if Electron is used or through U2F protocol in Chrome browser.
With the grant of W3F, the tooling for mass production could be made immediately. Fist batch devices will be ready in three months and 1000 devices could be donate to community freely for the promotion.
Team member

The following people are core members relevant for this proposal

* Chester Lee [CTO, firmware/software developer,Project leader].

Former technical working member of FIDO Alliance. Crypto consultant of EgisTec. 10 years experience of secure hardware product design of development. Architect of Wookong hardware wallet.

* Yanxiang Hua [Senior firmware engineer]

Former technical head of BHZ.com, CTO of pixelauth.com. has over 15 years’ experience as a programmer and firmware engineer.

* Wei Peng [Software engineer]

Full stack developer. Expert of node.js and electron. Also has experience to build application on Android and iOS.

* Minchao Xi [Software engineer]

Developer of device’s mid-ware for every platform. Good at security framework such as pkcs11,csp, openssl and libsodium.  Algorithm coder.

* Keifei Wei [Hardware engineer]

Expect of design schematic and pcb layout, as well as chip packaging and SIP solutions. Python developer, has ability to build all test tools.

## Team Website

https://wooko.ng

Wookong hardware wallet has two released products. Solo/Enterprise are USB based product for individuals and companies. Bio is a credit size product for mobile applications.
![Image text](https://raw.githubusercontent.com/extropiescom/ma/master/pic/product.jpeg)

## Legal Structure

China, LLC

Name: Beijing Extropies technology Co.LTD

Address: 3008-103 Floor3, Building B, Tower 1, No.2 Yongcheng North Rd, Haidan district, Beijing, PR.China

## Team's experience

Our team has 3 years experiences in design crypto currency hardware wallet and Hardware Security Module. The core members of team have background in financial security, blockchain technology and integrated circuit industry for more then 10 years. Our products are widely used in market both for individual private key protection and enterprise digital asset management.

## Team Code Repos

https://github.com/extropiescom/wookong-solo-tutorial-node
https://github.com/extropiescom/wookong-solo-rust
https://github.com/extropiescom/schnorr-cortex
https://github.com/extropiescom/bladeX

## Team LinkedIn Profiles

https://www.linkedin.com/in/li-chester-231a34b0
https://www.linkedin.com/in/yanxiang-hua-879791187
https://www.linkedin.com/in/wei-peng-122a0b82
https://www.linkedin.com/in/xi-ximinchao-10615039/
https://www.linkedin.com/in/可斐-韦-137a7318b

## Development Roadmap

### 1.Firmware development

Based on the basic firmware, a HDKD wallet firmware will be developed step by step following BIP39 and BIP44

* Entropy generate using hardware random source which is physical noise
* Entropy to Mnemonic
* Mnemonic recovery and back up using only screen and buttons on device
* Mnemonic to seed
* Seed to root private key
* Derive for each coins

There will be a secure boot-loader for the firmware update. It will verify the hash and signature of the main firmware of course.  
Build test tools by sending USB commands in test scripts to test the firm on EVB abd we wll have strictly code security review.

### 2.Mass production tooling

To open the mould is very expensive and need to deal with carefully.Several pilot rounds are necessary. Test tooling is also needed.

### 3.Software develop

1. Mid-ware to organize usb commands in C based on libusb.

2. RUST wrapper and JS wrapper for the mid-ware.

3. Work with Kusama to sign transfer and staking. Try to work with substrate CLI, fork, may submit PR.

4. Electron APP based on JS wrapper and Polkadot-js.

5. JS-API based on Chrome API to access device in web.

### 4.SDK and docs

With the SDK and fine docs, it will be more convenient to use the hardware wallet. An website will be set for them. Ref at: https://doc.wooko.ng/

### 5.Mass production

The most exciting part for hardware product is the engineer to seeing thousands device made out and they are all good at factory. There must de issued happen but to handle them is our mission.

### Milestones

#### Milestone 1 -- embedded schnorr 25519 --2 weeks-- $10000

* Folk schnorrkel and commit embedded changes as well as the compile guide for cortex-M.
* Add embedded C project to test the algorithm lib on cortex to project main repo.
* Code could be tested in any Cortex chip or using ARM simulator QEMU.
* Schedule parallel with milestone 2

#### Milestone 2 --release hardware design -- 2 weeks --$40000

* Release the Industrial Design, Mechanic Design and PCB Gerber file to project repo after final review and converted to prodction format.
* Start to pay the vendor to open the mould, the mass production tooling which will take more then 6 weeks. This is why this milestone costs the most.
* Pull in thousands of chip, OLED and components because vendors has 4-6 weeks leading time before ship them out and they have the MOQ (Minimum Order Quantity).And when you only order the MOQ, pay in advance is necessary.

#### Milestone 3 --Firmware into Beta -- 4-6 weeks --$10000

* Release firmware version(v0.8.0) firmware to repo, both source code and hex files for download.
* Including implement of: SR signer, USB-HID and Wallet function describe by Roadmap part.
* Provide Evaluation Board(EVB) for testing

#### Milestone 4 -- Work with Kusama -- 4-6 weeks -- $10000

* Release the software version(v0.2.0) and works with CLI to sign transactions for Kusama
* Using EVB in milestone 2.
* Strat before Milestone 2 finished for preparing for software integration.
* Pilot round of mass production

#### Milestone 6 -- System into Beta -- 4 weeks -- $10000

* Release software version v0.8.0
* Upgrade firmware to v0.9.0
* Implement the  JS-API which mean JS in Chrome could call the wallet directly to sign without extension and firmware update.
* Fix bugs report by testers. Start to send final PCBA(Printed Circuit Board Assembly) to testers instead of EVB.

#### Milestone 6: Mass production round stable verison -- depends both hardware and software schedule, within 3 month in total -- $20000

* Both firmware and software 1.0 released.
* 1000 free samples ready.
* First stable version released both software and firmware including Electron APP.
* The wallet is ready to keep DOTs after this milestone.

## Additional Information

Firstly, the design and source code could be open to W3F. However, we don’t recommend to open them to public from day-1 unless we could find way to deal with copycat with bad intension.

Here is the news about fake Trezor:
https://news.bitcoin.com/the-daily-fake-trezors-catching-knives-stablecoins-with-everything/

If the wallet could be made easily by copycat but with backdoors, users has less way to detect if they have a fake device. To verify the firmware hash on a blockchain may be a good choice or we find a way to force users download the firmware by themselves.

Anyway, we want it be open source project and will open most of the code, but we need time to ensure the method we provide to verify the firmware in users device is not compromised is good and easy enough for users before all design and code open to public.
