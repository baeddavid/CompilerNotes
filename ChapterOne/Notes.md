#Chapter 1

* A Compiler is a program that can read a program in one language — the source language — and translate it into an equivalent program in another language — the target language. 
* An Interpreter is another common kind of language processor. Instead of producing a target program as a translation, an interpreter appears to directly execute the operations specified in the source program on inputs supplied by the user.

Example
* A Java source program may first be compiled into an intermediate form called bytecodes. The bytecodes are then interpreted by a virtual machine. A benefit of this arrangement is that bytecodes compiled on one machine can be interpreted on another machine, perhaps across a network.
* some Java compilers called just-in-time compilers, which translates the bytecodes into machine language immediately before they run the intermediate program to process the input.

The task of collecting the source program is sometimes entrusted to a separate program, called a preprocessor. The modified program is then fed to a compiler. The compiler may produce an assembly-language program as its output, because assembly-language is easier to produce output and debug. The assembly is then processed by  a program called ab assembler that produces relocatable machine code as its output.

Large programs are often compiled in pieces, so the relocatable machine code may have linked together with other relocatable object files and library files into the code that runs on the machine. The Linker resolves external memory addresses, where the code in one file may refer to a location in another file. The Loader then puts together all the executable object files into memory for execution.
