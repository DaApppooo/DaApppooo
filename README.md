
# 💜 Hi there 👋

## All about me

> I'm a dev who <3 everything about `computers` and $math$ (social sciences are cool also !).

I handle a bunch of different languages, mainly python for prototyping and then
C or C++ for production.

I **LOVE** learning about new stuff, and I usually code a lot in my spare time. I've been coding for about 8 years now. I'm a CS student and I'm going for a CS PhD. Most of my projects are on private repos.
I'm really interesed in low-level stuff.

When I'm bored I really like doing little games or simulations with [Raylib](https://github.com/raysan5/raylib).

## For binge coding

See my little python script [tmpc](https://github.com/DaAppoxy/tmpc-bm).

## My programming ruleset and expected behavior (some of these only apply for C++)

> Applied *most of the time* in my own work

- In most cases, make as much things as possible "public". Prefer `_<name>` syntax to private members.
  User of my code (including me) must have full control over what they wanna do with the provided structures/classes/etc...
  Keeping an indication of what isn't supposed to be modified in most cases is good though.
- The `init()` member should initialize a structure in the simplest way: no allocation, no references to external objects, no argument.
  The initialized value can then be destroyed without errors.
- The `destroy()` member should destroy all owned attributes and modify the attributes so that this method can then be called again without risking any error.
  Usually, the value of a destroyed structure and an initialized one should be the same.
- To alloc necessary memory (after a call to `init()` and a possible initial setup), use `alloc()`
- To transform a reference into a new owned object use `realloc()`.
- OOP features of C++ should be avoided when possible (vtable, all types of C++ style initialization methods, C++ style destructor method)
  - To copy, use the `copy()` method. (or `deepcopy()` if it makes sense in context)
  - Move is the default
- Make all ownership operations manual and explicit:
  - To give ownership, use `disown()` (or `drop()`).
  - To take ownership, use `own()` (or `hold()`).
  - To give a reference, use `ref()`.
- Prefer C's standard library over C++'s for two main reasons:
  - More likely to need OS specific functions. This allows some optimizations for each target OS.
  - Sometimes help avoid unnecessary memory allocation and/or C++'s bloat (often due to conversions between non std C++ code and std C++ code).
- Avoid OOP approach, and when OOP is used, prefer rust's `impl` style of OOP (enums, unions and switches).
- The DEBUG flag can be enabled either:
  - During specific tests
  - At all time during development
- The PRODUCTION flag can be enabled only if:
  - most asserts are unnecessary when the program is being ran with production input
  - other safety checks have been tested and do not occur
