## Sentinals

Sentinals are the character that are used to reduce the number of checks when a lexeme is tokenized and the forward must be checked if its the end of the file and what character is read.This usually results in a multiway comparisons. but if a single character is used to represent the end of the file then the check can be reduced to single way check .**This special character than cannot be the part of the source is called a *sentinal*.** and a natural choice is $eof$.
