# README for a parser for a BASIC-like programming language

This is a parser for a BASIC-like programming language written in Flex and Bison. The parser defines the syntax and semantics of the programming language and detects if any error in syntax.

## Requirements

- Flex (version 2.5.35 or higher)
- Bison (version 3.0.2 or higher)
- C compiler (GCC or Clang)

## Usage

To build and run the parser, execute the following commands:

```bash
flex BMM_Scanner.l
yacc -d BMM_Parser.y -ll
gcc lex.yy.c y.tab.c -o parser
./parser < CorrectSample.bmm
```

Replace `input.bas` with the path to the input source file.

The program outputs the correct tokens it parses until an error due to a BNF rule violation. No syntax error for succesful execution.

## Language syntax

The language syntax is defined in the Bison file `BMM_Parser.y`. The following is a brief overview of the syntax:

- Statements are separated by newline characters.
- The language has a set of reserved keywords, such as `IF`, `THEN`, `FOR`, `NEXT`, `LET`, `PRINT`, etc.
- Variables can be of type `INT_ID`, `SINGLE_PRE_ID`, `DOUBLE_PRE_ID`, `STRING_ID`, or `CHAR`.
- Arrays can be accessed using the `CHAR` keyword followed by an array variable and an optional comma-separated list of indices.
- Expressions can be arithmetic, relational, logical, or string expressions.
- The `INPUT` statement reads user input into variables.
- The `PRINT` statement prints values to the console.
- The `LET` statement assigns values to variables.

## License

This software is licensed under the MIT License. See the LICENSE file for more information.

## Authors
- Alankrit Kadian (2021CSB1065)
- Nakul R. Alawadhi (2021CSB1111)
