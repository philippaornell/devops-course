# Introduction

## Testing mistakes


* Mistakes in the test code

    * Mistakes that cause us to believe tests pass

    * Mistakes that cause tests to pass when they should not

* Why are they bad?

    * Provides a false sense of security

    * DevOps workflows rely heavily on CI and CD

* How can you avoid them?
    
    * In practice, right now?

    * State-of-the-art sneak peak



# Common mistakes and practical countermeasures

## Tests are not executed
* Can for example appear because of

    * Missing annotations

    * Misspelled test function names


### Missing annotation (JUnit)
```java
@Test
public void testSomething() { // recognized
    assertTrue(true);
}

public void testSomethingElse() { // not rezognized
    assertTrue(false);
}
```

## Ensuring tests are executed

* Code coverage (with caveats)

* Stricter conventions

* Ensuring that tests can fail

    - TDD

    - Fault injection

## Tests that don't test (pseudo-tested methods)

* Can for example appear because of

    * Mistakes with references/pointers

    * Missing assertions

    * Copy-paste-and-forget-to-edit

    * Sleepy developer syndrome (SDS)

### A test that does not test (pytest)
```python
def test_my_sort():
    """Test sorting a random list with in-place"""
    randlist = generate_random_list(num_elements=1000)
    expected = randlist
    expected.sort()

    my_sort(randlist)
    assert lst == expected
```

## Eliminating/avoiding pseudo-tested methods

* Ensuring that tests can fail

    - TDD

    - Fault injection

* Test suite quality measurements

    - Mutation testing

    - Code coverage (with caveats)

# Automated countermeasures: the future?

## Automating countermeasures

* **Replace human:** Automated Test Generation

    * Tools such as `EvoSuite` (Java) and `Code Digger` (.Net)

    * Generate test cases from scratch

    * Doesn't always seem to work well in practice [@fraser2013does]

* **Help human:** Automatic Test Improvement

    * Tools such as `DSpot`

    * Improve already existing tests

* **Make better human:** Cybernetic Enhancements (possibly unethical)

# Conclusions

## Conclusions
* Test quality as important as production code quality 


* Passing test suite $\not \Rightarrow$ production code is correct
    - Insufficient as verification

* Test code correctness an open problem
    - Should you test your tests?

## References
