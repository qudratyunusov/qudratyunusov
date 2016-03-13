List of features that RPCS3 will support in the future and their corresponding status. It's not required for developers to write down here the tasks they are working on. It's just recommended, and if you do so, remember to delete those entries once you finish them, or move them to another category if you couldn't do it. The current categories are:
* **Short term goals:** Tasks that developers are currently doing.
* **Medium term goals:** Stuff that developers could do.
* **Long term goals:** Tasks that are not a priority right now.

Thank you for supporting RPCS3!

***
## Short term goals
* Rewriting OpenGL renderer, VP/FP recompiler. _[DH]_
* Implement Priority-Based Scheduler for PPU Threads. _Nekotekina_
* Implement/rewrite HLE modules: _tambre_
    * cellJpgDec: Use a better library, bugfixes, other improvements
    * cellFont: Use libtiff to properly decode and support font files
* Correctly handle exceptions in `Emulator::Load()` and `Emulator::Stop()` functions. Not important.
* Add basic types `s128` (signed 128-bit number), `v64` (vector 64-bit union), `v32` (vector 32-bit union). Not important.
* Improve `be_t` and `le_t` types, make them perfect and literally shine. Any flaws are intolerable.
* Filesystem: Process WinAPI/errno error codes if an error occured in system calls called through `fs::` functions. Set correct TLS error code. Throw an exception on unknown error. Reuse error codes when necessary, for example, in `sys_fs_open` implementation.
* Cease to use `assert` in most places whenever an error may occur. Use exceptions.
* Eliminate `delete`/`delete[]` operator usage. Eliminate `malloc`/`free` usage. Use `std::unique_ptr` instead.
* Implement correct SPU segment loading in order to provide correct `sys_spu_image_import`, `sys_raw_spu_load`, `sys_spu_elf_get_information`, `sys_spu_elf_get_segments`, etc. implementations.
* Examine PPU/SPU/ARMv7 stack structure. Restore the "callstack" in the debugger using the information from the real thread's stack, using SP register. Catching it from branch instructions was: 1) wrong 2) slow.
* Improve `vm::reservation_op`: use TSX intrinsics if supported (by CPUID).
* Eliminate `std::this_thread` `sleep_for()` and `yield()` usage in most places, because it's ineffective or even wrong.
* Eliminate wx dependencies from emucore.


## Medium term goals
* Improve solution structure.
* Correctly load EXPORT table of main PPU executable.
* Implement variable import/export support (VNIDs) for PPU.
* Improve all PRX-related things. Fix booting process in order to be compatible with liblv2. This includes TLS, correct module loading/unloading and various unimplemented syscalls.
* Improve debugger, fix bugs.
* Implement static AOT PPU recompiler.
* Implement AOT SPU recompiler.
* Implement block-based ARMv7 disassembler.
* Implement static AOT ARMv7 recompiler.
* Implement variable import support (VNIDs) for ARMv7.
* Implement SDATA loader, that is, read the contents of the SDATA file on the fly.
* Improve RSX and add unimplemented GCM commands.
* Implement loading SPU code from encrypted file.
* Improve RSX Debugger: Add frame stepping (pause the emulator and advance just one frame).
* Implement LV2 SysCalls. Specifically (ordered from more to less important):
    * 631 used by games like _Prince of Persia Classic [NPUB30031]_
    * sys_fs_chmod (834)
* Find bugs, wrong [autotests](https://github.com/DHrpcs3/ps3autotests/) or read the current [issues](https://github.com/DHrpcs3/rpcs3/issues) and fix them.
* Implement core dumps.
* Implement Priority-Based Scheduler for SPU Thread Groups.
* Write tests.


## Long term goals
* Add a User Manager to manage folders like: `dev_hdd0/home/00000001`.
* Implement a driver to use HPET (High Precision Event Timer) hardware in emulator if possible.