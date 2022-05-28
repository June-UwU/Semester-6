# Structure Of A Compiler

The Compiler can generally be divided into two the parts *analysis* and *synthesis*.The **Analysis** part breaks up the source program into constituent pieces and imposes a grammatical structure on them.It then uses this structure to create an intermediate representation of source.If analysis part detects that the source program is either syntactically ill formed or semantically unsound, then it must provide informative messages. The analysis part also collects information about the source and stores it in a data structure called *symbol table*,which is passed along with the intermediate representation to the synthesis part.

The  **Synthesis** part constructs the desired target program from the intermediate representation and the information in the symbol table. The analysis part is often called the *front end* of the compiler; the synthesis part is the *back end*.

![Phases of the Compiler](../../Images/Compiler%20Design/StuctureCompiler.jpg)

On further examination the compiler is divided into phases, each which transforms one representations of the source program to another. The **symbol table** , which stores information about the entire program ,is used by all phases of the compiler.

- [Lexical Analyzer](Lexical%20Analyzer.md)
