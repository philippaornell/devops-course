# Introduction

## How to measure test suite awesomeness?

* Code coverage

* Fault detection rate

    - Mutation testing

* Is that enough?

# Performance measures

## Code coverage

* Pros

    - Automated

    - Percentages are nice

    - Good at indicating what has not been tested

* Cons

    - Poor at indicating what has been _tested_

    - False sense of security

## Mutation testing

* Concept
    
    - Slightly change production code (mutate)

    - Check if test suite discovers mutation

* Pros

    - Indicates what has not been tested properly

    - Automated

* Cons

    - Traditional mutation testing takes a _long_ time

    - Equivalent mutants (10-20%)

## What performance measures do not say

* Performance measures are exclusively focused on the _now_

* Software is hardly ever _done_

    - Especially true for DevOps!
    


# Maintainability

## Why important?

## How to measure?

# Automated test generation and maintainability

## Fibo.java

```java
public class Fibo {
    private long previous;
    private long current;

    public Fibo() {
        previous = 0;
        current = 1;
    }

    public long next() {
        long toReturn = previous;
        previous = current;
        current = toReturn + current;
        return toReturn;
    }
}
```

## EVOSUITE generated test

```java
@Test(timeout = 4000)
public void test0()  throws Throwable  {
  Fibo fibo0 = new Fibo();
  long long0 = fibo0.next();
  assertEquals(0L, long0);
  
  long long1 = fibo0.next();
  assertEquals(1L, long1);
}
```

### Clean test?
1. Tests one thing?
2. Good test name?
3. Clear structure (e.g. AAA)?


## No domain knowledge -> poor test

* Test scores high on performance (full coverage, 71%
  mutation score)

### Broken implementation (generates 0, 1, 2, 3, ...)

```java
public class Fibo {
    private long current;

    public Fibo() {
        current = 0;
    }

    public long next() {
        int toReturn = current;
        ++current;
        return toReturn;
    }
}
```

## Summary

* Performance is _hard_ to measure in a general way

* High performance $\not \Rightarrow$ good test suite

* Maintainability is equally important


## References
