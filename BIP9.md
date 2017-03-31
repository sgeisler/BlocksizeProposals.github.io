# Activation using BIP 9

The proposal called "Version bits with timeout and delay" was made in the
form of BIP&nbsp;9 some time ago and this is active on the network. To do a
protocol upgrade using it is easy and straight forward.

The full
[BIP&nbsp;9](https://github.com/bitcoin/bips/blob/master/bip-0009.mediawiki) text.

Its basic properties are;

* Miners support a proposal by running the software and/or setting a
  pre-determined bit in the 32-bit block-version field of blocks they mine.
* When 95% or more of blocks in a difficulty adjustment period include
  support, the proposal will be locked-in.
* Exactly one difficulty adjustment period of 2016 blocks is given for
  network participants to upgrade their software.

The BIP 9 solution was created for soft forks and as such has as goals that
are not entirely in line with what most protocol upgrades want, it doesn't
allow any flexibility in percentage of counting nor of the waiting period.

Please check the [alternative](BIP9-like.md) voting proposal as well!
