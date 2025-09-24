The memories in the Datapath are actually caches, which is the level of memory hierarchy between the processor and main disk memory. 

Basic methodology: the cache contains a collection of recent references. When trying to recall a piece of data for the first time, the data is not inside the cache, and gets brought in.
- How do we know if a data item is in the cache?
- If that data is in the cache, how do we find it?

If each word can go to exactly 1 place in the cache, it's easy to find. Called **Direct Mapped Cache**.
- Easiest way is to assign a location in the cache based on the *address* of the word in memory
- Almost always use this mapping to find a block: $$(\text{Block address})\text{modulo}(\text{Number of blocks in the cache})$$
- If the number of entries in the cache is a power of 2, then module can be computed using $\log_2(\text{Cache size in blocks})$ bits of the address.
- For example, an 8-block cache uses the three lowest bits ($8=2^3$) of the block address
	- Memory addresses between 1 and 29 map to locations 1 and 5 in a direct-mapped cache of 8 words
	- ![[direct_map_cache_example.png]]
- Since each cache location could have one many possible memory address locations, we make sure the word we're retrieving is the one we want by using the **tag** field, which contains the bits that were not used in the mapping
- We also use the **valid** field to indicate that there is valid information in that cache location. For example, when the processor first starts up, the data in the cache is meaningless so the **valid** bits all start off as $0$

## Reading from Cache
- The cache starts off as empty on boot-up
- Every word we request from the cache that is a miss on an empty block we just fill that block in with the data from memory
- If we request a word from a block and *get the wrong word* (as in, the block is not empty, but the tag is not what we expected / a different word is already loaded into it)
- Since words in memory are aligned by multiples of 4 bytes, we can ignore the lowest 2 bits in a memory address because they occur every 4 bytes (think PC + 4) 

### Cache Size
For the following situation:
- 64-bit addresses 
- A direct-mapped cache
- Cache size is $2^n$ blocks, so $n$ bits are used for the index
- Block size is $2^m$ words ($2^{m+2}$ bytes) are used for the word within the block, and two bits are used for the byte part of the address
The size of the tag field is:
$$64-(n+m+2)$$
The total number of bits in a direct-mapped cache is:
$$2\times(\text{block size}+\text{tag size}+\text{valid field size})$$

![[4kb_cache.png]]
For this example, the block size is $2^m$ words ($2^{m+5}$ bits), and we need 1 bit for the valid field, the number of bits in such a cache is:
$$2^n\times(2^m\times32+(64-n-m-2)+1)=2^n\times(2^m\times32+63-n-m)$$
We can see from the image the $n=10$ and $m=1$ (we only store 1 word per block, definition of a direct-mapped cache) 

We still call this a 4 KiB cache because we can store 1024 words = 4 KiB

### Mapping an Address to a Multiword Cache Block
Consider a cache with 64 blocks and a block size of 16 bytes (2 words). To what block number does byte address 1200 map?
- Using formula: $(\text{Block address})\text{modulo}(\text{Number of blocks in the cache})$
- Where the address of the block is: $\frac{\text{Byte address}}{\text{Bytes per block}}$
- Notice that this block address is the block containing all addresses between: $[\frac{\text{Byte address}}{\text{Bytes per block}}]\times\text{Bytes per block}$ and $[\frac{\text{Byte address}}{\text{Bytes per block}}]\times\text{Bytes per block}+(\text{Bytes per block}-1)$
- Therefore with 16 bytes per block, byte address 1200 is block address $[\frac{1200}6]=75$ which maps to cache block number $75\text{modulo}64=11$. In fact, cache block 11 maps all addresses between 1200 and 1215

Multiword Blocks exploit spatial locality to lower miss rates.
- Increasing block size decreases miss rate
- Once the block size becomes a significant fraction of the cache size, the miss rate may go up, because the # of blocks you are able to store decreases
	- So blocks will often be bumped out of cache before many of its words are accessed
	- Spatial locality among the words in a block decrease with a very large block; consequently the benefits of the miss rate become smaller 
