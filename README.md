# VHDL Counter Overflow Bug

This repository demonstrates a common bug in VHDL code: an integer overflow in a counter. The `buggy_counter.vhd` file contains a counter that might overflow if not handled properly.  The `fixed_counter.vhd` shows the corrected code.

## Bug Description

The `buggy_counter` entity uses an integer type for its counter.  While the range is specified (0 to 15),  there's no explicit check for rollover.  Under certain circumstances, like clock glitches or improper reset handling, the counter could increment beyond its defined range, leading to unpredictable behavior or even simulation failures.  This is a subtle bug that might not be immediately apparent during initial design and testing.

## Solution

The `fixed_counter.vhd` addresses this by ensuring the counter always stays within its defined bounds through modulo operation.   This makes the counter behavior more robust and predictable.