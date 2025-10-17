# Definitions
### CPU Time
The clock cycles that the CPU spends executing the program and the clock cycles the CPU spends stalled, times the total time per clock cycle.
$$\text{CPU Time}=(\text{CPU execution clock cycles}+\text{[[[[[[[[[[Memory]]]]]]]]]]-stall clock cycles})\times\text{Clock cycle time}$$

### Memory Stall Clock Cycles
[[Memory]]-stall clock cycles come primarily from [[Cache]] misses, so we make this assumption for simplicity (in the real world, stalls can be complicated and difficult to predict). We define the number of [[Memory]] stall cycles as the total number of stall cycles coming from reads and writes:
$$\text{[[[[[[[[[[Memory]]]]]]]]]]-Stall Clock Cycles}=(\text{Read-stall cycles}+\text{Write-stall cycles)}$$
- If we assume that write buffer stalls are negligible and that the read and write miss penalties are the same (the time to fetch the block from [[Memory]], usually they are the same) we can combine the reads and writes by using a single miss rate and the miss penalty:
$$\text{[[[[[[[[[[Memory]]]]]]]]]]-stall clock cycles}=\frac{\text{[[[[[[[[[[Memory]]]]]]]]]] accesses}}{\text{Program}}\times\text{Miss rate}\times\text{Miss penalty}$$
- We can also factor this as:
$$\text{[[[[[[[[[[Memory]]]]]]]]]]-stall Clock Cycles}=\frac{\text{Instructions}}{\text{Program}}\times\frac{\text{Misses}}{\text{Instruction}}\times\text{Miss penalty}$$

### Read Stall Cycles
Read-stall cycles can be defined in terms of the number of read accesses per program, the miss penalty in clock cycles for a read, and the read miss rate:
$$\text{Read-stall cycles}=\frac{\text{Reads}}{\text{Program}}\times\text{Read miss rate}\times\text{Read miss penalty}$$
### Write Stall Cycles
For a write-through scheme we have 2 sources of stalls: write misses (which usually require that we fetch blocks before continuing the write) and write buffer stalls (which occur when the write buffer is full when a write happens). Therefore, the cycles stalled for a write is:
$$\text{Write-stall Cycles}=(\frac{\text{Writes}}{\text{Program}}\times\text{Write Miss Rate}\times\text{Write Miss Penalty})+\text{Write buffer stalls}$$
- Write buffer stalls depends on the proximity of writes (not just frequency) so there isn't a simple equation that computes such stalls 
	- In systems with reasonable write buffer depth (4 or more [[words]]) and a [[Memory]] capable of accepting writes at a rate that significantly exceeds the average write frequency in programs (like by a factor of 2) then the write buffer stalls will be small and we can safely ignore them
	- A system that does not meet this criteria is poorly designed and should either have:
		- A deeper write buffer
		- Write-back organization

Write-back schemes can have stalls arising from needing to write a [[Cache]] block back to [[Memory]] when the block is replaced. 

### Average Memory Access Time (AMAT)
To capture the fact that the time to access data for both a hit and a miss affects performance, we use *average [[Memory]] access time* to examine alternative [[Cache]] designs. This considers hits, misses, and the frequency of different accesses:
$$\text{AMAT}=\text{Time for a hit}+\text{Miss Rate}\times\text{Miss Penalty}$$




# Flexible Block Placement
- **Direct mapped [[Cache]]** as discussed in [[Caching]] is when a block can be placed in exactly one location.
- **Fully associative [[Cache]]** is when a block can be placed in *any* [[Memory]] location
	- To find a block in [[Cache]], all entries must be searched (because any block can be anywhere)
	- Searching is done in parallel with a comparator associated with each [[Cache]] entry 
	- Comparators are expensive and increase costs significantly
		- So fully associative [[Cache]] is mainly used for caches with a small number of blocks
