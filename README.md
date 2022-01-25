# Register machine

An implementation of the register machine introduced in Lecture 2 of the Cambridge CST IB Computation Theory course.

## Usage
`python3 machine.py input_file.reg`

## Input file structure
The first line needs to be an initial configuration (as used in the lecture course). This is a tuple whose 0th element is the first instruction, and subsequent elements are initial register values.

All parsed lines after this are instructions. Instructions start with a label (which can be any integer value but should probably be a natural number), followed by a colon (`:`), and then the instruction.

### Instructions

The possible instructions are:
- `halt`: proper halt
- `inc(rx), i`: increment register `x` and then go to instruction with label `i`
- `dec(ry), i, j`: if register `y` > 0 then decrement it and go to instruction `i`, otherwise go to instruction `j`.

### Comments and blank lines
Blank lines are ignored, as are comment line starting with `#`.

## Machine output
The machine outputs every operation in the comma-separated format `Program Counter, Instruction Label, Register State`.

Set the `SHOW_TRACE` constant in `machine.py` to `False` to only see the final state after the program has terminated and not every operation along the way.

## Examples
See the `.reg` files in this repo for examples.