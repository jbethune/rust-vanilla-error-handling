# Chains of errors

Chaining errors means that you define a `source` for each non-primary error.

The `std::error::Error` trait has a default-method called `source`:

```rust
fn source(&self) -> Option<&(dyn Error + 'static)> { ... }
```
which returns `None` in the default implementation. But we can override that:

```rust
impl std::error::Error for MyError {
  // look, no longer empty!
  fn source(&self) -> Option<&(dyn Error + 'static)> {
    Some(&self.inner_error)
  }
}
```

However, building up these chains of errors can be hard when you want to allow
any type of error to be in the chain. The code below gives a full
working example:

```rust
// You will typically use a library for this instead of writing it by hand.

use std::fmt;

#[derive(Debug)]
pub struct MyError {
    message: String,
    inner: Option<Box<dyn std::error::Error + 'static>>
}

impl MyError {
    pub fn new(message: String) -> Self {
        MyError{message, inner: None}
    }

    pub fn chain(message: String, other: Box<dyn std::error::Error + 'static>) -> Self {
        MyError{message, inner: Some(other)}
    }
}

impl fmt::Display for MyError {
  // I copy & paste this code snippet every time
  fn fmt(&self, f: &mut fmt::Formatter<'_>) -> fmt::Result {
      write!(f, "{}", self.message)  // note the lack of semicolon
  }
}

impl std::error::Error for MyError {
    // we implement an optional method to enable error chains
    fn source(&self) -> Option<&(dyn std::error::Error + 'static)> {
        self.inner.as_deref() // take a reference of the inner value
    }
}

```
