We recommend to follow these guidelines when writing code for RPCS3. They aren't very strict rules since we want to be flexible and we understand that under certain circumstances some of them can be counterproductive. Just try to follow as many of them as possible:

***
### General coding style
* Variable naming: *lower_case_underscored*
    * Globals: _g__*
    * Class members: _m__*
    * Statics: _s__*
* Avoid `#defines`, use constant variables instead.
* Put curly-brackets (`{` and `}`) on the next line.
* Try to eliminate all compiler warnings from your code.
* Try to use C++ standard data types whenever it's possible (e.g. _std::string_ instead of _wxString_).
* Comment *every* hack you do, *every* snippet you comment out and *every* improvable code.
* If you have to comment or place a commented code snippet, include the reasons to do that in the comment.

***
### Emulator coding style
* Module functions and lv2 syscalls:
    * Handle file accesses using *VFS* functions.
    * Return defined error codes. That is, use `return CELL_OK;` instead of `return 0;`.
    * Do **not** delete the entries in *rpcs3/Emu/SysCalls/FuncList.cpp* after implenting a function.
* Use only limited number of types in function arguments and result type.
    * Use `s8`, `s16`, `s32`, `s64` for integral signed types.
    * Use `u8`, `u16`, `u32`, `u64` for unsigned types.
    * Use `float`, `double` for floating point numbers. `f32` and `f64` are also available, but not widely used.
    * Use `b8` for `bool`; `char` for representing UTF-8 string character.
    * Don't use `be_t<>` in function arguments/results, they are already little-endian.
    * But don't forget that dereferencing vm::ptr for PS3 leads to big-endian values.
* Use `vm::ptr<>` arguments instead of `pointers`.
    * Pointers to the datatype `T` are `vm::ptr<T>`. For example, `void *buf` becomes `vm::ptr<void> buf`.
    * Pointers to the datatype `const T` are `vm::ptr<const T>`. For example, `const char *path` becomes `vm::ptr<const char> path`.
    * Pointers to the function `T(T1 arg1, ...)` are `vm::ptr<T(T1 arg1, ...)>`.
    * The function may be defined as `typedef T(func_name)(T1 arg1, ...);`, which becomes `vm::ptr<func_name>`.
    * Notice that `vm::ptr<u32>` and `vm::ptr<be_t<u32>>` are equal, because `be_t<>` template is implicitly applied in `vm::ptr<>` for basic types. You always work with big endian values in ps3 virtual memory, excepting some very rare cases.
* Allocate memory for temporary variables with *vm::var<>* or *vm::stackvar<>*.
    * Don't forget to switch endianness: That is, allocate `u32` with `vm::stackvar<be_t<u32>>`
* Switch endianness of constants on compile time if possible:
    * When comparing `be_t<u32> x` with the constant `y`, use: `x.data()` and `se32(y)` respectively to gain speed by switching endianness on `y` in compilation time.
    * `be_t<>.data()` method always returns the value of unsigned integer type (u16, u32, u64), as `se16()`, `se32()`, `se64()` do.
    * You are not forced to do it, especially if it decreases readability too much or you are not sure.
    * You can safely use only limited number of operations on raw big endian `.data()` or `se**()`: comparison with zero, logical bitwise `&`, `|`, `^` and `~`.
* Don't forget logging at the top of every function. Print all its arguments with `%d` or `0x%x` (always use `0x%x` if not sure).
    * Don't forget `0x` in `0x%x`. It may be really confusing.
    * Use `moduleName->Todo()` and other associated methods.
    * Use `.Todo()` method for unimplemented functions.
    * Use `.Error()` method to print error inside of function that may require user's attention. For example, some file is not found or some emulation option is not set correctly.
    * Use `.Warning()` method for partially implemented functions which still have some unimplemented functionality.
    * Use `.Notice()` method to print debug information unconditionally.
    * Use `.Log()` method for well implemented functions.
    * Don't return CELL_OK and other error codes if the function result type doesn't mean error code.
