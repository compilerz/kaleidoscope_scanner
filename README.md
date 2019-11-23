the [kaleidoscope] language is part of the LLVM intoroduction tutorial.
given below is what a fibonacci number program would look like:

```python
# Compute the x'th fibonacci number.
def fib(x)
  if x < 3 then
    1
  else
    fib(x-1)+fib(x-2)

# This expression will compute the 40th number.
fib(40)
```

it should also be possible to call math functions, like so:

```python
extern sin(arg);
extern cos(arg);
extern atan2(arg1 arg2);

atan2(sin(.4), cos(42))
```

we will implement the scanner using [flex] as part of the compilers
course at IIITH. a scanner takes as input, the program text, and
processes it into tokens for the next stage of the compiler, parser.
we use regular expressions to define each token type, and the associated
action. [flex] is a scanner code generation tool that generates a
**C code** for scanner, making our job a lot easier.

here is what the token would look like:

```text
identifier: [a-zA-Z][a-zA-Z0-9]*
number:     [0-9.]+
comment:    #[^\n]*
symbol:     otherwise
```

see `main.l` for the scanner code. code can be compiled with `make`
and `lex.yy.c` is the generated **C code** by [flex].



[kaleidoscope]: https://llvm.org/docs/tutorial/MyFirstLanguageFrontend/LangImpl01.html
[flex]: https://github.com/westes/flex
