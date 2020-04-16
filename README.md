# jlox

An implementation of lox in java, following [Bob Nystrom's guide to crafting
interpreters](https://craftinginterpreters.com/).

It's almost completely implemented except for inheritance. Make your own way in this world.

## Lox

The lox language was designed by Bob Nystrom (see above). It's implemented here in java.

Lox is dynamically typed.
 
Syntax is largely of the C family. Keywords include `var` for declaring variables, `fun`
for functions and `nil` for null. Only `nil` and `false` are falsy (like Ruby). You have to 
end statements with `;`.


## Install & run
This is my first project using java and I'm using the IntelliJ IDE. Do whatever you need 
to do to set that kind of thing up.
 
When you run `main` in `Lox`, it'll run whatever lox file you pass in. If you don't pass in
a file, it opens a repl to run code line by line.
 
There's some basic error reporting (line and error message), including:
* Parse errors, i.e. syntax errors. It should report an error but carry on parsing
from the next statement, meaning you'll see multiple error messages if you have multiple 
dodgy statements.
* Resolution errors, to do with variables. E.g. if you try and define two vars with the same
name in the same scope, or try and use `this` outside a class.
* Runtime errors e.g. if you have type issues (like trying to divide two non-numbers). 
 
Maybe you won't have any. Well done.

## Notes

The implementation of lox is made up so far of:
* Lox - the main class. Passes source code through the scanner, parser & interpreter.
Reports any errors thrown up by those programs.
* Scanner - scans source code and spits out tokens. Handles syntax errors such as
unterminated strings.
* Parser - turns the long series of tokens into an abstract syntax tree (AST) made up of 
expressions & statements. Handles errors such as invalid assignment.
* Resolver - resolves variables to their values. Variables are stored in 'environments'
(i.e. hashmaps) for each nested scope. Doing this pass before running the interpreter
proper is better for performance bc each var expression is resolved only once, and better
allows static scoping.
* Interpreter - traverses the syntax tree, evaluating expressions and executing statements.

Extras:
* GenerateAst script generates subclasses of expressions and statements.
* AstPrinter groups expressions with parentheses, to create an unambiguous string
representation of the syntax tree. It's only half-implemented because I didn't need it once
I'd got some key things sorted. 

