# Introduction

![logo](./img/logo.png)

This book is part of the [bincraft](https://github.com/StarCrossPortal/bincraft) project.
In this book, we will be talking about the [ghidracraft](https://github.com/StarCrossPortal/ghidracraft) project, which is a forked version of Ghidra.

The topics covered in this book including:

- Our version of vanilla Ghidra docs: you can see this as just an unofficial documentation. Note that this won't be finished soon. see [Vanilla Ghidra](./vanilla_ghidra.md)
- Documentation about the ghidracraft changes: fixings, features, design of those fixing and features. see [Ghidracraft Changes](./ghidracraft_changes.md)
- Documentation on Ghidra internals: to help people join the development quicker. see [internals](./internals.md)

Till now, Ghidracraft is not officially released yet. The nightly build is still in progress, and should be released shortly.

If you like what we did and want to test those changes, you can always use the nightly build.
But you have to make sure you are OK with those bugs.

If you encounter any bugs that we introduce, we are happy to have you [firing issues](https://github.com/StarCrossPortal/ghidracraft/issues) about we should do next.

## Compatibility Issue

The rule of thumb is to allow any ghidra user to move to Ghidracraft without breaking things.
But it is not the other way around.

If you do import a project from Vanilla Ghidra, you may never get it back.
Currently, only pcode patch does that.

If you have serious problem about the compatibility with vanilla Ghidra, [please let us know](https://github.com/StarCrossPortal/ghidracraft/discussions).
The project is not yet fixed, so we are quite open.
If you do have many occasions that you need total forward compatibility, we might consider trying harder to achieve that.

But for now, it is a non-goal.