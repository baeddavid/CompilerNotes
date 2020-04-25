# Chapter One Exercises

1.1.1 

What is the difference between a compiler and an interpreter?

A *compiler* reads the source program and then coverts it into the *target* language.
A *interpreter* directly executes the operation specified in the source program on inputs given by the user.

1.1.2 

What are the advantages of a compiler over an interpreter; an interpreter over a compiler?

The machine language target program produced by a compiler is usually much faster than an interpreter at mapping
inputs to outputs.

An interpreter gives better diagnostics than a compiler because it executes the source program statement by statement.

1.1.3 

What advantages are there to language-processing system in which the compiler produces an assembly language rather than machine language?

Assembly language is easier to debug and produce as output.

1.1.4

A compiler that translates a high-level language into another high-level language is called a source-to-source translator. 
What advantages are there to using C as a target language for a compiler.

Producing C as a target language for a compiler means that the ultimate program may be run on any machine capable of running C code.

1.1.5

Describe some of the tasks an assembler needs to perform

* An assembler produces relocatable machine code as an output.
* Can be used in large programs to modularize code and then link together with other relocatable object files. 

