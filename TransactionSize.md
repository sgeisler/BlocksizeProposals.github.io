# Transaction size

In today's Bitcoin the transaction size is set to be 1&nbsp;MB max.
This page makes the argument that even with larger blocks, it should stay
at 1&nbsp;MB.

As described in the [SigOp](SigOpLimits) page, some years ago we discovered
an issue with transaction size getting too large. It would allow
transactions to be created which have [Quadratic hashing
time](https://bitcoinclassic.com/devel/Quadratic%20Hashing.html) and thus
be slow to validate.

This leads us to believe that a transaction of no more than
1,000,000&nbsp;bytes should be allowed, even if the blocks have more space
for this.


Some basic facts;

* A transaction is on average 244 bytes.
* The default setting for a transaction size acceptance limits is
  100&nbsp;KB, meaning miners won't mine larger transactions by default.
* Miners can manually accept and mine larger transactions, some mining
  pools use this to pay out their miners.
* The vast majority of use-cases could just split a transaction into parts,
  with no down sides.

## Future expansion

The requirement for larger transactions will likely occur at one point in
the future. Keeping the transaction limits at 1&nbsp;MB forever is not the
best idea.

Future protocol upgrades intend to actually solve the underlying scaling
issue that leads to the slowdown. One of those is [Flexible
Transactions](https://bitcoinclassic.com/devel/Flexible%20Transactions.html)
which is a different transaction format and identifies itself with a new
version number in the transaction.

When that kind of protocol upgrade is activated we can keep the current
transactions limited at 1&nbsp;MB, while allowing the new format to have
more flexible limits and thus allow growth.

This is all speculation and none of this needs to be decided this year.
