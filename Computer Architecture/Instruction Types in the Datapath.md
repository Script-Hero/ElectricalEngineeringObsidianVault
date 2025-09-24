![[instruction_datapath_effect.png]]
- Where deasserted means the control signal is set to 0 and asserted means it is set to 1
- Note that all *state elements* also have a clock signal as an **implicit** input to control writes
	- Gating the clock externally to a state object can create timing problems


## Control Signals by Instruction Type
![[conrol_signal_by_instruction_type.png]]

## Datapath Diagrams
### R-Type
![[r_type_datapath.png]]

### Load Instructions
![[load_datapath.png]]

### Store Instructions
![[store_dataparh.png]]

### Branch Instructions
![[branch_instructions.png]]


## Specific Examples
### ADD X1, X2, X3
![[add_datapath.png]]
![[add_control_signals.png]]


## LDUR X1, \[X2, 40]
![[ldur_example.png]]
![[ldur_example_signals.png]]

## STUR X1, \[X2, 40]
![[stur_example.png]]
![[stur_example_signals.png]]

## CBZ X1, 25
![[cbz_example.png]]
![[cbz_example_signals.png]]


