# Example: std::num::ParseIntError

A rather simple error type to inform the user that they provided bad numerical input:
[ParseIntError](https://doc.rust-lang.org/std/num/struct.ParseIntError.html).

`ParseIntError` comes with its own error kind:
[std::num::IntErrorKind](https://doc.rust-lang.org/std/num/enum.IntErrorKind.html)
(which is a much smaller enum than the IO error kind).
