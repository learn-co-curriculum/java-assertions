# Assertions

## Learning Goals

- Learn about the different assertion methods.

## Introduction

In the last lesson, we were exposed to an assertion method, `assertEquals()`.
We saw how it could check and verify two different types of values: an expected
value and the actual value. This is crucial to unit testing since it can
immediately let us know if a test passed or failed when executed. In this
lesson, we will learn more about the different types of assertion methods that
can help us out when we are writing our unit tests!

## Assertion Methods

Let's get into discussing the various utility assertion methods now in the
`Assertions` class!

### assertEquals

As we saw in our last lesson, the `assertEquals()` method takes in two arguments
of almost any data type! As we will see in several of these assertion methods,
the first parameter is the **expected** value and the second parameter is the
**actual** value that the method evaluated to. The `assertEquals()` method will
check that two arguments are "equal" to each other.

```java
@Test
void testEquals() {
    int expected = 2;
    int actual = 2;
    
    assertEquals(expected, actual);
}
```

It should also be noted that most assertion methods can take in more parameters,
such as a `String message` to display when the assertion fails:

```java
@Test
void testEquals() {
    int expected = 2;
    int actual = 2;
    
    assertEquals(expected, actual, "The integers are not equal.");
}
```

The third parameter is considered optional. Know that we can specify a message
like the one above if we choose to in any of these assertion methods we mention
today. But for the purposes of this lesson, we will look only at the required
arguments.

### assertNotEquals

Sometimes we want to make sure that two data types are _not_ equal to each
other. In unit testing, we can use the `assertNotEquals()` method then to check
the two arguments are indeed "not equal".

```java
@Test
void testNotEquals() {
    double unexpected = 2.99;
    double actual = 2.999;
    
    assertNotEquals(unexpected, actual);
}
```

### assertTrue

Perhaps we want to ensure that a certain condition is true. We can use the
`assertTrue()` method to verify! Unlike the other assertion methods we have
seen, this method only takes in one required parameter and that is a condition
that can evaluate to a boolean.

```java
@Test
void testTrue() {
    boolean condition = 2 >= 1;
    assertTrue(condition);
}
```

### assertFalse

The complementary to the `assertTrue()` method is to assert that a condition is
false. If we want to verify that a condition evaluates to false, we can use the
`assertFalse()` method:

```java
@Test
void testFalse() {
    boolean condition = 2 < 1;
    assertFalse(condition);
}
```

## Assertions and Unit Tests

Now that we know a bunch of different assertion methods, we can write them into
our unit tests!

Remember that unit tests are supposed to be the smallest unit of testing - each
test will test a specific functionality. It is good practice to try to minimize
the asserts in each test; with one assert per test if possible. For example, if
we want to test if a method that returns a quotient and another method that
returns a sum, it is best to break up those into two different test methods:

```java
@Test
void divide() {
    double dividend = 4;
    double divisor = 2;
    double quotient = Calculator.divide(dividend, divisor);
    assertEquals(2.0, quotient);
}

@Test
void add() {
    double operand1 = 4.5;
    double operand2 = 2.5;
    double sum = Calculator.add(operand1, operand2);
    assertEquals(7.0, sum);
}
```

## Summary

The assertion methods we reviewed in this lesson can also be found in the JUnit
documentation here:
[Assertions Class](https://junit.org/junit5/docs/5.7.2/api/org.junit.jupiter.api/org/junit/jupiter/api/Assertions.html)

Below is a table briefly summarizing the assertion methods covered in this
lesson that may you can use as a quick reference:

| Assertion                             | Description                                                                                        |
|---------------------------------------|----------------------------------------------------------------------------------------------------|
| `assertEquals(expected, actual)`      | Takes in two required arguments to assert that the expected value and actual value are equal       |
| `assertNotEquals(unexpected, actual)` | Takes in two required arguments to assert that the unexpected value and actual value are not equal |
| `assertTrue(condition)`               | Takes in one required boolean argument to assert that the condition is true                        |
| `assertFalse(condition)`              | Takes in one required boolean argument to assert that the condition is false                       |

## Resources

[Assertions Class](https://junit.org/junit5/docs/5.7.2/api/org.junit.jupiter.api/org/junit/jupiter/api/Assertions.html)
