# bigmath

Arbitrary precision mathematics library implemented in pure V.

## Initial Goals

1. The main aim for this project is to be a drop-in replacement for V's [math/big](https://github.com/vlang/v/tree/master/vlib/math/big).
2. Have no dependency on external thridparty libraries.
3. Be written completely in V.
4. Implement the following types:
   - Int
   - Fraction
   - Decimal
5. Be well tested. Besides being in sync with the [standard tests](https://github.com/vlang/v/blob/master/vlib/math/big/big_test.v), we define more tests to ensure proper coverage of code and correct handling of all practical cases.

## Road-map

### 0.1.0

- [ ] Int is feature complete.
	- [ ] Initialization
	- [ ] Equality and Comparison
	- [ ] Addition and Subtraction
	- [ ] Multiplication
	- [ ] Division
	- [ ] Representation
- [ ] Existing tests work
	- [ ] `big_test.v` passes

### 0.2.0

- [ ] Fraction is feature complete.

### 0.3.0

- [ ] Decimal is feature complete.

### 0.4.0

- [ ] Standard Math library
	- [ ] Algebraic Functions
		- [ ] Roots
	- [ ] Transcendental Functions
		- [ ] Trigonometric Functions
		- [ ] Exponential and Logarithmic Functions
	- [ ] Fundamental Constants

## Under Active Development

This library is being developed actively by Subhomoy Haldar (@hungrybluedev). If you want to get involved you can do the following:

1. Create Feature Requests on the Issues tab.
2. Report a bug in the Issues tab and then submit a pull request if you can.
3. Stay in touch
    - Drop by on the Official VLang Discod Server - I'm fairly active there.
    - Follow me on Twitter [@hungrybluedev](https://twitter.com/hungrybluedev). 
