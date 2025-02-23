## questions / answers: 

- what is a dsp? -> dsp is just a piece of the FPGA itself that handles computation? from notes "DSP: Built-in components for fast arithmetic operation optimized for DSP applications"

- what does BRAM stand for? and how does it differ from DRAM? -> I believe that BRAM is the onboard RAM blocks within the FPGA that can be accessed a lot faster than DRAM which is on the host side. BRAM: Block RAM (Block Random Access Memory) DRAM is off of the chip but does not take up any LUTs vs BRAM does take up LUTs.

- what is the host vs what is the test bench? -> host is the thing running the code vs the test bench is the code being run "on target" in a simulation environment

- what is SIMD? Single Instruction, Multiple Data meaning that we can handle multiple multiplication / add / subtract ops in one clock cycle in certain situations

