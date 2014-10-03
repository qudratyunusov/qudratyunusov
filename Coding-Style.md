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
* Module functions and lv2 SysCalls:
    * Handle file accesses using *VFS* functions.
    * Return defined error codes. That is, use `return CELL_OK;` instead of `return 0;`.
    * Do **not** delete the entries in *rpcs3/Emu/SysCalls/FuncList.cpp* after implenting a function.
* Use `mem*_t` arguments instead of `u32 *_addr`.
    * Pointers to `u8`, `u16`, `u32`, `u64` are respectively `mem8_t`, `mem16_t`, `mem32_t`, `mem64_t`.
    * Pointers to the datatype `T` are `mem_ptr_t<T>`.
    * Pointers to the function `T (*)(t1 a1, t2 a2)` are `mem_func_ptr_t<T (*)(t1 a1, t2 a2)>`
* Allocate memory with *MemoryAllocator*.
    * Don't forget to switch endianness: That is, allocate `u32` with `MemoryAllocator<be_t<u32>>`
* Switch endianness of constants on compile time if possible:
    * When comparing `be_t<u32> x` with the constant `y`, use: `x.ToBE()` and `se32(y)` respectively to gain speed by switching endianness on `y` in compilation time.