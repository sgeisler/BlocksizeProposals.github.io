# Further scaling protocol fixes

Over the years we have identified a list of problems that should be fixed in the protocol for good scaling.

* Malleability
* Quadratic Hashing problem of transaction.

These are the most visible problems, not because they are in need to be fixed but because they have been advertised a lot more than any other problems.

These problems are not actually in need to be resolved right now. Nothing is actively waiting for them to be fixed on the main chain.

A protocol upgrade that **only** fixes the block size limits will be easy to roll out because only full nodes need to have compliant software. SPV wallets don't need any changes.

Any solution for malleability would require a massive cycle of upgrades and tests, including all SPV wallets and hardware wallets.

We should not try to combine them in one package, that is irresponsible and dangerous.

