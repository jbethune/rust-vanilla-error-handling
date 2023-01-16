# Crash when unexpected things happen

Depending on how high your reliability requirements are, you might want to avoid this option.

```rust
let cake = bake_cake().unwrap(); // It's okay if this crashes
```

Or, if you are sure that the baking will always succeed:

```rust
let cake = bake_cake().expect("Professional baker on the job");
```

That way you will know which assumption you had when the baking fails.
