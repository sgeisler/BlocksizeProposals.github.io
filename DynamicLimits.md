# Dynamic Blocksize Limit

The Bitcoin protocol currently states that the block size can not be larger than 1&nbsp;MB (1,000,000&nbsp;bytes). This is a static limit.

A simple example of a dynamic limit is [BIP-101](https://github.com/bitcoin/bips/blob/master/bip-0101.mediawiki) which made the block size limit grow based on the time stamp of the block.

Even more advanced are ideas which take some data from the blockchain and use it to calculate the new block size limit.

The properties of this type of limit are these;

* Miners can create any block size up until the current dynamic limit.
* The growth of Bitcoin is always limited to some magic numbers that can not be changed.
* The more complex the solution, the harder it is to convince everyone that the magic numbers and algorithm is the right one.


A dynamic limit is one that gives miners less room to grow and respond to market demands, at the same time it protects the full nodes on the network from miners deciding to make blocks that are so big they are unhealthy.

This means that the the dynamic limit at is basis constitutes a risk mitigation technique to lower the trust in miners' willingness to do what is good for Bitcoin.

This raises the question if the risk that is being mitigated is actually in
need to be addressed. There is no evidence that this is needed, and Bitcoin
economics shows that the best ones to decide on the block size are the
miners ([source](https://bitcoinclassic.com/devel/Blocksize.html)).

There is a cost to removing this risk. The miners will simply be less able
to respond to the market. A huge 2 day load on the network (Black Friday,
for instance) may take a week to remove.
