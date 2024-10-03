---
up: 
tags:
  - embedded
---
Based on "Advanced Bus Microcontroller Architecture" (AMBA)
specification (designed by ARM).

## Main BUS Protocols

AMBA supports several protocols:

### AHB Lite (AMBA High-Performance Bus)
  - Mainly used for the main bus Interfaces
  - High speed communication with peripherals that demand high operation
  speed.

### APB (AMBA Peripheral Bus) 
  - Used for **PPB** (Private Peripheral Bus) acces and some on-chip
    peripheral access using an AHB-APB bridge.
  - Used for low-speed communication. Most peripherals which don't
    require high operational speed are connected to this bus.



## Main BUS Interfaces

### I-BUS (I-CODE)
    - AHB interface
    - Fetches instructions and vector table from CODE memory region

### D-BUS (D-CODE) 
    - AHB
    - Data interface
    - Accesses the data from CODE memory region.


### S-BUS (System)
    - read/write acces to peripherals, device regions etc.

### PPB
    - Accesses to PPB memory region containing NVIC, System timer and
      system control block.


## AHB Bus Matrix

On chip/board implemented mutltiple (all AHB and APB buses) bus
synchronisation.