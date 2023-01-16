# Automatic error handling by the program

```rust
match bake_cake() {
  Ok(cake) => cake.eat(),
  Err(error) => match error.step {
    BakingStep::MakeDough => { ... }
    BakingStep::CutFruit => { ... }
    BakingStep::PreHeatOven => { ... }
  }
}
```
