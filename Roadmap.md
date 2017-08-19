This is a non-exhaustive list of current goals made possible with the support of our generous [patrons](https://www.patreon.com/Nekotekina).

## August 2017
* Add "Clear LLVM cache" function.
* Fix log appearance at RPCS3 startup. (Nekotekina)
* Improve fatal error dialog. (Nekotekina)
* Implement sys_net syscalls. (Nekotekina)
* Implement remaining syscalls for liblv2. (Nekotekina)

## September 2017
* Rebuild LLVM cache for the firmware after its installation. (Nekotekina)
* Fix parent of root in VFS. (Nekotekina)
* Remove obstacles for ASLR support. (Nekotekina)
* Improve PPU LLVM recompiler compatibility and speed. (Nekotekina)
* Begin SPU LLVM. (Nekotekina)

## Medium term goals
* Properly support some PS3 features like MSAA that are lacking at the moment.
* Implement RSX reports which are missing at the moment.
* Improve audio and video decoders for better speed and compatibility.
* Improve controller support. This includes emulated controllers (with mouse or keyboard) and real controllers as well.
* Add low-latency ASIO audio backend for Windows. With ASIO4ALL, it will work great on most modern hardware.
* Implement LLVM recompiler backend for SPU. This is actually a tremendous amount of work to make it useful, but it will also give the very important speed improvement (unless the SPU is not used at all).
* Improve LLVM flexibility. For example, it could scan game folder for all executables and SPRX modules and recompile them ahead of time.
* Implement PPU executable chain-loading.
* Improve solution structure, move and rename some files.
* Implement missing syscalls. Allow to LLE more system modules.
* Write automatic tests to minimize bugs.
* Implement savedata manager. Currently it doesn't have user interface.
* Implement (the rest of) precise PPU Interpreter.
* Enable hardware acceleration for decryption (AES-NI). **([#2457](https://github.com/RPCS3/rpcs3/pull/2457))**

## Long term goals
* Enable higher rendering resolution to play games at any resolution, for example 4k instead of 720p in Demon’s Souls or Persona 5.
* Enable extra graphics options to support extra rendering features, such as custom anti-aliasing modes.
* Build PPU/SPU interpreters at runtime using LLVM.
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
* Implement simple thread pool (Thread.cpp)
* Implement BPIP for synchronization primitives.
* Cleanup the VS project files: reduce to two build types (Release and Debug), but both must use *Release* LLVM build. Debug build should include memory leak detection features.