# Rust sucks

[Related video](/rust.webm)

* Rust lacks a specification
  * There is only one compiler
>>Everything in rust is undefined
>>Therefore Rust has more undefined behaviour than C.

* Cargo sucks
* Takes years to build

>>Consider adding CString/* const i8 literals
>>Use concat!

```
macro_rules! c_str {
    ($s:expr) => { {
        concat!($s, "\0").as_ptr() as *const i8
    } }
}

foo(c_str!("my string"));
```

I'll add more things later, I'm busy rewriting Rust software in C ;-)
