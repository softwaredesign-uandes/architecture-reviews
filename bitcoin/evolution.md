# Bitcoin - Evolution

[TOC]

## History and Evolution

### Number of files per commit

Starting from the first commit (with 45 files) to the official repository until 66667acc (with 2052 files).

![image-20201109214440714](assets/image-20201109214440714.png)



## Architecture Decision Records

The Bitcoin community introduce new features, changes and relevant information to the technology documenting the proposals through a standardized design document called "Bitcoin Improvement Proposal" (BIP). It contains precise technical specification of the attribute and a rationale for given feature.

All BIPs can be found [this repo](https://github.com/bitcoin/bips/blob/master/README.mediawiki).

###  [“BIP 21 - URI Scheme”](https://github.com/bitcoin/bips/blob/master/bip-0021.mediawiki)

> **Context**:
>
> - To increase the usability of Bitcoin and make it accessible to the layman user, an easy method of payment had to be envisioned. It’s needed that a user could just click a link or scan a qr code to start the process.
> - The method should be standard to work with any wallet. 
>
> **Decision**:
>
> - Use the *bitcoin:* URI with a defined schema that comply [RFC 3986](https://tools.ietf.org/html/rfc3986)
> - It should represent a one-time payment, not revealing personal information.
> - The URI scheme name should give a description if someone from outside sees it.
>
> **Status**: Active
>
> **Consequences**:
>
> - Since several clients already use a *bitcoin:* URI scheme similar to this one, a grace period of 6 months is given for developers to update their clients to comply.

### [“BIP 70 - Payment Protocol”](https://github.com/bitcoin/bips/blob/master/bip-0070.mediawiki)

> **Context**:
>
> - BIP 21 presented some security problems. A more secure method was needed to enable a better customer experience and security against man in the middle attacks on the payment process.
>
> **Decision**:
>
> - Payment protocol messages encoded using Google’s Protocol Buffers authenticated using 
> - Communicated over http/https.
> - Might extend this payment to other encoding, PLI systems or transport protocols.
>
> **Status**: Final
>
> **Consequences**:
>
> - There’s been some controversy over the idea that some entities provide a certificate that can validate payments, since this goes against the decentralization provided by Bitcoin, making the transaction process dependent on external, defined players.

 ### [“BIP 32 Hierarchical Deterministic Wallets”](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki) 

> **Context**:
>
> - Losing a wallet means losing all the money it “holds”, a method to deterministically generate a wallet is needed. Also avoiding the necessity for a backup after every transaction without exposing the private keys.
> - The method should be standardized so that the deterministic wallet can be interchanged between different clients.
>
> **Decision**:
>
> - A method for deterministically generating the same keys every time the same seed us used is needed.
>
> **Status**: Final
>
> **Consequences**:
>
> - All wallets should use the same standard algorithm to enable wallet portability. 