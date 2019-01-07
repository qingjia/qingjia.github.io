---
layout: post
title: Calculate Primes with Python 
---
The program print the primes less than 30 with lambda and yield operator.


```
from itertools import count

def _not_divided(n):
    return lambda x:x%n>0

def primes():
    it = count(3,2)
    yield 2
    while True:
        n = next(it)
        it=filter(_not_divided(n), it)
        yield n
if __name__== "__main__":
    for i in primes():
        if i > 30:
            break
        print("i = %d" % i)
```
