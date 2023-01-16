# Example: std::io::Error

The most frequent error in the Rust ecosystem: [`std::io::Error`](https://doc.rust-lang.org/std/io/struct.Error.html)
Whenever you fail to read or write from/to a file, you will get this error

Some (struct-based) errors come with an error-kind enum:
[std::io::ErrorKind](https://doc.rust-lang.org/std/io/enum.ErrorKind.html)
There are a lot of different things that can go wrong.
Some are more critical than others.
std::io::Error is really complex, because there are a lot of different potential IO failures.
(and it is marked as non-exhaustive)
