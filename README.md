# PyParser


## Description:
Features two applications: pyparser and pyscanner. PyScanner can be used to scan a source code written in a custom grammar, check it's validity on a basic level and generate PIF(Program Internal Form) and symbol table. PyParser it's an LR0 parser.


## Usage:

### PyScanner:
```terminal
python pyscanner.py -f/--file [source_code] (use -d/--debug for debug)
```

### PyParser (when PIF is included):
Before parsing the PIF will be generated by pyscanner.
```terminal
python pyparser.py -f/--file [source_code] -g/--grammar [grammar] -pif
```

### PyParser (without PIF):
```terminal
python pyparser.py -f/--file [source_code] -g/--grammar [grammar]
```

## How it works:
### PyParser:
The program constructs an in-memory representation of the grammar, source code and states.
Using the states and the input sequence constructs the canonical collection of LR0 items.
Finally, using the input sequence applies the LR0 parsing, determines the state transitions (shift, reduce, accept),
then outputs the productions and the validity of the source code.