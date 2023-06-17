# reading-list
Some short but useful microarchitecture research papers

## Microarchitecture

[The Microarchitecture of Superscalar Processors](https://github.com/Peter-Herrmann/reading-list/files/11748113/ss_cgi.pdf) - 16

Overview of superscalar microprocessor architecture, as it was in the mid 1990's. Introduces branch prediciton/speculative execution, superscalar hazards, register renaming, microperation tuple issuing/dispatch, superscalar memory operations, speculative states, checkpoints, and commitment. Hardware out-of-order execution is mentioned briefly including reservation stations and out-of-order memory operations, but it is not explored in depth; instead, compiler optomizations that re-order instructions to optimize parallel execution in a superscalar architecture are explored. The last 5 pages explore specific early 1990's microprocessor implementations and speculations about future (late 1990's) trends.

[Complexity-Effective Superscalar Processors](https://github.com/Peter-Herrmann/reading-list/files/11748112/isca.complexity.pdf) - 13

This paper looks at optimizing the tradeoff between instructions per cycle (IPC) and maximum frequency in superscalar microprocessor design. It specifically looks at the complexity tradeoff in register renaming logic, wakeup (windowing) logic, selection (issuing) logic, and bypass (forwarding) logic. The paper explores implementations on various process nodes down to 180nm, simulating the architectures in SPICE for quantitative results. The analysis suggests that issue width, window size, and bypassing logic are the most critical design parameters for optimizing performance. The paper the proposes the dependence-based microarchitecture, which detects dependent chains of instructions and steers these depent instructions into separate FIFOs that are constrained to execute in-order, optimizing bypass and selection logic to significantly increase the maximum frequency with a minor IPC hit.

[Trace Cache: a Low Latency Approach to High Bandwidth Instruction Fetching](https://github.com/Peter-Herrmann/reading-list/files/11748107/micro.trace-cache.pdf) - 12

This paper introduces a type of instruction memory cache that caches dynamic traces of instrucitons from non-contiguous memory locations (following branch targets) and presenting them to the decoder as if they were contiguous. With contiguous traces presented to the decoder in a fetch block, then if the branch prediciton was correct, there is no fetch break as seen by the decoder, even if a fetch block contains flow control instructions. The trace cache is implemented in parallel to a normal instruction cache. The trace cache, in a way, implements the [superblock compilation strategy](https://github.com/Peter-Herrmann/reading-list/files/11750061/hwu_jsuper93.pdf) in hardware, mapping commonly run sequences of code into a contiguous block.

[On Pipelining Dynamic Instruction Scheduling Logic](https://github.com/Peter-Herrmann/reading-list/files/11748110/stark.pdf) - 10

This paper introduces the idea of speculative wakeup in a dynamic instruction (out-of-order) scheduler. This solves the problem that selecting and waking up instructions that are dependent on presently executing instructions is an atomic operation, and a costly one at that. Instead of pipelining the logic (forcing a delay between all dependent instrucitons waking up) or not pipelining the logic (lkimiting the maximum frequency), the authors propose pipelining the logic and adding speculative wakeup to guess when an instruction will be ready. If the instruction turned out to not be ready, the instruction can be later discarded. This method allows for a significant IPC gain with no frequency penalty for out-of-order architectures that pipeline the scheduling logic, and offers a way to break up a logic path that can otherwise be the limiting factor for processors that do not pipeline the scheduling logic with a minimal IPC sacrifice. **I chose this paper because it offers the best introduction to the implementation details of an out-of-order superscalar processor**, independently of the speculative wakeup concept.

## Security

[Meltdown: Reading Kernel Memory from User Space](https://github.com/Peter-Herrmann/reading-list/files/11748108/meltdown.pdf) - 18

[Spectre Attacks: Exploiting Speculative Execution](https://github.com/Peter-Herrmann/reading-list/files/11748109/spectre.pdf) - 19

## Software

[code.positioning.pdf](https://github.com/Peter-Herrmann/reading-list/files/11749980/code.positioning.pdf)
