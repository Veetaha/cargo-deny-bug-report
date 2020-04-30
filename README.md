When running `cargo deny check` in the root of the repo you get:

# Expected
No errors, since `stream-vbyte` has a clarification to use `Unlicense` which is
explicitly allowed.

# Actual
```log
~/junk/cargo-deny-bug-report (master) $ cargo deny check
error: stream-vbyte 0.3.2 (registry+https://github.com/rust-lang/crates.io-index) is unlicensed

   ┌── stream-vbyte 0.3.2 (registry+https://github.com/rust-lang/crates.io-index):2:9 ───
   │
 2 │ name = "stream-vbyte"
   │         ^^^^^^^^^^^^ a valid license expression could not be retrieved for the crate
   ·
 4 │ license = ""
   │            - license expression was not specified
   ·
 6 │     { path = "LICENSE.txt", hash = 0x508d93ea, score = 0.31 },
   │                                                        ---- low confidence in the license text
   │
   = stream-vbyte v0.3.2
     └── cargo-deny-bug-report v0.1.0

2020-04-30 12:23:01 [ERROR] encountered 1 errors
```
