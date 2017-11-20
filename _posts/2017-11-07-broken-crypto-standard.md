---
layout: post
title: When the Devil is in the Crypto Standard
bigimg: /img/crypto.jpg
share-img: /img/crypto.jpg
tags: [IEEE P1753, Cryptography, Vulnerability]
---
What happens when a _security specification_ goes wrong - not because people use it in a wrong way, but the specification is poorly constructed without giving much thought about **potential security risks**? Well, kudos to the researchers from my research lab at [FICS](http://fics.institute.ufl.edu/) who have unveiled the broken standard, namely IEEE P1735 before it causes major damage. The IEEE P1735 standard is used to protect digital intellectual property. It allows vendors to combine their code to create new products while ostensibly protecting their intellectual property from reverse engineering and theft. Researchers have found **seven _CVEs_** in cryptographic standard that can be exploited to gain access to _intellectual property in plain_.

Quoting editor's note from [SANS NewsBites](https://view.email.sans.org/?qs=226e61b3b04380e621ab9cb248a6db8ce491db644404b0920f22e9ff96bb5ed0f88511ea9e7ae55c90d99ec0a609dfb11f1bd1296b164eeb)
"This flawed standard is less likely going to affect end users, but more a problem to manufacturers of "Systems on a Chip" devices. The standard is used to encrypt and authenticate drawings exchanged between companies. An adversary would be able to replace features in drawings (for example adding a backdoor) without the manufacturer of the device realizing that they are producing an altered circuit."

Read more here :
- [Read the research paper here](http://eprint.iacr.org/2017/828.pdf)
- [BleepingComputer](http://www.bleepingcomputer.com/news/security/crypto-bugs-in-ieee-standard-expose-intellectual-property-in-plaintext/)
- [ThreatPost](http://threatpost.com/us-cert-warns-of-crypto-bugs-in-ieee-standard/128784/)
- [CERT Warning](http://www.kb.cert.org/vuls/id/739007)
