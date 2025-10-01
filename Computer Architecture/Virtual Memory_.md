The main [[Memory]] can act as a "[[Cache]]" for secondary storage, which is called **[[Virtual Memory]]**. The benefits are:
1. Allows efficient and safe sharing of [[Memory]] among several programs
	1. Like the [[Memory]] needed by multiple virtual machines for cloud computing
	2. Most important reason for [[Virtual Memory]] in the modern day
2. Remove the programming burdens of a small, limited amount of [[Memory]]

To allow multiple virtual machines to share the same [[Memory]], we must be able to protect the virtual machines from each other.
- Ensure a program can just read and write the portions of main [[Memory]] that have been assigned to it

[[Virtual Memory]] only needs to contain the *active portions* of many virtual machines
- Just as [[Cache]] contains only the active portion of one program
- Therefore **the principle of locality enables virtual machines** as well as caches

We cannot know which virtual machines will share [[Memory]] with other virtual machines when we compile them, and those virtual machines change dynamically while they are running, so we compile each program into its own *address space*: a separate range of [[Memory]] locations accessible to only this program.
- [[Virtual Memory]] implements the translation of a program's address space to **physical addresses**
- This translation enforces **protection** of a program's address space from other virtual machines

We also use [[Virtual Memory]] to manage between different hierarchies of [[Memory]] -- main [[Memory]] (called **physical [[Memory]]**) and secondary storge. Same functions as [[Cache]], different terminology:
- [[Virtual Memory]] block is called a **page**
- [[Virtual Memory]] miss is called a **page fault**
- The [[Processor]] produces a **virtual address** which is translated by a combination of hardware and software to a **physical address** that can be used to access main [[Memory]]
	- This process is called *address mapping* or **address translation**
- Simplifies loading the program for execution by providing *relocation*
	- Maps the virtual addresses used by a program to different physical addresses before the addresses are used to access [[Memory]]
	- Allows us to load the program anywhere in main [[Memory]]
		- We don't need continuous blocks in main [[Memory]] anymore, just continuous blocks in [[Virtual Memory]]
![[address_mapping_diagram.png]]
![[address_translation_diagram.png]]

A page fault to disk will take millions of clock cycles to process, leading to several key decisions in designing [[Virtual Memory]] systems:
1. Pages should be large enough to compensate over time the high access time. Sizes from 4 KiB to 64 KiB are typical
2. Organizations that reduce page fault rate are attractive, typically fully associative placement
3. Page faults can be handled in software
4. Write through *will not work* for [[Virtual Memory]] because writes take too long. Instead, [[Virtual Memory]] systems use write-back.

## Placing a Page and Finding it Again
- We use fully associative placement to allow for clever optimizations involving placements and removal
	- The harm with fully associative placement is locating a word (page) in [[Cache]], so we solve with **[[Page Table]]**s 
- **[[Page Table]]** is a table that indexes the main [[Memory]] (and resides in main [[Memory]])
	- indexed by the page number from the virtual address to discover the corresponding physical page number
	- Each program has its own [[Page Table]]
		- maps the virtual address space of that program to main [[Memory]]
	- Hardware includes a *[[Page Table]] register* that points to the start of the [[Page Table]] in [[Memory]]
	- Contains a mapping for every possible virtual page, so no tag field is required
	- Index is full block address (the virtual page number)
![[virtual_page_table.png]]

## Page Faults
If the valid bit for a virtual page is off, a page fault occurs. The operating system is transferred [[Control]], which is done with the *exception mechanism*.
- Once [[Control]] is transferred to the operating system, it must find the page in the next level of hierarchy and decide where to place the page is main [[Memory]]
- Virtual address alone does not tell us where the page is in secondary [[Memory]]
	- We must keep track of the location is secondary [[Memory]] of each page in virtual address space
- Because we do not know ahead of time when a page in [[Memory]] will be replaced, the operating system creates the space on flash [[Memory]] or disk called the **swap space**
	- Creates a data structure to record where each virtual page is stored on disk
	- This data structure may be part of the [[Page Table]] or may be an auxiliary data structure indexed the same way as the [[Page Table]]:
		- ![[auxiliary_data_structure.png]]
	- The operating system also creates a data structure that tracks which processes and which virtual addresses use each physical page
		- When a page fault occurs, if all the pages in main [[Memory]] are in use, the operating system must choose a page to replace, usually LRU
		- The replaced pages are written to swap space in secondary [[Memory]]

## Translation Lookaside Buffer (TLB)
- Since page tables are stored in main [[Memory]], [[Memory]] access can take twice as long:
	- One [[Memory]] access to obtain the physical address
	- One [[Memory]] access to get the data
- We improve performance by relying on locality of reference to the [[Page Table]]
	- When a translation for a virtual page is used, it will probably be needed again soon, because the references to the [[words]] on that page have both temporal and spatial locality
- We use a special [[Cache]] for keeping track of recently used translations called the **translation lookaside buffer** (TLB). 
![[translation_lookaside_buffer.png]]
- TLB holds a portion of the virtual page number
- Each entry to the TLB holds a physical page number
- Because we access the TLB instead of the [[Page Table]] on every reference, the TLB will need to include other status bits, such as the dirty and the reference bit
	- dirty bit means the [[Page Table]] has been updated but the changes have not been written to the disk yet