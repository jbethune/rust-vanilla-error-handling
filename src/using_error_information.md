# Using information from errors

When analysing the information, errors can be handled and recovery can happen

```rust
match error.step {
  BakingStep::MakeDough => {
    throw_old_dough_away();
    clean_up_kitchen();
    buy_premade_dough();
  },
  BakingStep::CutFruit => {
    if self.is_bleeding {
      apply_patch_to_wound(&mut self);
       // this shouldn't stop us
    }
  },
  // ...
}
```
