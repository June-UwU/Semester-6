## Lexical Analysis

The first phase of a compiler is called lexical analysis or scanning. It reads the stream of characters making  up the source program and groups the characters into meaningful sequences called lexemes. For each lexeme, the lexical analyzer produces as output a token of the form


$<token-name , attribute-value>$

that is passed to syntax analysis . In this the token-name is an abstract symbol that is 
used during *syntax analysis*, and the *attribute-value* points to a entry in the symbol table for this token.

eg : 

$position =  initial  + rate  * 60$   (1.1)

The character is grouped into the following lexemes and mapped into the following :

> 	1. $position$ is a lexeme that would be mapped into a token $<id,1>$ , where $id$ is an abstract symbol standing for *identifier*  and $1$ points to the symbol table entry for $position$. The symbol table entry for an identifer holds information about the identifier ,such as  its name and type
> 	 
> 	2. The assignment symbol $=$ is a lexeme that is mapped into the token $<=>$.since this token needs no atttribute value it is omitted here.
> 	
> 	3. intial is a lexeme that is mapped into the token $<id,2>$,where $2$ points to the symbol table entry for $intial$.
> 	
> 	4. $+$ is a lexeme that is mapped into the token $<+>$.
> 	
> 	5. $rate$ is a lexeme that is mapped on to the token $<id,3>$,where $3$ points to the entry in symbol table entry for $rate$.
> 	
> 	6. * is a lexeme that is mapped into the token $<*>$.
> 	
> 	7. $60$ is a lexeme that is mapped into the token $<60>$.
>      

blanks seperating the lexemes would be disgarded by the lexical analyzer and the expression becomes

>
>  $<id,1> < = > <id,2> <+> <id,3> <*> <60>$
>   

In this representation, the token-names $+ , = , *$ are abract symbols for the same. 


```
Important Terms

Lexemes : A group of characters that are meaningful in a sequence.

Token : An Instance of the lexeme.

```

### Problems With Tokens And Recognizing Token
[Input Buffering And The Problem That It Faces](Input%20Buffering)

[](Role%20Of%20Lexical%20Analyzer.md)
[](Tokens%20,Patterns%20And%20Lexemes)