- **Set associative [[Cache]]** is when there are a fixed number of locations where each block can be placed
	- Set associative with $n$ locations for a block is called a $n$-way set-associative [[Cache]], meaning that the [[Cache]] consists of a number of sets that each contain $n$ blocks.
	- Each block in the [[Memory]] maps to a unique *set* in the [[Cache]] given by the index field, and a block can be placed in *any* element of that set
	- Combines direct-mapped placement and fully-associative placement: a block is directly mapped into a set, and then all blocks in the set are searched for a match
	- The set containing a [[Memory]] block is given by $(\text{Block number})\text{modulo}(\text{Number of sets in the [[[[[[[[[[Cache]]]]]]]]]]})$
	- **Offset Bits = $\log_2(\text{block size in bytes})$**
	- **Index bits = $\log_2(\text{number of sets})$**
![[set_associations.png]]

A direct mapped [[Cache]] is just a one-way set associative [[Cache]] (each [[Cache]] entry holds one block and each set has one element). A fully associative [[Cache]] with $m$ entries is simply a $m$-way set-associative [[Cache]] (it has one set with $m$ blocks and an entry can reside in any block within that set).

Increasing the degree of associativity usually decreases the miss rate, but has a potential increase in the hit time.

![[associativity_example.png]]
- Different ways to map an eight-block [[Cache]]

## Locating a Block in the Cache
Let's consider finding a block in a [[Cache]] that is set-associative
- Each block includes a tag
	- We search each tag in the set to see if that's the word / address we want
	- All the tags in the selected set are searched *in parallel*
- Index value is used to select the *set* containing the address of interest

If the total [[Cache]] size is kept the same:
- Increasing the associativity raises the number of blocks per set 
	- Which is the number of simultaneous compares needed to perform the search in parallel
- Each increase by a factor of 2 in associativity decreases the size of the index by 1 bit and expands the size of the tag by 1 bit 

In a fully associative [[Cache]], there is effectively only 1 set, and all the blocks must be checked in parallel
- Therefore there is no index
- The entire address, excluding the block offset, is compared against the tag of every block
- In other [[words]], we search the full [[Cache]] without any indexing

In a direct-mapped [[Cache]], only a single comparator is needed because the entry can be in only 1 block and we access the [[Cache]] simply by indexing.

![[4_way_associative_cache.png]]
- four-way set-associative [[Cache]]
- four comparators and a 4-to-1 multiplexor
	- comparators to see if any of the tags match
	- multiplexor selects the output signal based on the 4-bit digital signal from the comparators 


## Choosing which Block to Replace
1. In a **direct-mapped [[Cache]]** exactly one block is a candidate to be replaced
2. In a **n-associative [[Cache]]**, 1 of $n$ blocks are candidates to be replaced
3. In a **fully-associative [[Cache]]**, all blocks are candidates to be replaced

Most common scheme for replacement is **least recently used (LRU)** 
- The block replaced is the one that has been unused for the longest time
- In a two-way set-associative [[Cache]] we have a single bit in each set and setting that bit to indicate whatever element was most recently referenced (set to $0$ if the first element was most recently referenced and set to $1$ if the second element was most recently referenced)
- As associativity increases, LRU gets harder to implement 

## Reducing Miss Penalty with Multilevel Caches
To close the gap between increasingly fast modern clock rates and the long time required to access [[DRAM]], most microprocessors use an additional level of [[Caching]].
- Second-level [[Cache]] is normally on the same chip and is accessed whenever a miss occurs in the primary [[Cache]]
- If the second-level [[Cache]] contains the desired data, the miss penalty for the first-level [[Cache]] will be essentially the access time of the second-level [[Cache]] (much faster than the access time of the main [[Memory]])
- If neither the first-level or second-level [[Cache]] contain the desired data, then a main [[Memory]] access is required, and a larger miss penalty is incurred

The existence of a second-level [[Cache]] changes our [[Cache]] design strategy:
- Now the primary [[Cache]] focuses on minimizing hit time to yield a shorter clock cycle or fewer pipeline stages
	- Primary [[Cache]] size is usually smaller than in single-[[Cache]] design
	- May use smaller block size 
- The secondary [[Cache]] focuses on reducing miss-rate to reduce the penalty of long [[Memory]]-access times
	- Will be much larger than a single-level [[Cache]] (since access time of second-level is less critical)
	- Uses larger block size than would be appropriate with a single-level [[Cache]]
	- Often uses higher associativity than the primary [[Cache]] (given the focus on reducing miss rates)