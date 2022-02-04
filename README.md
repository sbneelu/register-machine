# Register machine

An implementation of a register machine with three instructions: increment, decrement, and halt.

## Usage
`python3 machine.py input_file.reg`

## Input file structure
The first line needs to be an initial configuration. This is a tuple whose 0th element is the label of the first instruction, and subsequent elements are initial register values. For example, `(0, 0, 2, 4)` means the first instruction is label `0` and the registers start with the values `(r0, r1, r2) = (0, 2, 4)`.

All parsed lines after this are instructions. Instructions start with a label (which can be made up of any ASCII characters except colons and whitespace characters such as spaces and line breaks), followed by a colon (`:`), and then the instruction.

### Instructions

The possible instructions are:
- `halt`: proper halt
- `inc(rx), i`: increment register `x` and then go to instruction with label `i`
- `dec(ry), i, j`: if register `y` > 0 then decrement it and go to instruction `i`, otherwise go to instruction `j`.

### Comments and blank lines
Blank lines are ignored, as are comment lines starting with `#`.

## Machine output
The machine outputs every operation in the comma-separated format `Execution Number, Instruction Label, Register State`.

Set the `SHOW_TRACE` constant in `machine.py` to `False` to only see the final state after the program has terminated and not every operation along the way.

## Examples
See the `examples` directory in this repo for examples.
