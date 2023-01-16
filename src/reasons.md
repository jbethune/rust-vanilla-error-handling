# Reasons for errors

Errors are a fundamental part of Rust programming because Rust wants to be a language for writing reliable programs.

Errors may happen due to different reasons:

1) A function was called with invalid arguments
2) A resource (file/network/...) is temporarily not available
3) Access is prohibited
4) ...

Depending on what is going on, different recovery strategies make sense
1) Request better input
2) Try again at a later time
3) Inform the user and let them talk to another human about it
4) ...
