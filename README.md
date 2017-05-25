# Intro

Should you consider a protocol upgrade in Bitcoin that allows the coin to continue organic growth and more customers, then this is the right place to come to.

Bitcoin requires a protocol upgrade (sometimes incorrectly called a hard fork) because of the 1&nbsp;MB-blocksize limit. Doing a simple protocol upgrade is easier said than done and we have seen a long list of suggested methods over the years.

These pages will attempt to dissect the concepts and provide you with enough knowledge to know what it takes to do a good upgrade.

# Required components

The goal of a block size protocol upgrade is mostly the same for everyone, but details differ and there are various options on how we do a safe upgrade of the entire Bitcoin project. I will explain this in several parts. First the **Actual block-limits**. This is the final goal we want to reach. Then everyone needs to follow the same strategy on actually activating these new changes, which is discussed in the **Activation method**.

Last we'll discuss various **Other properties** that are important to having a successful bigger block size. If we were to skip the sigop question that would likely mean we can't effectively get above 3 or 4 MB blocks.

## Actual block-limits

Here are some ways we can make the amount of transactions that Bitcoin can handle every hour go up, all of them focusing on removing the stifling 1&nbsp;MB block size limit.

It is important to realise that the block-limits will not be the same as
the actual size of the mined blocks. The actual growth will be organic and gradual.

1. [Static Limits](StaticLimits.md).  
The limits are currently 1,000,000 bytes, this is a static limit. A proposal can change the limit to another one, which requires another protocol upgrade when we reach that limit.

2. [Dynamic Limits](DynamicLimits.md).  
To avoid fears of unlimited blocks the maximum size of blocks can be decided by some algorithm in a dynamic way. Based on past usage, for instance.

3. [User Chosen](UserChosenLimits.md).  
This idea moves the block-size limits out of the protocol and into the hands of the market.

## Activation method

1. Signalling with [BIP 9](BIP9.md).  
A limited flexibility solution, but easy because the code is already there.

2. Signalling with [Block-Version-Bit](BIP9-like.md) (similar to BIP 9).  
Expanding on (1), but allowing other than 95% voting threshold and other details.

3. A chosen [block-height](Blockheight.md).  
This is by far the simplest technically, but it moves all negotiations off of the blockchain.

4. [Dynamic block-height](DynamicBlockheight.md) by vote.  
A combination of a simple solution, but with miners being able to support specific proposals.

## Other properties

1. [SigOp](SigOpLimits.md) limits  
For fear of bad miners a 'sig-op' limit was introduced some years ago which needs adjustment if we want to allow more growth.

2. [Transaction-size](TransactionSize.md) limits.  
Bigger transactions help some use-cases, but hurt others. A simple decision need to be made about the maximum size allowed.

# Features to avoid

* [Malleability / Quadratic Scaling](Malleability.md) fixes.  
While this is a very popular topic, there is no need to make a block size upgrade more complex by adding more. We can do more fixes in the future.

# Existing proposals

| BIP  | Limits | Activation | Comment|
| ---- | :-----:| :---------:| ------:|
|BIP100| 2: dynamic | 2: BIP9-like | 5% change limit rule |
|BIP101| 2: dynamic | 2: BIP9-like | 8&nbsp;MB, doubles every year |
|BIP102| 2: dynamic | 3: flag-day | 2&nbsp;MB |
|BIP109| 1: static | 2: BIP9-like | 2&nbsp;MB, 750/1000 blocks plus 28 days |
|EC (no BIP)| 3: user | none | |
