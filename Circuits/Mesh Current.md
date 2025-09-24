Method for solving a circuit by writing [[KVL]] equations to find the current of each loop of the circuit by using [[Ohm's Law]] to define the voltage across each element in terms of the loop's current and the element's resistance.

## Methodology
1. Identify all meshes (loops that do not enclose any other loops) and assign each one a current variable name ($I_1,I_2,\dots$)
2. Write the voltage across all resistors in each mesh in terms of the element's resistance and the loops current, in the form $I_{Loop}R_{n}$
3. Write [[KVL]] equation for each mesh using these voltage definitions
4. Solve the simultaneous equations

## Example
![[mesh_current_example.png]]

## Supermesh
For a circuit where a current source falls in a mesh that we need to use [[KVL]] on, mesh-current can fail because we don't know the voltage across the current source.
![[mesh-current-supermesh.png]]
To solve, we "erase" the middle line with the current source, and pretend that the 2 resistors are parallel and part of a single mesh.