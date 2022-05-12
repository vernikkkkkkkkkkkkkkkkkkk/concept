## Коды операций Попугай
коды операций попугай (eng: opcodes parrot)
## Определение 
Коды операций записываются с использованием особого синтаксиса, представляющего собой смесь C и специальных ключевых слов.
Коды операций преобразуются компилятором кодов операций tools/dev/ops2c.plв форматы, необходимые для различных ядер выполнения.
Все основные коды операций для Parrot определены src/ops/в файлах с *.opsрасширением. 

## Примечание
Опкоды делятся на разные файлы в зависимости от их назначения:

| Ops file         | Purpose                                                                                                                                                               |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| bit.ops          | bitwise logical operations                                                                                                                                            |
| cmp.ops          | comparison operations                                                                                                                                                 |
| core.ops         | Basic Parrot operations, private internal operations, control flow, concurrency, events and exceptions.                                                               |
| debug.ops        | ops for debugging Parrot and HLL programs.                                                                                                                            |
| experimental.ops | ops which are being tested, and which might not be stable. Do not rely on these ops.                                                                                  |
| io.ops           | ops to handle input and output to files and the terminal.                                                                                                             |
| math.ops         | mathematical operations                                                                                                                                               |
| object.ops       | ops to deal with object-oriented details                                                                                                                              |
| obscure.ops      | ops for obscure and specialized trigonometric functions                                                                                                               |
| pic.ops          | private opcodes for the polymorphic inline cache. Do not use these.                                                                                                   |
| pmc.ops          | Opcodes for dealing with PMCs, creating PMCs. Common operations for dealing with array-like PMCs (push, pop, shift, unshift) and hash-like PMCs                       |
| set.ops          | ops to set and load registers                                                                                                                                         |
| stm.ops          | Ops for software transactional memory, the inter-thread communication system for Parrot. In practice, these ops are not used, use the STMRef and STMVar PMCs instead. |
| string.ops       | Ops for working with strings                                                                                                                                          |
| sys.ops          | Operations to interact with the underlying system                                                                                                                     |
| var.ops          | ops to deal with lexical and global variables                                                                                                                         |


## Расширенные параметры
Список квалификаторов направления:

| direction | meaning                                       | example                                                                                                                                                                                                                                                      |
|-----------|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| in        | The parameter is an input                     | op my_op(in INT)                                                                                                                                                                                                                                             |
| out       | The parameter is an output                    | op pi(out NUM) {   $1 = 3.14; }                                                                                                                                                                                                                              |
| inout     | The parameter is an input and an output:      | op increment(inout INT) {  $1 = $1 + 1; } \|- \| inconst \|\| The input parameter is constant, it is not modified \| <pre> op double_const(out INT, inconst INT) {   $1 = $2 + $2; }  And, in PIR: $I0 = double_const 5 # numeric literal "5" is a constant  |
| invar     | The input parameter is a variable, like a PMC | op my_op(invar PMC)                                                                                                                                                                                                                                          |

## Тип аргумента

| type   | meaning                     | example        |
|--------|-----------------------------|----------------|
| INT    | integer value               | 42 or $I0      |
| NUM    | floating-point value        | 3.14 or $N3    |
| STR    | string                      | "Hello" or $S4 |
| PMC    | PMC variable                | $P0            |
| KEY    | Hash key                    | ["name"]       |
| INTKEY | Integer index               | [5]            |
| LABEL  | location in code to jump to | jump_here:     |


## Связь с другими понятиями

[попугай](parrot.md)
