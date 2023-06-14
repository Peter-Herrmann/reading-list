# reading-list
A semi-organized research paper reading list for a computer architecture research group

[The Microarchitecture of Superscalar Processors](https://github.com/Peter-Herrmann/reading-list/files/11748113/ss_cgi.pdf) - 16

Overview of superscalar microprocessor architecture, as it was in the mid 1990's. Introduces branch prediciton/speculative execution, superscalar hazards, register renaming, microperation tuple issuing/dispatch, superscalar memory operations, speculative states, checkpoints, and commitment. Hardware out-of-order execution is mentioned briefly including reservation stations and out-of-order memory operations, but it is not explored in depth; instead, compiler optomizations that re-order instructions to optimize parallel execution in a superscalar architecture are explored. The last 5 pages explore specific early 1990's microprocessor implementations and speculations about future (late 1990's) trends.

[Complexity-Effective Superscalar Processors](https://github.com/Peter-Herrmann/reading-list/files/11748112/isca.complexity.pdf) - 13

This paper looks at optimizing the tradeoff between instructions per cycle (IPC) and maximum frequency in superscalar microprocessor design. It specifically looks at the complexity tradeoff in register renaming logic, wakeup (windowing) logic, selection (issuing) logic, and bypass (forwarding) logic. The paper explores implementations on various process nodes down to 180nm, simulating the architectures in SPICE for quantitative results. The analysis suggests that issue width, window size, and bypassing logic are the most critical design parameters for optimizing performance. The paper the proposes the dependence-based microarchitecture, which detects dependent chains of instructions and steers these depent instructions into separate FIFOs that are constrained to execute in-order, optimizing bypass and selection logic to significantly increase the maximum frequency with a minor IPC hit.

[Trace Cache: a Low Latency Approach to High Bandwidth Instruction Fetching](https://github.com/Peter-Herrmann/reading-list/files/11748107/micro.trace-cache.pdf) - 12

[On Pipelining Dynamic Instruction Scheduling Logic](https://github.com/Peter-Herrmann/reading-list/files/11748110/stark.pdf) - 10

[Meltdown: Reading Kernel Memory from User Space](https://github.com/Peter-Herrmann/reading-list/files/11748108/meltdown.pdf) - 18

[Spectre Attacks: Exploiting Speculative Execution](https://github.com/Peter-Herrmann/reading-list/files/11748109/spectre.pdf) - 19
