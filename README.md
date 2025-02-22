# Assembly Compiler

This project implements a simple **compiler** that converts a high-level programming language into **x86-64 assembly**. The project consists of several core components, including a custom **ArenaAllocator** for memory management, a **Parser** that converts source code into an Abstract Syntax Tree (AST), and a **Generator** that translates the AST into assembly code.

## Features

- **Arena-based Memory Allocation**: Efficient memory allocation using an arena allocator.
- **AST Parsing**: Parses source code into an Abstract Syntax Tree (AST).
- **Assembly Code Generation**: Generates x86-64 assembly code from the parsed AST.
- **Support for Basic Constructs**: Supports basic expressions, variable declarations, assignments, if statements, and more.
- **Control Flow**: Supports conditional control flow with `if` and `else` branches.
  
---

## Components

### 1. **ArenaAllocator**
The `ArenaAllocator` is a custom memory allocator designed to manage a large block of memory efficiently. It provides fast memory allocation with low overhead and supports object construction via `emplace`.

- Allocates a contiguous block of memory for use by the compiler.
- Memory is allocated in chunks and does not require individual deallocation.
- Memory leaks are possible due to the absence of destructors (intended for performance).

### 2. **Parser**
The **Parser** converts the source code into an **Abstract Syntax Tree (AST)**. It handles:
- Lexical analysis (tokenization).
- Syntax parsing (creating a tree structure from the source code).

The parsed AST forms the basis for the compiler’s next steps (i.e., code generation).

### 3. **Generator**
The **Generator** takes the parsed AST and generates **x86-64 assembly code**. It includes:
- A mechanism for handling expressions (binary and terminal).
- Support for generating assembly for variables, expressions, and statements.
- Implementation of conditional structures like `if` and `else`.

The generator produces assembly instructions that can be directly assembled into machine code.

---

## Installation

Follow these steps to install and run the compiler:

### 1. Clone the repository:

```bash
git clone https://github.com/your-username/compiler.git
cd compiler
