# SigOp limits

SigOp is short for "Signature Operations" and refers to the Scripting
concept that is used in Bitcoin transactions.  
The current active consensus rules and BIPs explicitly state that Bitcoin
has a limit of 20,000 sigops allowed per block.

This is a limitation that was invented to work around another much harder
to fix problem we call the
[Quadratic Hashing](https://bitcoinclassic.com/devel/Quadratic%20Hashing.html)
problem.  
In short, a block with too many signature operations can take longer
amounts of time to validate.

To put this problem in perspective, to validate the most complex
[p2pkh](http://bitcoinfactswiki.github.io/Transaction/#Pay-to-PubkeyHash)
block would theoretically occupy a laptop for a total 100 seconds. Assuming
the transaction size continues to be limited to 1&nbsp;MB.

Counting SigOps is a simple and effective way to limit the impact of such
attacks.

Some facts about SigOps as we use them today;

* The way we count sigops is known to have issues, its an estimation only.
* With the default policy of 100&nbsp;KB max for transactions, any actually
  harmful block has to be specifically crafted by a miner.
* The average amount of sigops on a 1&nbsp;MB block is between 3000 and
  6000.
* counting of sigops from
  [P2SH](http://bitcoinfactswiki.github.io/Pay_to_script_hash/)
  transactions is much more logical and correct.
* Since exceedingly large transactions are required to abuse the system,
  technologies like xthin and compact blocks increase the risk of orphaning
them and thus remove much of the risk.


Today's limit of 20,000 sigops per block has a very direct effect that a
7&nbsp;MB block will likely be the maximum until we lift or remove that
limit.

## Proposal

We suggest to change the consensus rules only very slightly and define that
the maximum sigop limits is to be set to 20,000 per MB.  
A block between 1000001 and 2000000 (inclusive) has a limit of 40,000
SigOps.

This is safe because the quadratic effects of accumulating sigops is based
on growing transaction size, not block size. So a two times as large block
can be used to create an attack that is only twice as slow. A linear growth
is expected.


## Implementation is done

Both Bitcoin Classic and Bitcoin Unlimited follow the above scheme already.
