# Combining error types

Problem: You typically can't have more than 1 error result type

```rust
fn my_function(a: usize) -> Result<usize, OneSingleErrorType>
```

Ways to solve this:
* Use enums. And make them not-exhaustive for future-proofness
* Convert internal errors into outward-facing errors
* Create chains of errors, with the outward-facing error being the head of the chain

We will now look at each of these solutions.
