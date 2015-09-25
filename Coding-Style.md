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
* Don't use `/**/` for commenting out multiple lines. Use `//` on every line instead. In Visual Studio, for example, you can just select desired lines and use `Ctrl+K,C` combination to comment every line with `//`, `Ctrl+K,U` reverts this.

***
### Emulator coding style
* Module functions and lv2 syscalls:
    * Access files using *VFS* functions.
    * Return defined error codes. That is, use `return CELL_OK;` instead of `return 0;`.
    * Do **not** modify the entries in *rpcs3/Emu/SysCalls/FuncList.cpp*.
* Use only limited number of types as function arguments and result types.
    * Use `s8`, `s16`, `s32`, `s64` for signed integral types. These are aliases to `std::int8_t`, `std::int16_t`, `std::int32_t`, `std::int64_t` respectively.
    * Use `u8`, `u16`, `u32`, `u64` for unsigned integral types. These are aliases to `std::uint8_t`, `std::uint16_t`, `std::uint32_t`, `std::uint64_t` respectively.
    * Use `f32` and `f64` for floating point numbers. These are aliases to `float` and `double`.
    * Use `b8` instead of `bool`. This type is special.
    * Use `char` for UTF-8 string characters, usually as `vm::cptr<char>`. Don't treat char values as signed or unsigned numbers.
    * Function arguments and results use native endianness.
* Use `vm::ptr<>` arguments for PS3 memory pointers.
    * Pointer to the datatype `T` is `vm::ptr<T>`. For example, `void *buf` becomes `vm::ptr<void> buf`.
    * Pointer to the datatype `const T` is `vm::cptr<T>`. For example, `const char *path` becomes `vm::cptr<char> path`.
    * Pointer to the function `T(T1 arg1, ...)` is `vm::ptr<T(T1 arg1, ...)>`.
    * The function may be defined as an alias `using func_name = T(T1 arg1, ...);` and used as `vm::ptr<func_name>`.
    * Note that types `vm::ptr<u32>` and `vm::ptr<be_t<u32>>` are equal, because `be_t<>` template is implicitly applied in `vm::ptr<>` for basic types. You always work with big endian values in ps3 virtual memory, excepting some very rare cases.
    * Usual pointers (`vm::ptr`) are native-endian itself, but don't forget that dereferencing vm::ptr leads to the PS3 memory which uses big-endian values by default (if it's not known explicitly that some specific value is little-endian).
    * Pointers in PS3 memory must be big-endian: define them as `vm::bptr` or `vm::bcptr`.
* Allocate memory for temporary variables with `vm::var<>`. Under construction.
* Don't forget logging at the top of every function. Print all its arguments with `%d` or `0x%x` (always use `0x%x` if not sure).
    * Don't forget `0x` in `0x%x`. It may be really confusing.
    * Use `moduleName->Todo()` and other associated methods.
    * Use `.Todo()` method for unimplemented functions.
    * Use `.Error()` method to print error inside of function that may require user's attention. For example, some file is not found or some emulation option is not set correctly.
    * Use `.Warning()` method for partially implemented functions which still have some unimplemented functionality.
    * Use `.Notice()` method to print debug information unconditionally.
    * Use `.Log()` method for well implemented functions.
    * Don't return CELL_OK and other error codes if the function result type doesn't mean error code.
