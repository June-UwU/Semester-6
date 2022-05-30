## Modular Arithemetic

Modular arithmetic is a system of arithmetic for integers, where values reset to zero and begin to increase again, after reaching a certain predefined value, called the modulus (modulo). Modular arithmetic is widely used in computer science and cryptography

> Definition Let ZN be a set of all non-negative integers that are smaller than N:  
    ZN = {0,1,2,...,N-1}
> 
> where:
>
>-   N is a positive integer,
>-   if N is a prime, it will be denoted p (and the whole set as Zp).
>

### Modular inversion

>
>Integers in modular arithmetic may (but not must) have inverse numbers.
>
**Definition** :The inverse of x in ZN is a number y in ZN, that satisfies the equation:  
    x · y = 1 (in ZN)
>
>where:
>
>-   y is denoted x-1
>

For example, if N is an odd number, then the inverse of 2 in ZN is (N+1)/2:  
    x · (N+1)/2 = N + 1 = 1 (in ZN)
    
>
**Theorem** : A number x is invertible in ZN if and only if the numbers x and N are relatively prime.
>
>- The theorem can be proved using the fact that it is possible to present the greatest common divisor of two integers as a sum of two products each of the numbers and another properly selected integer:  
        $a·x + b·y = gcd(x,y)$
>


Determining inverse numbers in ZN allows solving linear equations in modular arithmetic:  
    the equation:  $a · x + b = 0 (in Z_{N})$  
    has the solution:   $x = -b · a-1 (in Z_{N})$

>Definition The symbol $Z^{*}_{N}$ denotes a set of all elements of $Z_{N}$ that are invertible in $Z_{N}$ ; that means the set of numbers x that belong to ZN, and x and N are relatively prime.
>
>
>-   for example for a prime number p:  
        $Z^{*}_{p}  =  Z_{p} \ {0} = {1, 2, …, p - 1}$
>

