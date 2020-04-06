# jlox

An implementation of lox in java, following [Bob Nystrom's guide to crafting
interpreters](https://craftinginterpreters.com/).

## Lox

The Lox language was designed by Bob Nystrom. It's implemented here in java.

## To run
The Lox class runs the lox file passed in, or opens a repl to run code line by
line. It handles error reporting (line and error message).

## Notes
### Scanning

The Scanner class scans source code and identifies tokens. At the moment it
prints the token objects to stdout.

## Parsing

There's a GenerateAst script to generate subclasses of expressions for the AST.
There's also an AstPrinter that groups expressions with parentheses, to
create an unambiguous string rep of the AST.

Currently working on a top-down parser for expressions...
