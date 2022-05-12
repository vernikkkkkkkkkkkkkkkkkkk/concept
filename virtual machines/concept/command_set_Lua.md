## Набор команд Lua
набор команд "lua" (eng:command set lua)

## Примечание
Инструкции [байт-кода](byte-code.md) [Lua](liaVM.md) имеют размер 32 бита. Все инструкции имеют код операции в первых 6 битах. 

Инструкции могут иметь следующие поля:

'A' : 8 bits

'B' : 9 bits

'C' : 9 bits

'Ax' : 26 bits ('A', 'B', and 'C' together)

'Bx' : 18 bits ('B' and 'C' together)

'sBx' : signed Bx

## Набор инструкций/команд
R(A)

Register A (specified in instruction field A)

R(B)

Register B (specified in instruction field B)

R(C)

Register C (specified in instruction field C)

PC

Program Counter

Kst(n)

Element n in the constant list

Upvalue[n]

Name of upvalue with index n

Gbl[sym]

Global variable indexed by symbol sym

RK(B)

Register B or a constant index

RK(C)

Register C or a constant index

sBx

Signed displacement (in field sBx) for all kinds of jumps

## Opcode


| Opcode   | Description                                         |
|----------|-----------------------------------------------------|
| MOVE     | Copy a value between registers                      |
| LOADK    | Load a constant into a register                     |
| LOADKX   | Load a constant into a register                     |
| LOADBOOL | Load a boolean into a register                      |
| LOADNIL  | Load nil values into a range of registers           |
| GETUPVAL | Read an upvalue into a register                     |
| GETTABUP | Read a value from table in up-value into a register |
| GETTABLE | Read a table element into a register                |
| SETTABUP | Write a register value into table in up-value       |
| SETUPVAL | Write a register value into an upvalue              |
| SETTABLE | Write a register value into a table element         |
| NEWTABLE | Create a new table                                  |
| SELF     | Prepare an object method for calling                |
| ADD      | Addition operator                                   |
| SUB      | Subtraction operator                                |
| MUL      | Multiplication operator                             |
| MOD      | Modulus (remainder) operator                        |
| POW      | Exponentation operator                              |
| DIV      | Division operator                                   |
| IDIV     | Integer division operator                           |
| BAND     | Bit-wise AND operator                               |
| BOR      | Bit-wise OR operator                                |
| BXOR     | Bit-wise Exclusive OR operator                      |
| SHL      | Shift bits left                                     |
| SHR      | Shift bits right                                    |
| UNM      | Unary minus                                         |
| BNOT     | Bit-wise NOT operator                               |
| NOT      | Logical NOT operator                                |
| LEN      | Length operator                                     |
| CONCAT   | Concatenate a range of registers                    |
| JMP      | Unconditional jump                                  |
| EQ       | Equality test, with conditional jump                |
| LT       | Less than test, with conditional jump               |
| LE       | Less than or equal to test, with conditional jump   |
| TEST     | Boolean test, with conditional jump                 |
| TESTSET  | Boolean test, with conditional jump and assignment  |
| CALL     | Call a closure                                      |
| TAILCALL | Perform a tail call                                 |
| RETURN   | Return from function call                           |
| FORLOOP  | Iterate a numeric for loop                          |
| FORPREP  | Initialization for a numeric for loop               |
| TFORLOOP | Iterate a generic for loop                          |
| TFORCALL | Initialization for a generic for loop               |
| SETLIST  | Set a range of array elements for a table           |
| CLOSURE  | Create a closure of a function prototype            |
| VARARG   | Assign vararg function arguments to registers       |


## Связь с другими понятиями
[LiaVM](liaVM.md)
