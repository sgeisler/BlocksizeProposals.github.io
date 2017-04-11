# Activation on block-height (Flag day)

The usage of the term "block-height" is an implementation detail, it is
easier to just think of this proposal as activation on a specific date in
the future.  
Block height is used as it is more reliable and easier to predict.

What this activation method lacks is a specific way to find out how much
support there is.

The basic properties are;

* Miners have decided on a date to do the protocol upgrade.
* At a certain block-height the new rules come into action.
* Miners are allowed to soft-fork down to the old rules for as long as they
  feel is safe.
* The first block that is mined which is only valid under the new rules
  marks the traditional "hard fork" block.
* With enough miner support and given enough time the chance of orphans is low.


The activation method is by far the simplest there is from a technical
point of view. It can't really be gamed and it is very obvious to everyone
when the new rules become active.

The down side is that support for the new rules has to be broad enough to
be sure that the new rules will have majority support and we avoid orphans.
