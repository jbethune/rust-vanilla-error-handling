# The Result enum

Errors are typically wrapped in a `Result` enum:

```rust
pub fn bake_cake() -> Result<Cake, CakeBakingError> {
  let mut dough = make_dough()?;
  let fruit = cut_fruit()?;
  let mut cake = dough.mix_into(fruit);
  cake.apply_topping(ChocolateTopping::new())?;
  cake.bake(Temperature::new(180, TemperatureUnit::Celsius))?;
  Result::Ok(cake) // everything worked!
}
```
