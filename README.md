# chibicc: A Small C Compiler

## Introduction
chibicc is yet another small C compiler that implements most C11 features. Despite being categorized as a "toy compiler," it can compile several real-world programs such as Git, SQLite, libpng, and chibicc itself, passing their corresponding test suites. It supports a wide variety of C11 features and is capable of compiling hundreds of thousands of lines of real-world C code correctly.

chibicc is developed as the reference implementation for a book currently being written about the C compiler and low-level programming.

## Repository Structure

chibicc/
├── src/
│ ├── include/
│ │ └── header files
│ ├── chibicc.h
│ ├── codegen.c
│ ├── hashmap.c
│ ├── main.c
│ ├── parse.c
│ ├── preprocess.c
│ ├── strings.c
│ ├── tokenize.c
│ ├── type.c
│ └── unicode.c
├── tests/
│ └── test files
├── .gitignore
├── LICENSE
├── Makefile
└── README.md

## Features
chibicc supports almost all mandatory features and most optional features of C11, as well as a few GCC language extensions. Some notable features include:

- Preprocessor
- float, double, and long double (x87 80-bit floating point numbers)
- Bit-fields
- alloca()
- Variable-length arrays
- Compound literals
- Thread-local variables
- Atomic variables
- Common symbols
- Designated initializers
- Various string literals
- Structs as values

chibicc does not support complex numbers, K&R-style function prototypes, or GCC-style inline assembly. Digraphs and trigraphs are intentionally left out.

## Build and Installation

### Dependencies
- `gcc` or `clang`
- `make`

### Build Instructions
1. Clone the repository:
   ```bash
   git clone https://github.com/rui314/chibicc.git
   cd chibicc
   
2. Build the project:
   ```bash
   make

3. Run the compiler:
   ```bash
   ./chibicc [options] [file...]


## Testing
To run the tests, execute:
make test

## Contributing
When a bug is found, it is essential to go back to the original commit that introduced the bug and rewrite the commit history as if the bug never existed. Therefore, pull requests are not directly merged but are used to inform the historical rewrite.

## Design Principles
chibicc's core value is simplicity and readability. Code improvements that add complexity without substantial benefit to first-time readers are avoided. Some design decisions include:

-  Using simple algorithms where n is small.
-  Allocating memory using calloc and not freeing it until the process exits.
=  Maintaining code readability even at the cost of minor inefficiencies.

# References
-  tcc: A small C compiler by Fabrice Bellard
-  lcc: A small C compiler
-  An Incremental Approach to Compiler Construction
-  Rob Pike's 5 Rules of Programming

# Contact
For more information or to report issues, please visit the GitHub repository.
