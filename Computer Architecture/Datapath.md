Performs arithmetic operations.
![[better_datapath_diagram.png]]
- [[Control]] lines are shown in color
- PC does not require a write [[Control]] because it is written at the end of every clock cycle
	- Branch [[Control]] logic determines whether it is written with the incremented PC or the branch target address