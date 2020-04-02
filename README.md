# jlox

An implementation of lox in java, following [Bob Nystrom's guide to crafting
interpreters](https://craftinginterpreters.com/).

## Lox

The Lox class runs the lox file passed in, or opens a repl to run code line by
line. It handles error reporting (line and error message).

## Scanner

The Scanner class scans source code and identifies tokens. At the moment it
prints the token objects to stdout.
