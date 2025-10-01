

![[data_hazard.png]]
- In this example, register X2 is used in all subsequent steps, but *Instruction 2* is trying to use X2 before *Instruction 1* has finished loading it. This leads to **undefined behavior**.

We can solve data hazards in a few ways.

## Without Forwarding
![[better_without_forwarding.png]]
We insert three *bubbles* to resolve the data hazard. This ends up resolving all data hazards in subsequent instructions too! 

## With Forwarding
![[with_forwarding_data_hazad.png]]
The dependencies between the pipeline [[Registers]] *move forward in time*. We can use the $\text{and}$ instruction and $\text{or}$ instruction without delaying by **forwarding the value in the pipeline register directly rather than stall**
-  We assume reading and writing can occur during the same clock cycle
	- so during CC 5, X2 is 10 at the beginning and -20 at the end 
	- $\text{add}$ does not stall but the values come from the register file instead of a pipeline register

![[with_forwarding_datapath.png]]

![[forwarding_example.png]]
- An example **where forwarding does not work** because the the dependencies between the load and the following instruction go **backwards in time**
- This is called a **load-use data hazard** which results in a **pipeline stall** and we have to solve it using bubbles:![[bubble_load_use_data_hazard.png]]

