Method for solving a circuit by defining a ground node, defining the [[Current]] of each element in terms of the voltages of essential nodes relative to ground, and using simultaneous [[KCL]] equations to solve.

## Methodology
1. Identify all essential nodes (nodes with $\geq$ 3 elements connected)
2. Choose one node to be the *reference node* (usually the node with the most elements connected) and assign it a [[Voltage]] of zero
3. Assign an unknown [[Voltage]] to each other essential node ($V_1, V_2, \dots$)
	1. Basically just naming each node
4. Write [[KCL]] for each node in terms of named voltages, writing each [[Current]] as $\frac{V_a-V_b}{R}$ 
5. Solve simultaneous equations for unknown voltages

## Example
![[node_voltage_example.png]]

## Special Case (Supernode)
If a circuit has *only* a [[Voltage]] source between 2 nodes, we can't use node-[[Voltage]] method normally
- There is no resistor in between so we can't use [[Ohm's Law]]
- But there is a [[Voltage]] difference between the nodes because of the source 

![[supernode_node_voltage.png]]

There are 2 solutions:
1. You *can* get the relationship equation $V_2-V_1=V_s$ and sometimes this is enough
2. "Combine" the two nodes into a "Supernode" which allows us to write a [[KCL]] equation without knowing the [[Current]] through the $V_s$ [[Voltage]] source
![[supernode_node_voltage_cont.png]]
Yields the equation $I_1+I_2+I_3+I_4=0$