![[block_size_tradeoff.png]]

## Miss Cost
If we have a cache miss (try to retrieve a word from cache that isn't there) then there is a miss penalty in time required to fetch the word from the next lowerest level of memory and load it into the cache. The time to fetch the block consists of:
1. the latency to the first word 
2. transfer time for the rest of the block
For direct-mapped caching, the transfer time will likely increase as block size increases. The improvement in miss rate starts to decrease as the blocks become larger. This means that **the increase in miss penalty overwhelms the decrease in the miss rate for blocks that are too large, decreasing cache performance.**
- If we design the memory to transfer larger blocks more efficiently, we can increase the block size and obtain further improvements in cache performance.

## Handling Misses
The control unit must detect a cache miss and process the miss by fetching the requested data from memory (or a lower-level cache). When a cache miss is detect, the control unit must stall the entire processor (freezing the contents of the temporary and programmer-visible registers) while we wait for memory.

On an instruction cache miss (trying to read an instruction from the instruction memory that is not there):
1. Send the original PC value to memory
2. Instruct main memory to perform a read and wait for the memory to complete its access
3. Write the cache entry, putting the data from memory in the data portion of the entry, writing the upper bits of the address (from the ALU) into the tag field, and turning the valid bit on
4. Restart the instruction execution at the first step, which will refetch the instruction, this time finding it in the cache 
The control of the cache on a data access is essentially identical: on miss, we stall the processor until the memory responds with the data.

## Handling Writes
Imagine on a store instruction that that the data is only written into the data cache and not the memory. This would cause a mismatch / inconsistent data. So we write to both the memory and the cache, called a **write-through**. 
- On a write-miss (we want to update a record in the cache, but that block isn't even in the cache yet)
	- we first fetch the words of the block from memory
	- then place it into the cache (potentially overwriting the wrong-tag word in the cache that caused the miss). 
	- We then write the word to main memory (write-through).
- Writes can always be done in one cycle
	- We always read the tag and write the data portion of the selected block
	- If the tag matches the processor continues normally
	- If the tag does not match, we generate a write miss 


However, doing a write-through every time is inefficient, so we use a **write buffer** which stores the data while its waiting to be written to memory. 
- When a write to main memory completes, that entry in the write buffer is freed. 
- If the write buffer is full when the processor reaches a write, then the processor must stall until there is an empty position in the write buffer (meaning a write to main memory is forced)
- If the rate at which memory can complete writes is less than the rate at which the processor is generating writes, then *no amount of buffering can help because writes are being generated faster than the memory system can accept them.*
- Even when the rate that writes are generated is less than the rate that memory can accept them, stalls can still occur when writes occur in bursts.
	- To reduce these types of stalls, processors usually increase the depth of the write buffer beyond a single entry


An alternative to the write-through scheme is the **write-back** scheme.
- When a write occurs, the new value is written *only to the block in cache*
- The modified block is written to the lower level of the hierarchy *when the block is replaced in cache*
- Write-back scheme improves performance especially when the processor can generate writes as fast or faster than the writes can be handled by the main memory
- But write-back is more complex to implement than write-through
- Stores require 2 cycles
	- one cycle to check for a hit
	- one cycle to actually perform the write 
 - A write buffer makes write-though use only 1 cycle via pipelining
	- The processor does the cache lookup and places the data in the store buffer during the normal cache cycle
	- Assuming a cache hit, the new data are written from the store buffer into the cache on the next unused cache access cycle 
- Write buffers in write-back schemes reduces the miss penalty when a miss replaces a modified block
	- The modified block is moved to a write-back buffer associated with the cache while the requested block is read from memory 
	- The write-back buffer is later written back to memory
	- Assuming another miss does not occur immediately, this techniques halves the miss penalty when a dirty block (a block in cache that has been written to but the changes haven't been written back to the main memory yet) must be replaced