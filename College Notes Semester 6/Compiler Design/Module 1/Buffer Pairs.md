## Buffer Pairs

This technique requires two buffers that are alternately reloaded 

![](../../Images/Compiler%20Design/BufferPairs.png)

Each buffer has the same size N, and N is usually the size of disk block . Using one system read command we can read N characters into a buffer, rather than using one system call per character. If fewer than N character remains , a special character that marks the end of file is used ,represented by $eof$,

Two pointers to the input are maintained :

1. Pointer **LexemeBegin**, marks the beginning of the current lexeme, whose extend we are attempting to determine
2. Pointer **forward** scans ahead until a pattern match is found;

Once the next lexeme is found, forward is set to the character at its right end. Then , after the lexeme is recorded as an attribute value of a token returned to the parser, lexemeBegin is set to the character immediately after the lexeme has been just found.After the end of lexeme forward must check for the end of file and change the buffers if nessary. 