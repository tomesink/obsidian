---
up: 
tags:
  - embedded
---
The T-Bit is a status flag in the Current Program Status Register (CPSR)
of ARM processors.
It indicates the current instruction set state:

-   0 (Cleared): Processor is in ARM state (default).
-   1 (Set): Processor is in Thumb state.

**ARM vs. Thumb State**

**ARM State:**

-   Offers a wider range of instructions for complex operations.
-   Instructions are 32-bit sized, potentially leading to faster
    execution.
-   Requires more memory space to store code.

**Thumb State:**

-   Designed for memory-constrained environments.
-   Uses a subset of ARM instructions encoded in 16-bit or 32-bit
    formats.
-   More compact but may have slightly slower execution due to fewer
    instructions.

**ARM and Thumb Instruction Set Architectures (ISAs)**

**ARM ISA:** The full-fledged instruction set architecture for ARM
processors, providing a comprehensive set of instructions for various
tasks.

**Thumb ISA:** A sub-set of the ARM ISA with a focus on code size
efficiency. It offers a subset of ARM instructions in a more compact
16-bit or 32-bit format.

**Relationship Between T-Bit, ARM, and Thumb**

-   The T-Bit reflects the current execution state: ARM (T-Bit=0) or Thumb (T-Bit=1).
-   Programs can switch between ARM and Thumb states to optimize for
    performance or memory usage. Special instructions or conditions can
    trigger this switch.

**Additional Notes**

-   While the T-Bit can be manipulated in software, it's generally not
    recommended to write to it directly as improper state changes could
    lead to unpredictable behavior.
-   Modern ARM processors often support a combined instruction set called
    Thumb-2, which extends Thumb with additional capabilities closer to
    ARM.