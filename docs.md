# Proposed Documentation

## Important Notice

This is not the final API for the library. It will evolve as development continues. This document is meant to be a reference for both end users and contributors alike for the duration of development.

Once major progress is made (like releasing version 0.1.0 or 0.2.0), we will finalize the API and ensure backwards compatibility.

## Int (`big.bigint`)

### Overview

`Int` is an arbitrary precision integer that supports the following operations:

1. Initialization
	1. From primitive integers (both signed and unsigned)
	2. From strings (including bases other than 10)
2. Comparison
	1. Equality (`eq`)
	2. Less than (`lt`) and less than or equal to (`le`)
	3. Greater than (`gt`) and greater than or equal to (`le`)
3. Arithmetic
	1. Addition
	2. Subtraction
	3. Multiplication
	4. Division
	5. Modular division
4. Representation as string
	1. Decimal
	2. Binary, Octal, Hexadecimal (and other bases that are powers of 2)
	3. General bases

### Initialization

#### From Integer

There exist four functions for the largest integer types:

1. 32-bit types: `int` and `u32`
2. 64-bit types: `i64` and `u64`

To initialize an Int, we use `from_<type_name>()` as shown below:

```v
base_damage := bigint.from_int(-90)
large_value := bigint.from_i64(i64(9007199254740992))

answer_to_everything := bigint.from_u32(42)
big_contrived_number := bigint.from_u64(u64(1152922010148202969))
```

Smaller integer types are coerced automatically, so `from_int` for signed integers and `from_u32` for unsigned integers will suffice.

#### From String

By default, normal strings are treated as sequences of decimal digits. There is a general function to create an `Int` from any radix.

```v
very_random_number := bigint.from_string('4') // xkcd.com/221/
fortytwo_in_binary := bigint.from_radix('101010', 2)
hexadecimal_phrase := bigint.from_radix('ABE_FED_A_BABE_CAFE', 16)
```

Using `_` (underscores) to separate and group the digits is allowed.

### Comparison

#### Equality

_**Note:** Support for `==` has been requested (along with `!=`, `<`, `>`, `<=` and `>=`). You can track the progress of that [here](https://github.com/vlang/v/issues/4742)._

```v
one := bigint.from_int(1)
two := bigint.from_int(2)

five := bigint.from_int(5)

// assert five == (one + two * two)
assert five.eq(one + two * two)
```

#### Comparison

```v
three := bigint.from_int(3)
six := bigint.from_int(6)
nine := bigint.from_int(9)

// assert three < six
assert three.lt(six)

// assert three <= nine
assert three.le(nine)

// assert !(nine < three)
assert !(nine.lt(three))

// assert !(nine <= six)
assert !(nine.le(six))

// assert six > three
assert six.gt(three)

// assert nine >= three
assert nine.ge(three)
```