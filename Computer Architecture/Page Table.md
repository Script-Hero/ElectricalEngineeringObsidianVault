
![[page_table.png]]

The page table maps each page in [[Virtual Memory]] to either a page in physical [[Memory]] or a page stored on disk, which is the next level in the hierarchy.
- The virtual page number is used to index the page table
- **If the valid bit is on, the page table supplies the physical page number** (i.e. the starting address of the page in [[Memory]]) corresponding to the virtual page
- **If the valid bit is off, the page currently resides only on disk, at a specified address**
- In many systems, the table of physical page address and disk page addresses, while logically one table, are stored in two separate data structures. 
- Data tables are justified in part because we must keep the disk addresses of all pages, even if they are currently in main [[Memory]]

# Definitions
**Page Table**:
- Resides in [[Memory]]
- Indexed with the page numbers from the virtual address
- Contains the corresponding physical page numbers

**Page fault**:
- The page *does not* reside in main [[Memory]]
- There is a **very** high cost for a page fault
- Write through is not allowed (use write back)
- LRU is adopted
- Fully associative is used