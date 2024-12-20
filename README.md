# Unexpected Behavior When Modifying a Vector via Raw Pointers

This repository demonstrates a subtle bug in Rust that can occur when modifying a vector using raw pointers.  The seemingly straightforward code manipulates the vector's first element directly through a raw pointer. However, this approach circumvents Rust's memory safety mechanisms and can lead to undefined behavior or a panic if the modified value exceeds the vector's capacity.

The `bug.rs` file contains the problematic code, while `bugSolution.rs` provides a corrected version that utilizes safe Rust idioms.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's root directory.
3. Compile and run `bug.rs` using `rustc bug.rs && ./bug`.
4. Observe the unexpected output or potential panic.
5. Repeat steps 3 and 4 with `bugSolution.rs` to see the corrected behavior.

## Discussion

This example highlights the importance of understanding Rust's ownership and borrowing system. Directly manipulating memory through raw pointers should be avoided unless absolutely necessary, and even then, extreme caution is required to prevent memory safety violations. Using safe, idiomatic Rust constructs is always preferred.