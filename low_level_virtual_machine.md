## Виртуальная машина низкого уровня
виртуальная машина низкого уровня(eng: low level virtual machine) 

## Определение
LLVM (Low Level Virtual Machine) — проект программной инфраструктуры для создания [компиляторов](compiler_1.md) и сопутствующих им утилит.
Состоит из набора [компиляторов](compiler_1.md) из языков высокого уровня, системы [оптимизации](code_optimization.md), [интерпретации](interpreter_1.md)
и [компиляции](compilation_process.md) в [машинный код](machine_code_1.md). В основе инфраструктуры используется [RISC](restricted_instruction_set_computer.md)-подобная платформонезависимая система кодирования машинных инструкций 
(байткод LLVM IR), которая представляет собой высокоуровневый ассемблер, с которым работают различные преобразования.
## Компиляция языков
В настоящее время LLVM поддерживает [компиляцию](the_process_of_compiling_and_executing_program_code.md) языков:

- Ada

- C

- C++

- D 

- Delphi

- Fortran 

- Haskell 

- Julia

- Objective-C 

- Rust

- Swift 

## Платформы
LLVM поддерживает работу на следующих платформах:

| Операционная система | Архитектура | Компилятор               |
|----------------------|-------------|--------------------------|
| Linux                | x86/AMD64   | GCC, Clang               |
| FreeBSD              | x86/AMD64   | GCC, Clang               |
| OpenBSD              | x86/AMD64   | GCC, Clang               |
| Mac OS X             | PowerPC     | GCC                      |
| Mac OS X             | x86/AMD64   | GCC, Clang               |
| Solaris              | UltraSPARC  | GCC                      |
| Cygwin/Win32         | x86         | GCC 3.4.X, Binutils 2.15 |
| MinGW/Win32          | x86         | GCC 3.4.X, Binutils 2.15 |

## Типы данных

- Простые типы

| Целые числа произвольной разрядности                                                                                                                                                                                                                                                                                                                        | iразрядность                                                                   | i1 — булево значение — 0 или 1 i32 — 32-разрядное целое i17 i256 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|------------------------------------------------------------------|
| Генерация машинного кода для типов очень большой разрядности не поддерживается. Но для промежуточного представления никаких ограничений нет. Числа считаются представленными в дополнительном коде. Различий между знаковыми и беззнаковыми целыми на уровне типов не делается: в тех случаях, когда это имеет значение, с ними работают разные инструкции. |                                                                                |                                                                  |
| Числа с плавающей точкой                                                                                                                                                                                                                                                                                                                                    | float, double, типы, специфичные для конкретной платформы (например, x86_fp80) |                                                                  |
| Пустое значение                                                                                                                                                                                                                                                                                                                                             | void                                                                           |                                                                  |
 - Производные типы

| Указатели                                                                                                                              | тип*                      | i32* — указатель на 32-разрядное целое                    |
|----------------------------------------------------------------------------------------------------------------------------------------|---------------------------|-----------------------------------------------------------|
| Массивы                                                                                                                                | [число элементов x тип]   | [10 x i32] [8 x double]                                   |
| Структуры                                                                                                                              |                           | { i32, i32, double }                                      |
| Вектор — специальный тип для упрощения SIMD-операций. Вектор состоит из 2n значений примитивного типа — целого или с плавающей точкой. | < число элементов x тип > | < 4 x float > — вектор XMM                                |
| Функции                                                                                                                                |                           | i32 (i32, i32) float ({ float, float }, { float, float }) |
## Cвязь с другими понятиями 
[набор команд llvm](command_set_llvm.md)
