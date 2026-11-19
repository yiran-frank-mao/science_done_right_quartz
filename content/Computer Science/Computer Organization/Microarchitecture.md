**Fact** There can be many implementations of the same (Instruction Set Architecture)ISA
![ISA|350](https://i.imgur.com/SRjNQwL.png)

## **Process Instruction**

**Def**  <i><u>Processing an Instruction</u></i> 
Processing an instruction is to transforming state AS to state AS’ according to the ISA specification of the instruction, where ISA specifies abstractly what AS’ should be, given an instruction and AS(i.e. transition function in an abstract [finite state machine](https://www.notion.so/Finite-State-Machine-FSM-dda9888a629641bdab08f874cfbc7143?pvs=21)), and the microarchitecture implements how AS is transformed to AS’. For example, it can transform AS to AS’ in a single clock cycle, or take multiple clock cycles to transform AS to AS’.

**Fact**  Almost every high-performance computer processes instructions out of order (OOO). In-program-order instruction processing (execution) is an illusion

**Fact** Stages in “Instruction Processing”:
1. Fetch
2. Decode/RF-Read
3. Execute
4. Memory Access
5. Writeback
![IP|400](https://i.imgur.com/GDfds0k.png)
<u><b>e.g.</b></u> For the ARM assembly code `LDR R2, [R0, #40]`, the processing would be:
1. Fetch the instruction(envolv reading `PC`)
2. Decode the instruction and RF-Read `R0` and `#40`
3. Execute `R0 + #40`
4. Memory access, retriving the value in memory address `R0+#40`
5. Write back to `R2`
<u><b>e.g.</b></u> For the ARM assembly code `AND R5, R12, R13`, the processing would be:
1. Fetch the instruction(envolv reading `PC`)
2. Decode the instruction and RF-Read `R12` and `R13`
3. Execute `R12 & R13`
4. Memory access, retriving the value in memory address `R12 & R13`
5. Write back to `R5`

**Def**  <i><u>Single-cycle machines</u></i> is the machine such that:
- Each instruction takes a single clock cycle
- All state updates made at the end of an instruction’s execution
- Big disadvantage: The slowest instruction determines cycle time

**Def**  <i><u>Multi-cycle machine</u></i> is the machine such that:
- Instruction processing broken into multiple cycles/stages
- State updates can be made during an instruction’s execution
- Architectural state updates made at the end of an instruction’s execution
- Advantage over single-cycle: The slowest “stage” determines cycle time

## Instruction Processing Engine

**Fact**  An instruction processing engine consists of two components, datapath and control logic

**Def** <i><u>Datapath</u></i>
Datapath consists of hardware elements that deal with and transform data signals.
- Functional units that operate on data
- Hardware structures (e.g., wires, muxes, decoders, tri-state bufs) that enable the flow of data into the functional units and registers
- Storage units that store data (e.g., registers)

**Def**  <i><u>Control Logic</u></i> 
Control logic consists of hardware elements that determine control signals, i.e., signals that specify what the datapath elements should do to the data.

## Pipelined Microarchitecture

**Def**  <i><u>Pipelined Microarchitecture</u></i> 
Pipelined Microarchitecture has following properties:
- Multiple instructions (up to 5) can be in the pipeline in any cycle
- Each instruction can be in a different stage(i.e. maximize utilization of hardware resources)
- Stages must be isolated from one another using pipelined register(non-arch. registers), referred to as “PPR”
- The work of a stage should be preserved in a PPR each cycle
- PPR acts as a source of data the next stage needs in a subsequent cycle

**Prop** Instruction latency with pipelining:
- Pipelining does not help to reduce the latency of a single instruction.
    - Latency of a single instruction increases as sequencing overhead of pipeline registers and clock cycle time is decided by slowest pipeline stage
- Pipelining helps increase the throughput of an entire workload as long as number of instructions is sufficiently large

**Def**  <i><u>Timing Diagrams</u></i>
To visualize the execution of many instructions in a pipeline we can use where time is on the horizontal axis, instructions are on the vertical axis. ![cycle|400](https://i.imgur.com/JMmeKnw.png)

### Balanced Pipeline

### Pipeline Hazards

**Fact** When multiple instructions are handled concurrently there is a danger of hazard.
- Structural hazard
    - When two instructions want to use the same resource
    - Memory for instructions (F) and data (M)
    - Register file is accessed in two different stages
- Data hazard
    - When a dependent instruction wants the result of an earlier instruction
- Control hazard
    - When a PC-changing instruction is in the pipeline

**Def**  <i><u>Data Dependency</u></i>
Data dependency in computer science is a situation in which a program statement (instruction) refers to the data of a preceding statement. There are three types of data dependencies: true, anti, and output.
- _True dependence_ (also known as flow dependence or read-after-write) occurs when an instruction depends on the result of a previous instruction. For example, `B = A + 1` is truly dependent on `A = 3`.
- _Anti-dependence_ (also known as False-dependence or write-after-read) occurs when an instruction requires a value that is later updated. For example, `A = B + 1` is anti-dependent on `B = 7`.
- _Output dependence_ (also known as write-after-write) occurs when both instructions write the same memory location. For example, `A = 3` and `A = 4` are output dependent.

### Solutions to Pipeline Hazards

>[!example] Summary
>
>||Read-after-Write Hazards|Load-Use Hazards|Control Hazards|
>|---|---|---|---|
>|Software Interlocking|✅|✅|✅|
>|Forwarding or Bypassing|✅|||
>|Stall||✅|✅|
>|Branch Prediction|||✅|

**Def**  <i><u>Software Interlocking</u></i> 
Software interlocking is a solution to pipeline hazards such that insert `NOPS` in code at compile time.

**Prop** Software Interlocking solution has two main weaknesses:
- Programming is complicated
- Speed is degraded

**Def**  <i><u>Forwarding</u></i> and <i><u>Bypassing</u></i> 
Forwarding or bypassing is a solution to read-after-write hazards that needs extra hardware to send the result from the Memory or Writeback stage to a dependent instruction in the Execute stage. i.e. We can bypass the register file and get results early from pipeline register.
Concretely, it checks if register read in EX stage matches register written in MEM or WB stage, if so, it will forward the result.
![fb|500](https://i.imgur.com/GTluoBR.png)

**Def**  <i><u>Stall </u></i>
Stall is a solution for Load-Use Hazards such that stall the dependent instruction in Decode stage. Stalling a stage requires disabling the pipeline register, so that the contents do not change. Stalls degrade performance so must be used only when needed.
![stall|500](https://i.imgur.com/mHVFqjk.png)

**Def**  <i><u>Bubble</u></i>
The used stage propagating through the pipeline is called a bubble.
![bubble|500](https://i.imgur.com/mHVFqjk.png)

**Def**  <i><u>Control Hazards</u></i>
Control hazards are due to changes to sequential control flow.
- Branch (`B`) instructions
- Writes to `PC` (`R15`) by regular instructions

**Prop**  Stall the pipeline on a branch instruction can resolve control hazards.
- Instruction is fetched in the first stage
- Branch is resolved in the last (fifth) stage
- Four stall cycles is a very high penalty for a branch

**Def**  <i><u>Branch Prediction</u></i>
Branch prediction is a solution exclusively for control hazards.
- If the outcome is correct, continue execution (zero penalty)
- If the outcome is wrong (branch misprediction), clean up the pipeline, and restart from the correct target instruction