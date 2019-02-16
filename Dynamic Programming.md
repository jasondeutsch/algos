dynamic programming is mainly an optimizatino over plain recursion.

whereever we see a recursive solutoin that has repeated calls for the same inputs, we can optimize it using dynmic programming.

the idea is to simply store the results of subproblems so that we do not have to re-compute them when needed later.

this simple optimization reduces the time complexities from exponential to polynomial.

Example:

```c

// recursion: exponential
int fib(int n) {
  if (n <= 1) {
    return n;
  }
  return fib(n-1) + fib(n-2);
}

// dynamic programming: linear

f[0] = 0;
f[1] = 1;
for (i = 2; i <= n; i++) {
  f[i] = f[i-1] + f[i-2];
}
```