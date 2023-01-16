# Error handling by the user

Errors need to be displayed as strings!

That is why all errors implement the [`std::error::Error`](https://doc.rust-lang.org/std/error/trait.Error.html)
trait which requires that the `Debug` and the `Display` traits are implemented.

```rust
use std::fmt;

#[derive(Debug)]
pub struct MyError {
  message: String
}

impl fmt::Display for MyError {
  // I copy & paste this code snippet every time
  fn fmt(&self, f: &mut fmt::Formatter<'_>) -> fmt::Result {
          write!(f, "{}", self.message)  // note the lack of semicolon
      }
}

impl std::error::Error for MyError {} // look, no code!

```
