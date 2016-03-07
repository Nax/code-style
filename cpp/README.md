# C++ Code Style

> These guidelines apply to C++11

## Table Of Contents

## Files
* Use `.hpp` for headers and `.cpp` for source files.
* Always implement `main` in `main.cpp`.
* As an exception, if the project consist of one file, define `main` in `<ProjectName>.cpp`.
* Nothing but `main` and static functions should be defined in `main.cpp`.
* Never, ever create a `main.hpp` file.
* Every filename but `main.cpp` should be in `UpperCamelCase`. This does not apply to one-file projects.
* Headers serving as entry points to a module may be extensionless (Math instead of Math.hpp).
* When creating a library, put every public header in `include/<ModuleName>/<PossibleSubdirectories>`.
* When the target is an executable, mix `.cpp` and `.hpp` files.

## Preprocessor
* Never, ever include a `.cpp` file.
* Always create header guards as follow:

```c++
#ifndef LIBRARY_MODULE_FILE_EXT
#define LIBRARY_MODULE_FILE_EXT

(...)

#endif
```

* Don't use #pragma once
* Avoid macros when possible.
* Still, use macros when they clarify the intent of your code.
* Always put `()` around macro parameters, unless you want to stringify or tokenize them.
* Avoid creating macros which evaluates they arguments twice or more.
* Always prefix your macros, to avoid any clash.
* Macros should be `UPPER_SNAKE_CASE`.

## Whitespaces
* Use 4 spaces wide soft tabs.
* No trailing whitespaces.
* Always append a newline at the end of a file.
* Put a space around binary operators.
* Put a space after `if`, `else if`, `for`, `while`.
* Put a space and do not use parens after a `return`.
* Do not, however, put a space when returning from a `void` function.
* Put a space, and don't use parens after `sizeof`.
* Don't put a space between a function's name and the opening paren.

## Namespaces
* No `using namespace` in global scope in header files.
* When the target is a library, put everything in a library-wide namespace.
* Library-wide namespace should be `lowercase` only. No underscores.
* Namespaces that provide a service (a group of related functions, or scoped weak enums) should be `UpperCamelCase`.
* Use of `using namespace` is accepted in a source file, for a library-wide namespace.
* A `priv` namespace should be used when exposing implementation details in a header file. This is mostly for templates or inlined code.
* Always indent a namespaced block. Always put the `{` on it's own line.

```c++
// Bad
namespace Math {

class Vector (...)

}

// Good
namespace Math
{
    class Vector (...)
}
```

* Avoid service namespaces containing only classes. Prefer to use a prefix instead.
* Never add new elements to `std`, except specializations, and do so with care.

## Functions
* Put the function's type on it's own line in the definition.
* Put the function's type  in the same line in the declaration.
* Insert a newline before the opening `{`.
* Always make `main` following this exact signature, including arguments names: `int main(int argc, char** argv)`

```c++
// Bad
void main () {

}

// Good
int
main(int argc, char** argv)
{

}
```

* Never use `WinMain`, or `mainw`. Force the use of `main` instead.
* Always declare a function `static` when it's not exported.
* Never declare a standalone `static` function in headers.

## Code
* Use `for` over `while` when it clarify the intent of your code.
* Use `for (;;)` as infinite loops.
* Avoid using `goto`, unless you have a very good reason to use it.
* 
