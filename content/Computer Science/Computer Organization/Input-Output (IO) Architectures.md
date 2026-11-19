## Device Visibility

**Def** <i><u>Port-Mapped I/O (PMIO)</u></i>
The device is accessible in a dedicated address space, separate from the address space of memory. I/O devices have a separate address space from general memory, typically accomplished by extra "I/O" pins on the CPU's physical interface. Because the address space for I/O is isolated from that for main memory, this is sometimes referred to as isolated I/O.

**Def** <i><u>Memory-Mapped I/O (MMIO)</u></i>
I/O devices and memory share the same address space. Each I/O device has its own reserved block of memory. Data transfers to and from the I/O device involve moving bytes to and from the memory address that is mapped to the device. MMIO is like using regular load/store instructions from the programmer’s perspective.

## Reading Data

**Def** <i><u>Programmed I/O</u></i>
Each data item transfer is initiated by an instruction in the program, involving the CPU for every transaction. The term can refer to either memory-mapped I/O (MMIO) or port-mapped I/O (PMIO). However, since CPU is much faster than the I/O device, for large data transfers (for example, reading a video file from disk), we would like to free up the CPU to do other things while transfer happens in parallel.

**Def** <i><u>Direct-Memory Access (DMA)</u></i>
CPU offloads the execution of tedious I/O instructions to a dedicated chip called DMA controller, where CPU provides the DMA controller with
- The location of the bytes to be transferred
- The number of bytes to be transferred
- The destination memory address
And DMA controller will place the data in memory and interrupts the CPU.
![DMA|600](https://i.imgur.com/SI9IFWs.png)

## Event Notification

**Def** <i><u>Polled I/O</u></i>
CPU monitors a control/status register associated with a port. When a byte arrives in the port, a bit in the control register is set. The CPU eventually polls and notices that the “data ready” control bit is set. The CPU resets the control bit, retrieves the byte, and processes it. Finally, the CPU resumes polling the register as before.

**Def** <i><u>Interrupt-driven I/O</u></i>
CPU is not held up from doing other things. Interrupts are asynchronous signals, the devices tell the CPU when they have data to send. The CPU proceeds with other tasks until a device requesting service sends an interrupt to the CPU.
Concretely, communication between many interrupt-enabled devices and CPU is handled via an interrupt controller. Once the circuit recognizes an interrupt signal from any device, it raises a single interrupt signal that activates a control line on the system bus. Control line feeds directly into a pin on the CPU chip.

## I/O Devices

**Def** <i><u>Character I/O devices</u></i> process one byte (or character) at a time.
e.g. Modems, keyboards, and mice

**Def** <i><u>Block I/O devices</u></i> handle bytes in groups
e.g. Most mass storage devices (disk and tape)

**Prop** Block I/O systems are most efficiently connected through interrupt-driven DMA.

**Def** <i><u>Device driver</u></i> is the software that handles the details of I/O transfer granularity and I/O-related instructions in general

## Bus Technology

**Def**  <i><u>Bus</u></i>
Bus is a collection of wires to transfer signals (address, data, control) between sender and receiver. It can do serial transmissions(i.e. one bit at a time) or parallel transmissions(i.e. multiple bits in parallel)

## Amdahl’s Law

**Thrm** <i><u>Amdahl’s Law</u></i>
The overall performance of a system is a result of the interaction of all of its components. And system performance is most effectively improved when the performance of the most heavily used components is improved.$$ S = \frac{1}{(1-f) + (\frac{f}{k})} $$Where $S$ is the overall speedup; $f$ is the fraction of work performed by a faster component; and $k$ is the speedup of the faster component.
<u><b>e.g.</b></u> On a large system, programs spend 70% of their time running in the CPU and 30% of their time waiting for disk service. Suppose we can upgrade a CPU to make it 50% faster for &dollar;10,000 or upgrade its disk drives for &dollar;7,000 to make them 150% faster. An upgrade of which component would offer the greater benefit for the lesser cost?$$\begin{aligned}S_{\text{CPU}} = \frac{1}{(1-0.7)+(0.7/0.5)} = 1.30 \\ S_{\text{Disk}} = \frac{1}{(1-0.3) + (0.3/2.5)}=1.22 \end{aligned}$$Each 1% of improvement for the processor costs $333, and for the disk a 1% improvement costs $318. Hence an upgrade of disk would offer the greater benefit for the lesser cost.


