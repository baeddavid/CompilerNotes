* Syntax - The syntax of a programming language describes the proper form of its programs.
* Semantics - The semantics of the language defines what its programs mean; that is, what each program does when it executes.
* Lexical analyzer - A lexical analyzer allows a translator to handle multi character constructs like identifiers, which are written as sequences of characters, but are treated as units called tokens during syntax analysis.

Two forms of intermediate code 
1. Abstract Syntax Trees - Represents the hierarchical syntactic structure of the source program.
    * The root of the abstract syntax tree represents an entire do-while loop. The left child of the root represents the body of the loop, which   consists of only the assignment i = i + 1. The right child of the root represents the condition a[i] < v. 
    * 
2. Sequence of Three-Address - This form of intermediate code takes its name from instructions of the form x = y op z, where op is a binary operator, y and z are the addresses for the operands, and x is the address for the result of the operation. 

stmt —> if ( expr ) stmt else stmt 
in which the arrow may be read as “can have the form.” Statement can have the form if expression statement else statement.
Such a rule is called a production. Variables like expr and stmt represent sequences of terminals and are called nonterminals.

* Context-free grammar
    1. Terminal - A set of terminal symbols, sometimes referred to as “tokens”. The terminals are the elementary symbols of the language defined by the grammar.
    2. Nonterminals - A set of nonterminals, sometimes called “syntactic variable.” Each nonterminal represents a set of strings of terminals, in a manner we shall describe.
    3. Productions - A set of productions where each production consists of a nonterminal, called the head or left side of the production, an arrow, and a sequence terminals and/or nonterminals, called the body or right side of the production. The unintuitive intent of a production is to spec one of the written forms of a construct; if the head nonterminal represents a construct, then the body represents a written form of the construct.
    4. A designation of one of the nonterminals as the start symbol.
