
# 💜 Hi there 👋

## _`$ whoami`_ ?

> I'm a dev who ❤️ everything about `computers` and $math$ (social sciences are cool also).

I handle a bunch of different languages, mainly python for prototyping and then
C or C++ for production.

I **LOVE** learning about new stuff, and I usually code a lot in my spare time.

I started my journey with computers when I was 10 with unity copying and pasting code around,
then I learned python when I was 12, and now I'm working on a bunch of different projects.
My biggest is the [_Da Programing Language_](https://github.com/TheDaProject) (a highly customizable C
with modern cool features). I'm currently solo-ing this project, but if someone wants to join: do not
hesitate. Also, I'm heading toward a CS PhD.

When I'm bored I really like doing little games or simulations with [Raylib](https://github.com/raysan5/raylib).

## For binge coding

See my little python script [tmpc](https://github.com/DaAppoxy/tmpc-bm).

## My C++ rules and expected behavior

> Applied *most of the time* in my own work

- In most cases, make as much things public. Prefer `_<name>` syntax to private members.
  User of my code (including me) must have full control over what they wanna do with the provided structures/classes/etc...
  Keeping an indication of what isn't supposed to be modified in most cases is good though.
- The `init()` member should initialize a structure in the simplest way: no allocation, no references to external objects, no argument.
  The initialized value can then be destroyed without errors.
- The `destroy()` member should destroy all owned attributes and modify the attributes so that this method can then be called again without risking any error.
  Usually, the value of a destroyed structure and an initialized one should be the same.
- OOP features of C++ should be avoided when possible (vtable, all types of C++ style initialization methods, C++ style destructor method)
  To copy, use the `copy()` method. (or `deepcopy()` if it makes sense in context)
  To give ownership, use `disown()`.
  To take ownership, use `own()`.
  To explicitly 
