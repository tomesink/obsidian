---
up: 
tags:
  - embedded
---
**printf** works over SWO pin (Serial Wire Output) of SWD interface
(Serial Wire Debug)

**SWD** is a two wire protocol for accessing ARM debug interface. It has
2 pins for debug and 1 pin for trace. Alternative to JTAG (older debug
interface for older ARM7/9 family).

A physical layer of SWD consists of SWDIO (a bidirectional data line) and
SWCLK (a clock deriven by the host)

**SWO** is one more pin provided by SWD used for SIngle Wire Viewing 
(SWV) which is a low cost tracing technology. Reading from SWO pin is
not supported by all IDEs.

*ITM** - Instrumental Trace Macrocell Unit) supports printf style 
debugging and tracing. Its an optional part of a processor (not available
on M0 ARM Processors for example). It sends print fata from FIFO to
SWO pin.