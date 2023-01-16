# Error structs

Rust errors are regular structs (or enums) that carry information about what went wrong

```rust
pub struct CakeBakingError {
  pub step: BakingStep, // enum of baking steps
  pub description: String,
}

pub enum BakingStep {
  MakeDough,
  CutFruit,
  PreHeatOven,
  // ... imagine more
}
```
