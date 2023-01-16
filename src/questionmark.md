# The question mark operator

The question mark operator does 2 things at once:
* return from the function (or block, once we have try-blocks)
* convert the value before the question mark into the error-type of a function

That means when we call:

```rust
fn my_function() -> Result<usize, OuterError> {
  function_that_produces_inner_error()?;
  42
}

```
and if the function fails, then the inner error is automatically converted
to the outer error type (assuming we have written the `std::convert::From` code for that).
