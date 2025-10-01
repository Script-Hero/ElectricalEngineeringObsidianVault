![[direct_mapped_cache.png]]
- A *direct-mapped [[Cache]]* where there many [[words]] in [[Memory]] being mapped to the same location in the [[Cache]], allowing quick retrieval.

## Set Associativity
1. **Direct Mapped:** a block can go in exactly **one place** in the upper-level (1-way)
2. **Set Associative:** each block can be placed in a **fixed number of** locations (n-way)
3. **Fully Associative:** a block can be placed **anywhere** in the upper level (m-way, if m is the number of blocks)
![[set_associativity_timing.png]]
- Placement of a block **whose address is 12** 
- In direct mapped placement, there is only one [[Cache]] block where [[Memory]] block 12 can be found

- In the two-way set associative placement, there would be 4 sets and the block must be in 12mod(4) = 0
- In a fully associative set, the block for address 12 can appear in any of the 8 blocks

![[different_set_associations.png]]
- An eight-block [[Cache]] configured as directly mapped, a two-way set associative, a four-way set associative, and a fully associative [[Cache]]
- The total size of the [[Cache]] in blocks is equal to the number of sets times the associativity (or set size)
- For a fixed size [[Cache]], increasing the associativity decreases the number of sets while the number of elements per set increases 
- With 8 blocks, an eight-way set associative [[Cache]] is the same as a fully-associative [[Cache]]
	- For realistically sized caches the organization would usually look rather different
- In hits and misses, we mod the # of sets again and again, so don't get the # of sets wrong!
# Cache Vocab
- **Hit** the data is present in [[Cache]]
- **Miss** the data is not present in the [[Cache]] and must be fetched
- **Hit rate** is the fraction of [[Memory]] accesses that produce a hit in the [[Cache]] (hit ratio)
- **Miss rate** 1 - hit_rate
- **Miss penalty** time needed to bring data into the [[Cache]] after a [[Cache]] miss
- **Hit time** time needed to access data in the [[Cache]] 
## Three C's
1. **Compulsory Misses**: [[Cache]] misses caused by the first access to a block that has never been in the [[Cache]], also called *cold-start misses*
	1. To reduce the number of compulsory misses, increase the block sizes since fewer [[Cache]] blocks are resulted 
2. **Capacity Misses**: [[Cache]] misses when the [[Cache]] cannot contain all the blocks needed during execution of a program. Capacity misses occur when blocks are replaced and then later retrieved
3. **Conflict Misses**: [[Cache]] misses that occur in set-associative or direct-mapped caches when multiple blocks compete for the same set. Conflict misses are those misses in a direct-mapped or set-associative [[Cache]] that are eliminated in a fully associative [[Cache]] of the same size. These [[Cache]] misses are also called *collision misses*.


# Cache Problems

![[Pasted image 20250501031336.png]]
**For this [[Cache]], the lower portion of the address is used to select a [[Cache]] entry consisting of a data word and a tag.** 
- This holds 1024 [[words]] / 4 KiB, as we assume 64-bit addresses. 
- The tag from the [[Cache]] is compared against the upper portion of the address to determine whether the entry in the [[Cache]] corresponds to the requested address. 
- The [[Cache]] has 2^10 [[words]] and block size of 1 word, 10 bits are used to index the [[Cache]], leaving 52 bits to be compared against the tag
	- If the tag and upper 52 bits of the address are equal and the valid bit is on, then the request **hits** in the [[Cache]], and the word is supplied to the [[Processor]], otherwise a **miss** occurs

**How many bits are needed to build such a [[Cache]]?**
$$2^n\times[1+\text{v}+\text{Tag}+\text{Data}]$$
$$2^{n}\times[1+(64-n-2)+32]$$ and for this [[Cache]], $n=10$ as seen in the diagram


![[four_way_set_associative_cache.png]]
- Four-way set associative [[Cache]]
- Requires 4 comparators and a 4-to-1 MUX
- The comparators determine which element of the selected set (if any) matches the tag
- The output of the comparators is used to select the data from one of the four indexed sets, using a multiplexor 

![[Pasted image 20250501033040.png]]