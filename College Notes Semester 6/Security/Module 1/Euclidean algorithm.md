### Euclidean algorithm

A more efficient method is the _Euclidean algorithm_, a variant in which the difference of the two numbers a and b is replaced by the _remainder_ of the [Euclidean division](https://en.wikipedia.org/wiki/Euclidean_division "Euclidean division") (also called _division with remainder_) of a by b.

Denoting this remainder as _a_ mod _b_, the algorithm replaces (_a_, _b_) by (_b_, _a_ mod _b_) repeatedly until the pair is (_d_, 0), where d is the greatest common divisor.

>$gcd(48,18) -> gcd(18,48 mod 18) = gcd(18,12)$
> 					$-> gcd(12,18 mod 12)  = gcd(12,6)$
> 					$-> gcd(6,12 mod 6)     = gcd(6,0)$
> 					$= 6$
> $gcd(48,18)  = 6$
> 	 								


