The main memory can act as a "cache" for secondary storage, which is called **virtual memory**. The benefits are:
1. Allows efficient and safe sharing of memory among several programs
	1. Like the memory needed by multiple virtual machines for cloud computing
	2. Most important reason for virtual memory in the modern day
2. Remove the programming burdens of a small, limited amount of memory

To allow multiple virtual machines to share the same memory, we must be able to protect the virtual machines from each other.
- Ensure a program can just read and write the portions of main memory that have been assigned to it

Virtual Memory only needs to contain the *active portions* of many virtual machines
- Just as cache contains only the active portion of one program
- Therefore **the principle of locality enables virtual machines** as well as caches

We cannot know which virtual machines will share memory with other virtual machines when we compile them, and those virtual machines change dynamically while they are running, so we compile each program into its own *address space*: a separate range of memory locations accessible to only this program.
- Virtual Memory implements the translation of a program's address space to **physical addresses**
- This translation enforces **protection** of a program's address space from other virtual machines

We also use Virtual Memory to manage between different hierarchies of memory -- main memory (called **physical memory**) and secondary storge. Same functions as cache, different terminology:
- Virtual memory block is called a **page**
- Virtual memory miss is called a **page fault**
- The processor produces a **virtual address** which is translated by a combination of hardware and software to a **physical address** that can be used to access main memory
	- This process is called *address mapping* or **address translation**
- Simplifies loading the program for execution by providing *relocation*
	- Maps the virtual addresses used by a program to different physical addresses before the addresses are used to access memory
	- Allows us to load the program anywhere in main memory
		- We don't need continuous blocks in main memory anymore, just continuous blocks in virtual memory
![[address_mapping_diagram.png]]
![[address_translation_diagram.png]]

A page fault to disk will take millions of clock cycles to process, leading to several key decisions in designing virtual memory systems:
1. Pages should be large enough to compensate over time the high access time. Sizes from 4 KiB to 64 KiB are typical
2. Organizations that reduce page fault rate are attractive, typically fully associative placement
3. Page faults can be handled in software
4. Write through *will not work* for virtual memory because writes take too long. Instead, virtual memory systems use write-back.

## Placing a Page and Finding it Again
- We use fully associative placement to allow for clever optimizations involving placements and removal
	- The harm with fully associative placement is locating a word (page) in cache, so we solve with **page table**s 
- **Page table** is a table that indexes the main memory (and resides in main memory)
	- indexed by the page number from the virtual address to discover the corresponding physical page number
	- Each program has its own page table
		- maps the virtual address space of that program to main memory
	- Hardware includes a *page table register* that points to the start of the page table in memory
	- Contains a mapping for every possible virtual page, so no tag field is required
	- Index is full block address (the virtual page number)
![[virtual_page_table.png]]

## Page Faults
If the valid bit for a virtual page is off, a page fault occurs. The operating system is transferred control, which is done with the *exception mechanism*.
- Once control is transferred to the operating system, it must find the page in the next level of hierarchy and decide where to place the page is main memory
- Virtual address alone does not tell us where the page is in secondary memory
	- We must keep track of the location is secondary memory of each page in virtual address space
- Because we do not know ahead of time when a page in memory will be replaced, the operating system creates the space on flash memory or disk called the **swap space**
	- Creates a data structure to record where each virtual page is stored on disk
	- This data structure may be part of the page table or may be an auxiliary data structure indexed the same way as the page table:
		- ![[auxiliary_data_structure.png]]
	- The operating system also creates a data structure that tracks which processes and which virtual addresses use each physical page
		- When a page fault occurs, if all the pages in main memory are in use, the operating system must choose a page to replace, usually LRU
		- The replaced pages are written to swap space in secondary memory

## Translation Lookaside Buffer (TLB)
- Since page tables are stored in main memory, memory access can take twice as long:
	- One memory access to obtain the physical address
	- One memory access to get the data
- We improve performance by relying on locality of reference to the page table
	- When a translation for a virtual page is used, it will probably be needed again soon, because the references to the words on that page have both temporal and spatial locality
- We use a special cache for keeping track of recently used translations called the **translation lookaside buffer** (TLB). 
![[translation_lookaside_buffer.png]]
- TLB holds a portion of the virtual page number
- Each entry to the TLB holds a physical page number
- Because we access the TLB instead of the page table on every reference, the TLB will need to include other status bits, such as the dirty and the reference bit
	- dirty bit means the page table has been updated but the changes have not been written to the disk yet