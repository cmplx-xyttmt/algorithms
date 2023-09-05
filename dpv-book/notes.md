# Algorithms (by DPV)

## Chapter 0: Prologue
Questions to ask about an algorithm:
1. Is it correct?
2. How much time does it take as a function of n?
3. Can we do better?

### Runtime analysis for Fibonacci algorithm
```
function fib1(n):
    if n = 0: return 0
    if n = 1: return 1
    return fib1(n - 1) + fib1(n - 2)
```

Let `T(n)` be the number of computer steps needed to compute `fib1(n)`:

$T(n) <= 2$ for $n <= 1$

$T(n) = T(n - 1) + T(n - 2) + 3$ for $n > 1$

The running time of the algorithm grows as fast as the Fibonacci numbers i.e $T(n)$ is exponential in $n$!

To make this more efficient, store intermediate values:
```
function fib2(n):
    if n = 0: return 0
    create an array f[0..n]
    f[0] = 0, f[1] = 1
    for i=2..n:
        f[i] = f[i - 1] + f[i - 2]
    return f[n]
```

This algorithm is linear in $n$, assuming adding 2 numbers takes constant time. However, this isn't true when the numbers are big enough.

Each Fibonacci number is about $0.694n$ bits long, therefore the number of steps taken by `fib2` is proportional to $n^2$.



