This is a non-exhaustive list of current goals made possible with the support of our generous [patrons](https://www.patreon.com/Nekotekina).

## Short term goals
* Improve SPU/PPU LLVM recompiler compatibility, add more optimizations. (Nekotekina)
* Implement parametrized PPU/SPU Interpreters reusing current LLVM IR generator, remove original hard-coded interpreters and make LLVM mandatory. Add options regulating its accuracy detached from the base choice of the Interpreter or the Recompiler. (Nekotekina)
* Make journaling VFS layer or something that fits, properly implementing some missing features like case sensitivity. (Nekotekina)
* Fix any remaining RSX regressions. (kd-11)
* RSX header restructuring. (kd-11)
* Zero-copy RSX DMA. (kd-11)
* Rewrite texture cache. (kd-11)
* Rework RSX <-> Cell synchronization framework to be more cohesive. (kd-11)

## Medium term goals
* Improve SPU instruction accuracy, investigate vectorized software FP implementation. Integrate as an option for SPU LLVM. Remove SPU Precise.
* Improve controller support. This includes emulated controllers (with mouse or keyboard) and real controllers as well.
* Improve solution structure, move and rename some files.
* Implement missing syscalls. Allow to LLE more system modules.
* Write automatic tests to minimize bugs.
* Implement config tristate in GUI for per-game configurations.
* Improvements to the shader generation and cache system
* Swich to homebrew shared_ptr<> (Nekotekina)
* Implement implicit event sending by invoking operator() with arguments for named_thread template, remove lf_queue and lf_fifo. (Nekotekina)
* Get rid of RTTI (Nekotekina)
* Improve internal profilers and statistic printers, at least ones in g_fxo. (Nekotekina)

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
* Implement MFC_DMA_TAG_CMD_STALL_NOTIFY_EVENT and other SPU events.
* Return `error_code` from syscalls and functions to enable error reporting.
* Improve embedded debugging tools (CPU, RSX, Kernel Explorer).
* Cleanup the VS project files: reduce to two build types (Release and Debug), but both must use *Release* LLVM build.