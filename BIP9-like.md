# Activation using voting bits (like BIP&nbsp;9)

This proposal allows activating a protocol upgrade based on a pre-chosen
percentage of miner support (in the form of blocks mined) and a pre-chosen
"grace period" which will allow the network to become accustomed to the new
rules.

This is very similar to [BIP9](BIP9), but since that proposal is very
inflexible with regards to activation threshold and other variables this is
a modified version.

The basic properties are;

* Miners support a proposal by running the software and/or setting a
  pre-determined bit in the 32-bit block-version field of blocks they mine.
* When an percentage of blocks supports the proposal it will become
  "locked in".
* A number of blocks later (for instance 1 month) miners are obligated to
  support the new rules, which allows bigger blocks to be mined.


The advantage of this method is that there is a very clear indication when
the bigger blocks are allowed. Anyone can look at the blockchain and do the
calculations.

It is also very flexible as any number of blocks can be chosen, for
instance BIP109 (2&nbsp;MB) would have activated at 750 blocks out of 1000.
Miners can decide on any number of blocks.

The down side is that a level of support has to be decided early on. This
means that opposing miners can buy more hashpower or orphan voting blocks
and other such games in order to fight the block size upgrade. The problem
here is that there is no longer a human judgement that can decide that
support is "good enough".
