
## Combinational and State Elements
The Datapath consists of two different types of logic elements:
1. **Combinational**: elements that operate on data values, meaning output depends *only* on current input. An input always produces the same output.
2. **State**: elements that contain an internal state. Instructions, data memories, and registers are all state elements.
	1. Contains at least 2 inputs: the value to be written to state, and the clock signal
	2. Clock determines when element is written. *State elements can be read at any time.*


## Clocking
If a signal is written at the same time that it is read, the value of the read could be the old value, new value, or some combination of the two.

We use **edge-triggered clocking**
- All state changes occur on a clock edge

Because all **combinational** elements rely on data from **state** elements. Therefore the inputs to combinational elements are the values previously written to the state element.
![[state_combinatiaonl_clock_cycles.png]]
- We assume state changes happen on a positive edge in this book
- All signals must propagate from state element 1, through the combinational logic, and into state element 2 in the time of one clock cycle
- For simplicity, *not shown* is the **write signal**, which is a *control signal* that enables a write to go through. Without this signal, the component would write every single clock cycle (which we may not want)


Edge-trigger clocking methodology allows us to read the contents of a register, send the value through some combinational logic, and write that register in the same clock cycle. It does not matter if we choose rising-edge or falling-edge, but we have to choose 1. 

For the 64-bit LEGv8 architecture, nearly all state and logic elements have inputs and outputs that are 64 bits wide. 

