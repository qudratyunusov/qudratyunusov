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

***
### Emulator coding style
* Module functions and lv2 SysCalls:
    * Handle file accesses using *VFS* functions.
    * Return defined error codes. That is, use `return CELL_OK;` instead of `return 0;`.
* Use `mem*_t` arguments instead of `u32 *_addr`.
    * Pointers to `u8`, `u16`, `u32`, `u64` are respectively `mem8_t`, `mem16_t`, `mem32_t`, `mem64_t`.
    * Pointers to the datatype `foo` are `mem_ptr_t<foo>`.
* Allocate memory with *MemoryAllocator*.
    * Don't forget to switch endianness: That is, allocate `u32` with `MemoryAllocator<be_t<u32>>`