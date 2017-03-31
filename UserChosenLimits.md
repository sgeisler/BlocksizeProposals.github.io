# User chosen limits

The Bitcoin protocol currently states that the block size can not be larger
than 1&nbsp;MB (1,000,000&nbsp;bytes). This is a static limit.

A pure user chosen limit
changes the protocol to no longer have any direct limits. Indirectly there
will be factors that limit blocks sending so it will never be unlimited.

This proposal doesn't leave the system without any limits either, the block
size is chosen by users in a way that essentially gives the miners almost
complete control over the effective size limit.

The properties of this limit are these;

* Block size limits are the minimum of what miners and economic majority
  configure their nodes to accept.
* Miners can create any block size up until the chosen limit.
* Changing the limits can be done by simple discussion or similar methods
  and will not require a protocol upgrade in the future.
* Due to there not being a simple authoritative place where the actual limit
  is decided it should be expected that miners get orphans unless they
  manually keep their node's setting accurate at all times.

The most exciting part of this proposal is at the same time its weakest
point. The proposal changes automated limits using software tools with a
completely user operated and manual system.  
And users are people and they make mistakes. Mistakes that could cost them
money.

In the most pure form, any full node will be able to signal to the world
what its accept limits are (sometimes called Excessive Blocksize (EB)). The
signalling of full nodes that are not miners is trivial to
[Sybil](https://en.wikipedia.org/wiki/Sybil_attack), so mining nodes also
publish this value in mined blocks coinbase which is protected by
proof-of-work from such Sybil attacks.

In practice what will happen is that miners will ignore the announced values
and instead have a conference or other methods to communicate with other
miners where they can decide about the when and how the block size limits
should change.

The proposal to make limits completely user based is practically speaking
incomplete and in need of further refinement for on-chain signalling or
voting for each and every time the limits should change. Various Bitcoin
Client maintainers have indicated they are willing to implement any such
extensions that the mining community deems wanted.
