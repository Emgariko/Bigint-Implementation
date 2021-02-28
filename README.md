# Bigint-Implementation

Big integer implementation ITMO CT basic Cpp course 

#### Big-integer class

Implemented class supports: 

- Default constructor that initializes the number to `0`.
- Copy-constructor. After this constructor is available to change copy and original object independently.
- `int` constructor.
- `std::string` explicit constructor.
- Assignment operator.
- Comparison operators.
- Arithmetical operation: addition, subtraction, unary minus and plus.
- `O(nm)` complexity multiplication, where `n`, `m` - multiplier length in bits.
- `O(nm)` division and remainder.
- Prefix/postfix increment/decrement
- Bit operators: `and`, `or`, `xor`, `not`, shits

#### Optimized storage

Storage implements [Small Object](https://github.com/CppCon/CppCon2016/blob/master/Presentations/The%20strange%20details%20of%20std%20string%20at%20Facebook/The%20strange%20details%20of%20std%20string%20at%20Facebook%20-%20Nicholas%20Ormrod%20-%20CppCon%202016.pdf) and [Copy-on-write](https://en.wikipedia.org/wiki/Copy-on-write) optimizations. 

Storage properties:

- If the number stored by `big_integer` is from the range `[-2^95; 2^95 - 1]` then the storage doesn't allocate heap memory. Storage allocate no more than one block of heap memory per instance of `big_integer` otherwise.
-  Copy constructor and assignment operator has `O(1)` complexity and satisfies no-throw exceptions guarantee.
