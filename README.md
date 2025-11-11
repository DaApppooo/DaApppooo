
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

- Types (apart from primitives) use PascalCase, variables and constants used for intermediary results use snake_case, and global/static constants use UPPER_SNAKE_CASE.
- For methods (static or not), prefer the shortest but most explicit word possible (eg: use 'init' instead of 'create').
- Try declaring all needed variables at the begining of the function (feels a bit cleaner, especially in big functions).
- In most cases, make as much things as possible "public". Prefer `_<name>` syntax to private members.
  Users of my code (including me) must have full control over what they wanna do with the provided structures/classes/etc...
  Keeping an indication of what isn't supposed to be modified in most cases is good though.
- Prefer static constructors (in the style of rust), they're way more explicit about what you're doing and which way of constructing the type you want. When 'new' is a keyword, use 'init' instead.
- Copies must be explicit (with the `.copy()` method). Moves must be explicit (with the `.drop()` method). The defauly way of passing arguments must be C-style. In C, if you don't use a function to cleanly move or copy the object with it's allocations, the allocations will be shared. Because of this rule, rvalue-references should only be used to recieve prvalues.
- All destroyable types must have an init state. The 'init' constructor and/or method must put the type back in its init state.
- The `destroy()` member should destroy all owned attributes and modify the attributes so that this method can then be called again without risking any error.
  Usually, the value of a destroyed structure and an initialized one should be the same.
- OOP features of C++ should be avoided when possible (vtables, all types of C++ style constructors and destructors)
- Prefer C's standard library over C++'s for two main reasons:
  - More likely to need OS specific functions. This allows some optimizations for each target OS.
  - Sometimes it helps avoiding unnecessary memory allocation and/or C++'s bloat (often due to conversions between non std C++ code and std C++ code).
  - The first exception is the use of constexpr utilities like `std::copy` or `std::fill`.
  - The second exception is when there's a missing features in the c-lib that's in the c++ one.
- When writing OOP code, prefer rust's `impl` style of OOP (enums, unions and switches).
- asserts should not contain non-const methods (to avoid side-effects)
- The DEBUG flag can be enabled either:
  - During specific tests
  - At all time during development
- The FINAL flag can be enabled only if:
  - all asserts are unnecessary when the program is being ran with production input
  - no `todo()` or `TODO()` (depending on the codebase) is left
  - no `unexpected()` or `UNEXPECTED()` (depending on the codebase) is left
- The FINAL flag should transform asserts into `[[assume(...)]]`.

<sub>chessbattleadvanced</sub>
