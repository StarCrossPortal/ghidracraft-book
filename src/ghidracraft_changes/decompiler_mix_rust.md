# Refactor: mix Rust into the decompiler

This is not intended to be read by end-user. As this "feature" does not introduce any end-user usable thing.

## Problem

Current Ghidra decompiler is old, and uses some bad practice (example like `using namespace std;`). Raw pointers and references are used without quite a guideline.

To fix this problem, we decided to introduce Rust into the decompiler architecture.

## How

This will be a very long process.
There are just too much code in the decompiler.
And they are all very complex.

So, we will do this in a long run.

### Stage 1: introduce Rust

This is now checked. By using the [cxx](https://cxx.rs/) crate, we are able to connet C++ world and Rust world.
A [build script](https://github.com/StarCrossPortal/ghidracraft/blob/master/Ghidra/Features/Decompiler/src/decompile/build.rs) is written to automate the building part.

### Stage 2: abstract away API

There are many objects used in the decompiler.
To abstract away current implementation, a new crate called [pcodecraft](https://github.com/StarCrossPortal/pcodecraft) is designed to provide the traits the original decompiler C++ side should implement.

In this way, we are able to re-write some of the algorithms in Rust gradually.
During the re-write, if the algorithm requires any API of the original decompiler, it should refer to the pcodecraft.

The pcodecraft API should be implemented in the original decompiler Rust-side code. Then we are able to integrate the re-written Rust algorithms into this project.

Currently, pcodecraft is not yet finished. Or, so to say, just started.

### Stage 3: gradually re-write some of the algorithms

This is the most complicated part. We need to re-write the algorithms one by one, in a form of crates.

To be short, in this phase, we are gonna implement every algorithms used by the decompiler, one after one, in Rust crate.
If any API is needed to fulfill the final goal, use pcodecraft.
The pcodecraft should do the rest, provide the actual implementation needed, once integrated.

In this phase, we are also able to adjust the algorithms our way. Or if you like, to experiment your own algorithms.

That is the best part of this arrangement.