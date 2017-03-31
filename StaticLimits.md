# Static Blocksize Limit

The Bitcoin protocol currently states that the block size can not be larger than 1&nbsp;MB (1,000,000&nbsp;bytes). This is a static limit.

The properties of this limit are these;

 * Miners can create any block size up until the static limit.
 * Miners can agree to 'soft-fork' to a lower limit many times.
 * The entire bitcoin ecosystem needs to agree to change the block size
   limits to a larger limit
   via a protocol upgrade when the current limit becomes too small.


Bitcoin is a market driven system. Its value comes from a continuously
increasing network effect based on new people using it and thereby
increasing its value, which causes more new people to use it and so on.

In such a market driven system a hard static limit which caps the growth,
forces the entire system to evolve or die. A coin that has a hard limit
will, on an open market, loose out and ultimately be replaced by a coin
that does not have such a limit.

The idea of "evolve or die" is thus a double edged sword. It forces an
ongoing development effort and punishes an unchanging system.  In a
distributed system it is important to note that this is one of the few ways
to force people to upgrade their software every couple of years. All of
these effects are generally seen as a healthy way to keep the system going
forward.

The expected outcome of picking a new static value for the coming upgrade is this;

* We should have ample opportunity to grow for a considerable amount of time.
* In this time Bitcoin can evolve various strategies to grown beyond the
  boundary of the new static limit. Layer 2 strategies will keep pressure
  for ongoing development.
* A change of attitude; we know that eventually a new protocol upgrade will
  have to happen, and as such we better get good at doing them.
