# AFL++ Fuzz Testing with Rust

This repository contains a lightweight Rust program designed to demonstrate fuzz testing with AFL++. The example program reads input from a file, processes the data, and intentionally includes a potential out-of-bounds error. By using AFL++, we can generate crashes and identify flaws in the code, providing a practical introduction to fuzzing techniques and AFL++ usage.

## Getting Started

### Prerequisites

1. [`afl.rs` installed](https://github.com/rust-fuzz/afl.rs)

### Steps

1. Clone the repository:
   ```bash
   $ git clone https://github.com/BowTiedRadone/rust-aflPlusPlus
   ```
2. Build the program using `cargo afl`:

   ```bash
   $ cd rust-aflPlusPlus
   $ cargo afl build
   ```

3. Test the test cases from the `corpus` directory manually:

   ```bash
    $ cat ./corpus/test.txt
    test

    $ ./target/debug/afl-rust ./corpus/test.txt
    Buffer content: test

    $ cat ./corpus/crash.txt
    AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA

    $ ./target/debug/afl-rust ./corpus/crash.txt
    thread 'main' panicked at src/main.rs:29:36:
    index out of bounds: the len is 101 but the index is 201
    note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace
   ```

4. Instructions on how to run AFL++ against the generated binary will be provided soon!

## Conclusion

Stay tuned for updates!
