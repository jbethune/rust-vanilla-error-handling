# Error enums

```rust
#[non_exhaustive]  // give us the option to expand in the future
pub enum MyError {
  SillyReasonToFail,
  UnfortunateReasonToFail,
  WeirdReasonToFail,
  PredictableReasonToFail,
  ComplexReasonToFail(usize, String),
  ObscureReasonToFail{thing: ObscureThing, date: Timestamp},
}
```

Or use a struct with an error kind:

```rust
pub struct myError {
  message: String
  kind: MyErrorKind
}
```
