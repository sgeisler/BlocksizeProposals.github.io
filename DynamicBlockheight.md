# Activation on voted block-height

The usage of the term "block-height" is an implementation detail, it is
easier to just think of this proposal as activation on a specific date in
the future.  
Block height is used as it is more reliable and easier to predict.

This activation method is different from the direct [block
height](Blockheight) proposal in that the actual activation date is
something that can be voted on by miners.

In this activation method the actual activation is 3 steps.

1. A miner proposes a change using various flags which he encodes in
his coinbase. One of the flags is the effective block-height.
2. Other miners can make a counter proposal or they agree with the first
miner and thus they 'vote' for his proposal.
3. If there is enough support, the vote is locked in and activated.


The list of flags that are actually voted on can be very flexible and
many can be combined. Examples of flags are; block-height,
grace-period, required-support etc.

The basic properties are;

* Miners can make proposals on the blockchain or by conference for a date
  of the protocol upgrade.
* Should there be enough votes then at the chosen block-height the new
  rules come into action.
* The first block that is mined which is only valid under the new rules
  marks the traditional "hard fork" block.

This proposal is probably the most complex solution there is, but it is
also the most flexible.  Miners can act rapidly on changing markets or take
it slow and be safe and most important is that there is no need to do
software upgrades while still allowing a very different way of doing
activation.

The down side of this proposal is that it is more complex to understand, a
natural consequence of its flexibility.

## A more in-depth example

Lets define a list of 'flags';

1. block-height-absolute
2. grace-period-block-count
3. required-block-count
4. block-count-window

A miner can make several actual protocol proposals from this list of
properties. Notice how the first and the second can not be used in the same
proposal.

Here is an example which emulates the BIP&nbsp;109 activation method of
requiring 750 voting blocks in a window of 1000 blocks, and then 28 days
(is 4032 blocks) grace period.

> 2:4032, 3:750, 4: 1000

The actual data to put in the coinbase is likely better to be binary and
not ASCII like my text example here, but details like this quickly are
off-topic for this site.

If this is used in combination with [user chosen limits](UserChosenLimits)
a flag can be added for a new block size limit.

