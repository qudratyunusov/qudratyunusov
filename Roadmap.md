This is a non-exhaustive list of current goals made possible with the support of our generous [patrons](https://www.patreon.com/Nekotekina).

## Short term goals
* Fix parent of root in VFS. (Nekotekina)
* Remove obstacles for ASLR support. (Nekotekina)
* Improve PPU LLVM recompiler compatibility and speed. (Nekotekina)
* Begin SPU LLVM. (Nekotekina)
* Fix some engine-specific rendering issues (kd-11)
* Improve the shader decompiler/recompiler (kd-11)
* Fix remaining problems with texture readback (write color buffers) (kd-11)

## Medium term goals
* Improve SPU instruction accuracy for Fast Interpreter and ASMJIT
* Improve audio and video decoders for better speed and compatibility.
* Improve controller support. This includes emulated controllers (with mouse or keyboard) and real controllers as well.
* Implement LLVM recompiler backend for SPU. This is actually a tremendous amount of work to make it useful, but it will also give the very important speed improvement (unless the SPU is not used at all).
* Improve solution structure, move and rename some files.
* Implement missing syscalls. Allow to LLE more system modules.
* Write automatic tests to minimize bugs.
* Enable hardware acceleration for decryption (AES-NI). **([#2457](https://github.com/RPCS3/rpcs3/pull/2457))**
* Implement config tristate in GUI for per-game configurations.
* Improvements to the shader generation and cache system
* Implement parametrized PPU Interpreter reusing current LLVM IR generator, remove original hard-coded PPU Interpreter and make LLVM mandatory. Add options regulating its accuracy detached from the base choice of the Interpreter or the Recompiler. The same extends to SPU.

## Long term goals
* Support booting from original game discs.
* Implement user manager.
* Support mic, camera, USB peripherals, etc.
* Implement network functionality.
* Implement every system module in the emulator. This will allow the emulator to work without the PS3 firmware.

## Never-ending goals
* Improve game compatibility by fixing bugs and missing functionality.
* Continue to improve emulation speed and accuracy.
* Improve performance and compatibility of all renderers.

## For developers
* Parse .eh_frame section in PPU analyser and use this information in LLVM recompiler.
* Implement MFC_DMA_TAG_CMD_STALL_NOTIFY_EVENT and other SPU events.
* Return `error_code` from syscalls and functions to enable error reporting.
* Improve embedded debugging tools (CPU, RSX, Kernel Explorer).
* Implement BPIP for synchronization primitives.
* Cleanup the VS project files: reduce to two build types (Release and Debug), but both must use *Release* LLVM build. Debug build should include memory leak detection features.