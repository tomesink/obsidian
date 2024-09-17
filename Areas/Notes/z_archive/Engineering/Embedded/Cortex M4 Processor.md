---
up: 
tags:
  - embedded
URL: https://www.udemy.com/course/embedded-system-programming-on-arm-cortex-m3m4/
---
Cortex M4 is a family of ARM 32 processors.
The "F" Means Floating Point Unit.

## Operational modes

The processor runs either in **thread mode** or **handler mode**.

All application code executes under thread mode. This is also called as 
"User Mode" and this is wher the processor starts.

All exception or interrupt handlers will run under the handler 
mode.

## Access levels

### Priviledged Access Level (PAL)

If running in PAL the code has acces to all the processor specific
resources and restricted registers.

Your code is running in PAL by default. Handler mode code exectutuion is
always done with PAL.

You can switch between access levels via CONTROL register.

### Non-Priviledged Access Level (NPAL)

The code does not have access to some of the restricted registers. When
the processor is in thread mode it is possible to move processor to the
NPAL but after that it is not possible to come back ( because from NPAL
you are not able to access the CONTROL register) unless you change
to handler mode (this means you need to trigger interrupt/ system exception
which moves your code to the Handler mode). The interrupt handler than
can change the CONTROL=0. By exiting from interrupt handller you are 
exiting directly into PAL.




## Registers

### Core registers

All these registers are non-memory mapped. This means we cannot access
them via address/pointer from C. We can access them only from assembly.

NOTE: Tehre are other special registers accessible via memory (eg. 
registers for peripherals, debug etc)

**R0 - R12** (total 13) registers are for general purpose.

All the core registers are 32 bit wide.

**SP (R13)** register is for the Stack Pointer (together with PSP - Process
Stack Pointer and MSP - Main Stack Pointer, they are active depending of
the mode of the processor). MSP plays role in reset handling.

**LR (R14)** - link register. It stores return information for subroutines
function calls and exceptions. If code calls a function it performs a
`jmp` instruction in assembly. The LR stores the next instruction of the
caller code where the execution jumps back once the callee finishes its
execution.

**PC (R15)** register contains the current program address. If code calls
a function the PC stores the address of the function for the `jmp`. If
the callee function returns it sets PC = LR so the next instruction jumps
back into the caller code.

### Special registers

**PSR** Program Status Register. It holds the current program/execution 
status. It is 32 bits wide. See the datasheet for details. It combines
3 registers:

- APSR - Application Program Status Register (5 bits)
- IPSR - Interrupt Program Status Registers (0-8 bits)
- EPSR - Execution Program Status Register

The APSR receives the result flags from ALU (like negative flag, zero 
flag etc. see Nand2Tetris to understand what the flag are).

The IPSR contains the exception type number of the current Interrupt
Service Routine (ISR). It can also tell if code is being exectuted in
thread mode.

The EPSR contains the Thumb state bit and the exevution state for either
the:
- *If-Then* (IT) instruction
- *Interruptible-Continuable-Instruction* (ICI) field for an interrupted
load multiple or store multiple instruction.

**PRIMASK**, **FAULTMASK**, **BASEPRI** are exception mask registers.

**CONTROL** register allows switching between access modes.


## Reset Handling

When reset button is pressed the PC is loaded with 0x00000000. The
processor than puts this value in MSP. That means processor first
initializes the stack pointer. 

Than value @ 0x00000004 memory location is loaded into PC. This address
is actually address of the reset handler (more precisely the address of
the first instruction of the reset handler).

Reset handler is just a C or ASM function to perform necessary
initialisations and than call the main() function.

The reset handler needs to initalize:
- .data section (data segment, address space containing initialized
  static variables (global and local). The size of this segment is
  determined and does not change at run time.
- .bss section (Block Starting Symbol, and address space  contain statically allocated
  variables that are declared but not been assigned a value yet
- C std library (__libc_init_array())