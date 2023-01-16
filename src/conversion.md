# Error conversion

To convert one error to another, use the [`std::convert::From`](https://doc.rust-lang.org/std/convert/trait.From.html) trait

```rust
impl std::convert::From<InnerError> for OuterError {
  fn from(error: InnerError) -> Self {
    OuterError{
      kind: OuterErrorKind::InnerComplications
    }
  }
}
```

And then you can call:

```rust
let outer_error = inner_error.into();
```
