# erever - EVM Reversing Tools (WIP)

Install:
```
pip install git+https://github.com/minaminao/erever.git
```

Usage:
```
$ erever -h
usage: erever [-h] [-b BYTECODE]

EVM Reversing Tools

options:
  -h, --help            show this help message and exit
  -b BYTECODE, --bytecode BYTECODE
```

## Disassemble with stack and memory tracing
Source: [A quine for the SOURCECODE challenge in Paradigm CTF 2022](https://github.com/minaminao/ctf-blockchain/blob/main/src/ParadigmCTF2022/SourceCode/Quine35Bytes.huff).

```c
$ erever -b "70806011526000526070600e536023600ef3806011526000526070600e536023600ef3"
PUSH17 0x806011526000526070600e536023600ef3
	stack	[0x806011526000526070600e536023600ef3]
	memory	
DUP1
	stack	[0x806011526000526070600e536023600ef3, 0x806011526000526070600e536023600ef3]
	memory	
PUSH1 0x11
	stack	[0x11, 0x806011526000526070600e536023600ef3, 0x806011526000526070600e536023600ef3]
	memory	
MSTORE
	stack	[0x806011526000526070600e536023600ef3]
	memory	0000000000000000000000000000000000000000000000000000000000000000806011526000526070600e536023600ef3
PUSH1 0x00
	stack	[0x00, 0x806011526000526070600e536023600ef3]
	memory	0000000000000000000000000000000000000000000000000000000000000000806011526000526070600e536023600ef3
MSTORE
	stack	[]
	memory	000000000000000000000000000000806011526000526070600e536023600ef3806011526000526070600e536023600ef3
PUSH1 0x70
	stack	[0x70]
	memory	000000000000000000000000000000806011526000526070600e536023600ef3806011526000526070600e536023600ef3
PUSH1 0x0e
	stack	[0x0e, 0x70]
	memory	000000000000000000000000000000806011526000526070600e536023600ef3806011526000526070600e536023600ef3
MSTORE8
	stack	[]
	memory	000000000000000000000000000070806011526000526070600e536023600ef3806011526000526070600e536023600ef3
PUSH1 0x23
	stack	[0x23]
	memory	000000000000000000000000000070806011526000526070600e536023600ef3806011526000526070600e536023600ef3
PUSH1 0x0e
	stack	[0x0e, 0x23]
	memory	000000000000000000000000000070806011526000526070600e536023600ef3806011526000526070600e536023600ef3
RETURN
	return	70806011526000526070600e536023600ef3806011526000526070600e536023600ef3
	stack	[]
	memory	000000000000000000000000000070806011526000526070600e536023600ef3806011526000526070600e536023600ef3
```
