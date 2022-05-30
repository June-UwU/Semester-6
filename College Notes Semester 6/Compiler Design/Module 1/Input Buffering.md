## Input Buffering

Input buffering are strategies to speed up the task of reading source code ,but they are limited since it is required to look at once or more characters beyond the next lexeme before we can be sure that we have the right lexeme.

eg:
> iffy = 10;
> 
$<if>$
$<id,fy>$
$<equals>$
$<number,10>$
>

this is malformed code but improper lexical analysis can generate valid and often wrong tokens

### Speeding Up Reading Source
[Buffer Pairs](Buffer%20Pairs.md)
[Sentinals](Sentinals.md)

