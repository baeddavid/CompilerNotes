#Chapter 1

* A Compiler is a program that can read a program in one language — the source language — and translate it into an equivalent program in another language — the target language. 
* An Interpreter is another common kind of language processor. Instead of producing a target program as a translation, an interpreter appears to directly execute the operations specified in the source program on inputs supplied by the user.

Example
* A Java source program may first be compiled into an intermediate form called bytecodes. The bytecodes are then interpreted by a virtual machine. A benefit of this arrangement is that bytecodes compiled on one machine can be interpreted on another machine, perhaps across a network.
* some Java compilers called just-in-time compilers, which translates the bytecodes into machine language immediately before they run the intermediate program to process the input.

The task of collecting the source program is sometimes entrusted to a separate program, called a preprocessor. The modified program is then fed to a compiler. The compiler may produce an assembly-language program as its output, because assembly-language is easier to produce output and debug. The assembly is then processed by  a program called ab assembler that produces relocatable machine code as its output.

Large programs are often compiled in pieces, so the relocatable machine code may have linked together with other relocatable object files and library files into the code that runs on the machine. The Linker resolves external memory addresses, where the code in one file may refer to a location in another file. The Loader then puts together all the executable object files into memory for execution.


Analysis - breaks up the source program into constituent pieces and imposes a grammatical structure on them. It then uses this structure to create an intermediate representation of the source program. If the analysis part detects that the source program is either syntactically ill-formed or semantically unsound, then it must provide informative messages, so that the user can take corrective action. The analysis also collects information about the source program and stores it in a data structure called a symbol table. 

Synthesis - constructs the desired target program from the intermediate representation and the information in the symbol table. The analysis part is often called the front end of the compiler; the synthesis part is the back end. If we examine the compilation phase, we see that it operates in a sequence of phases, each of which transforms one representation of the source program to another. 

Phases of Compilation
1. Lexical Analysis or Scanning - The lexical analyzer reads the stream of characters making up the source program and groups the characters into meaningful sequences called lexemes. For each lexeme, the lexical analyzer produces as output a token of the form <token-name, attribute-value> that it passes on to the subsequent phase, syntax analysis.
    * In the token, the first component token-name is an abstract symbol that is used during syntax analysis. 
    * The second component attribute-value points to an entry in the symbol table for this token. 
    * Information from the symbol-table is needed for semantic analysis and code generation.
        * For example, suppose a source program contains the assignment statement position = initial + rate * 60.
            1. Position is a lexeme that would be mapped into a token <id, 1> where id is an abstract symbol standing for identifier and 1 points to the symbol-table entry for position. The symbol-table entry for an identifier holds information about the identifier, such as its name or type.
            2. The assignment symbol = is a lexeme that is mapped to the token <=>. Since the token needs no attribute-value, we have omitted the second component. We could have used any abstract symbol such as assign for the token-name, but for notational convenience we have chosen to use the lexeme itself as the name of the abstract symbol.
            3. Initial is a lexeme that is mapped to <id, 2> where 2 points to the symbol-table entry initial.
            4. + is a lexeme that is mapped to the token <+>.
            5. rate is a lexeme that is mapped to the token <id, 3>, where 3 points to the symbol-table entry rate.
            6. * is a lexeme that is mapped to the token <*>.
            7. 60 is a lexeme that is mapped to the token <60>.
            8. This evaluates to: <id, 1> <=> <id, 2> <+> <id, 3> <*> <60>
            9. Technically the lexeme <60> should evaluate to a token like <number, 4>.