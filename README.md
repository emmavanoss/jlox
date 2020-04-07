# jlox

An implementation of lox in java, following [Bob Nystrom's guide to crafting
interpreters](https://craftinginterpreters.com/).

## Lox

The lox language was designed by Bob Nystrom (see above). It's implemented here in java.

Lox is dynamically typed. Keywords include `var` for declaring variables and `nil` for
null. Only `nil` and `false` are falsy (like Ruby).

There aren't any functions yet, sorry. Have fun writing a useful program.

## Install & run
This is my first project using java and I'm using the IntelliJ IDE. Do whatever you need 
to do to set that kind of thing up.
 
When you run `main` in `Lox`, it'll run whatever lox file you pass in. If you don't pass in
a file, it opens a repl to run code line by line.
 
There's some basic error reporting (line and error message). The parser should
'synchronise' and continue if it comes up against a syntax error. That means you should get
up to one error message per statement. Maybe you won't have any errors in your statements.
Well done.

## Notes

The implementation of lox is made up so far of:
* Lox - the main class. Passes source code through the scanner, parser & interpreter.
Reports any errors thrown up by those programs.
* Scanner - scans source code and spits out tokens. Handles syntax errors such as
unterminated strings.
* Parser - turns the long series of tokens into an abstract syntax tree (AST) made up of 
expressions & statements. Handles errors such as invalid assignment.
* Interpreter - traverses the syntax tree, evaluating expressions and executing statements.
Only handles a few kinds of statements so far.

Extras:
* GenerateAst script generates subclasses of expressions and statements.
* AstPrinter groups expressions with parentheses, to create an unambiguous string
representation of the syntax tree.  

