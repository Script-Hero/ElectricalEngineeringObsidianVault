Instruction $n+1$ can be started before instruction $n$ is done executing, as long as instruction $n+1$ is at least one stage in front of instruction $n+1$
![[two_instructions_pipeline.png]]
![[two_instruction_pipeline_alt.png]]
![[space_time_diagram.png]]

The speedup from increasing the pipeline depth has *diminishing returns*
![[pipeline_depth_speedup.png]]
- Where the x-axis is the number of stages **in the EX portion of the floating-point pipeline**
- A single-stage pipeline corresponds to 32 levels of logic 