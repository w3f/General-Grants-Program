# Project name
Anastasis

## Project Description

Summary: Anastasis will allow users to securely recover secret keys
without necessarily relying on passwords or other key material.  Our
contacts at the European Central Bank informed us about a requirement
for "custody" solutions denominated in Euros to support such a
password-less recovery fearture.  It improves the threat model if many
custody projects share the same open source system for this purpose.


GNU Taler is free software for anonymous payments using blind
signatures.  GNU Taler operates above any "custody" layer, such as
conventional bank accounts.  The GNU Taler project was informed by
regulators that we must offer a way for users to recover access to
their wallet data without relying on a passphrase or key.

We, however, deemed it an unacceptable risk for any individual provider
to be able to directly recover a user's core secret and possibly steal
their coins in the underlying custody system.  Anastasis permits users
to split their core secret across any number of semi-trusted providers
they select.  The user specifies which combination(s) of providers are
required to authenticate the user for the core secret to be recovered.
Importantly, users remain free to make passwords or cryptographic
secrets critical for recovery, but Anastasis increases their options
and addresses this legal hurdle for providers.

The high level process is that the user has some core secret which
they use to encrypt their wallet data.  The user then publishes an
encrypted version of their wallet data to some untrusted backup
service (like IPFS or Dropbox).  The symmetric encryption key used
for the backup is then encrypted with a policy key.  This policy key
is derived from multiple policy shares, where each policy share is
given to one of the Anastasis providers.  The Anastasis providers
are not given the policy share or the user's identity in the clear,
but only again encrypted with another identity key, which is derived
from user's attributes like name, social security number or birthday
which cannot be easily forgotten as requires by regulators.
After this, the policy providers are given an authentication method
(SMS, mail, video-indent) and the associated authentication data
(phone number, address, photo) needed to perform the authentication.
If at a later point a user needs to recover their core secret, they
authenticate to (a subset) of the Anastasis providers, which in
response disclose their policy key share to the user. The user
combines the policy key shares to decrypt the core secret, and finally
downloads and decrypts their backup.

Our design uses only symmetric cryptography, is post-quantum secure,
and never discloses any information to the Anastasis providers beyond
that required for authentication.  We only require this personal data
when doing authentication, and it is never disclosed before this point.
The latter is only ever disclosed if and when the user attempts to
recover their core secret.  An attacker should need the (semi-public)
identity information (name, birthdate, social security number, other fixed
attributes) and to successfully pass authentication to obtain the core
secret from a provider.  We believe this scheme will satisfy the regulatory
requirements for wallets containing Euro-denominated coins.

Anastasis would provide the service as a REST API with an associated client
library as Free Software under the AGPL, in line with the GNU Taler
licensing strategy as agreed with the GNU project. The REST API includes
a mechanism for the providers to request payment for the offered service.

The project would benefit the ecosystem as a distributed key splitting
system is useful for various applications, including storing GnuPG key
rings, crypto-currency wallets, custody based wallets like Taler, and others.
Furthermore, the authentication methods (SMS, video-indent, snail mail)
could likely be adopted for KYC checks in finance-related domains.

We do not intend to directly integrate Anastasis with Substrate or
Polkadot wallet software.  We do, however, expect the resulting
Anastasis infrastructure to be used by various wallet implementations,
presumably including some Polkadot wallets.  Also, some stable coins
designs fall under the regulations that Anastasis helps address.



## Team members
* Christian Grothoff
* Dennis Neufeld
* Dominik Samuel Meister

## Team Website
* https://gnunet.org/
* https://taler.net/
* https://bfh.ch/
* https://grothoff.org/christian/

## Legal Structure
The project would be executed at the University of Applied
Sciences in Bern.

## Team's experience
Christian Grothoff is Professor for Computer Science at
BFH as well as GNU maintainer of GNUnet, GNU Taler and
GNU libmicrohttpd. He has been designing and implementing
privacy-enhancing network protocols for almost 20 years.

Dennis Neufeld and Dominik Samuel Meister are currently
finishing their last semester in Computer Science at BFH
in the Information Security focus area.


## Team Code Repos
* https://git.taler.net/
* https://git.gnunet.org/

## Team LinkedIn Profiles
* https://grothoff.org/christian/

## Development Roadmap

We have started the implementation in the context of the
GNU Taler project under the AGPLv3+ license.

Given that the specification is already largely done,
we forsee the following milestones:

#1 Server backend and low-level HTTP client (CHF 5000); 4 weeks
Implement the REST API to store and retrieve the policy documents
and allow users to request authentication procedures.

#2 Cryptographic library (CHF 5000); 4 weeks
Implement, test and document the client-side secret splitting and
recovery, representation of policy documents and encryption/decryption
logic.

#3 High-level API (CHF 7500); 6 weeks
Combine the cryptographic library with the HTTP backend. Write a simple
command-line client to test key splitting and recovery end-to-end.

#4 Authentication backends (CHF 10000); 8 weeks
Implement authentication backends for SMS, mail and video-indent on the
server-side.  Basically, upon a recovery request, the server must trigger
the respective authenciation procedure, and upon its completion release
the policy share to the proper client.  For the first design, we would
focus only on the SMS-authentication backend due to its lower cost and
easier integration.

#5 Payment integration (optional, if we are fast with the other steps)
Implement support for users paying for the service, to ensure that the
Anastasis service providers can operate under a for-profit regime and
not only as non-profits.

Hence the total duration of the project would be 22 weeks after
project start (real-time).

Longer-term plans would be to include various payment methods, more
authentication methods, setup proper businesses offering the service,
and to integrate Anastasis with applications such as pretty-easy-privacy.


## Additional Information

We have made a first technical specification of Anastasis
available at https://docs.taler.net/.

BFH is hosting our infrastructure, and we may be able to
apply some match funding from Taler Systems SA.

BFH has (as far as we know) not applied for any other Web3 grants.

In the context of the German PrototypeFund, there is work
on an implementation of Shamir Secret Sharing, but as far
as we know, it is NOT:
- integrating a business approach with payments for the
  use of the service
- integrating proper backends for user authentication
- offering post-quantum security
- offering flexible policies beyond k-out-of-n.
