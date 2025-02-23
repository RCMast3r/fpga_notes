## questions / answers: 

- what is a dsp? -> dsp is just a piece of the FPGA itself that handles computation? from notes "DSP: Built-in components for fast arithmetic operation optimized for DSP applications"

- what does BRAM stand for? and how does it differ from DRAM? -> I believe that BRAM is the onboard RAM blocks within the FPGA that can be accessed a lot faster than DRAM which is on the host side. BRAM: Block RAM (Block Random Access Memory) DRAM is off of the chip but does not take up any LUTs vs BRAM does take up LUTs.

- what is the host vs what is the test bench? -> host is the thing running the code vs the test bench is the code being run "on target" in a simulation environment

- what is SIMD? Single Instruction, Multiple Data meaning that we can handle multiple multiplication / add / subtract ops in one clock cycle in certain situations

## optimization techniques:

- copying data to BRAM / moving data around
- loop unrolling 
- pipelining

## the problem:
[background paper on attention computation](https://arxiv.org/pdf/1706.03762v7)
```cpp
#define B   32      // Batch size
#define N   100     // Sequence length
#define dk  128     // Key/Query dimension
#define dv  128     // Value dimension
```

the attention matrix is is a tensor of size 100x100x32.

Q and K are in tensors with the size 100 x 100 x 128


### the default impl cycle estimation

1. (a) 2x(B * N * N * dk) + (b)(B * N * N)
- (a) is from the sum and multiplication operation being done at dk times for each ith column of Q and jth column of K for the dot product calculation 
- (b) is from the multiplication of the result of the dot product along every jth row of the attention tensor at each ith column in each bth batch

2. 

