# Equivalence Partitioning

Equivalence partitions are ranges of values that can be treated the same for testing purposes. For example, given a function that adds two numbers together, it may be valuable to check that it can add `1` to `2`. However, once you've verified that, verifying that `1` can be added to `3` is unlikely to reveal any new insights into the code. That's because `2` and `3` are part of the same equivalence partition.

## Equivalence Partitions

Equivalence partitions are always specific to the context. For example, a function that should accept an array of no more than 10 string elements might have the following partitions:

* Empty array
* Array with one string
* Array with multiple strings

### Strings

Some stock partitions for strings are:

* An empty string
* A single character
* Multiple characters
* The maximum string length on the platform. The longest string supported by the JavaScript spec is 2^53, but in practice the number is much lower.

### Numbers

Some stock partitions for numbers are:

* `-1`
* `0`
* `1`
* Integers greater than 1
* Integers less than -1
* Postive rational numbers
* Negative rational numbers
* Positive irrational numbers
* Negative irrational numbers
* Postive integer boundary
* Highest integer supported on the platform
  * There's a built-in constant representing this which you can access with `Number.MAX_SAFE_INTEGER`
* Highest decimal supported on the platform
  * There's a built-in constant representing this which you can access with `Number.MAX_VALUE`
* Lowest integer supported on the platform
  * There's a built-in constant representing this which you can access with `Number.MIN_SAFE_INTEGER`
* Lowest decimal supported on the platform
  * There's a built-in constant representing this which you can access with `Number.MIN_VALUE`
* Positive infinity
  * There's a built in constant representing this which you can access with `Number.POSITIVE_INFINITY`
* Negative infinity
  * There's a built in constant representing this which you can access with `Number.NEGATIVE_INFINITY`

### Booleans

The only legal values for Booleans are `true` and `false`.

### Arrays

Some stock partitions for arrays are:

* Empty array
* Array with 1 element
* Array with more than one element

### Objects

Some stock partitions for objects are:

* Empty object
* Array with 1 element
* Array with more than one element

## Boundaries

A boundary is where values change from one partition to another. For example, if one partition is the numbers `1` through `5` and another partition is the numbers `6` through `10`, the boundaries are `1`, `5`, `6`, and `10`.

## Watch Out!

* You may want to check all data types with `null` and `undefined` too

## Additional Resources

| Resource | Description |
| --- | --- |
| [MDN: Infinity](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/POSITIVE_INFINITY) | MDN's guide to `Infinity`, which includes what different calculations with infinity should evaluate to. |
