This is a non-exhaustive list of current goals made possible with the support of our generous [patrons](https://www.patreon.com/Nekotekina).

## Short term goals
* Implement MSELF support without intermediate files. Currently it doesn't work at all. Depends on "decryption on the fly" task. **(WIP by [jarveson](https://github.com/jarveson))**
* Enable hardware acceleration for decryption (AES-NI). **(WIP by [cornytrace](https://github.com/cornytrace), [#2457](https://github.com/RPCS3/rpcs3/pull/2457))**
* Implement decryption on the fly. No more temporary files and additional steps. This affects, for example, EBOOT, SELF, EDAT, and MSELF embedded files.
* Implement SDAT decryption. No need to decrypt them manually. Currently some games may silently fail to boot.
* Parse .eh_frame section in PPU analyser and use this information in LLVM recompiler.
* Configure Travis to automatically upload Linux binaries on GitHub.
* Investigate Linux specific bugs. Avoid using executable dir completely.
* Start to improve compatibility by fixing bugs and missing functionality.

## Medium term goals
* Improve audio and video decoders for better speed and compatibility.
* Improve controller support. This includes emulated controllers (with mouse or keyboard) and real controllers as well.
* Enable Vulkan graphic renderer for Linux.
* Add low-latency ASIO audio backend for Windows. With ASIO4ALL, it will work great on most modern hardware.
* Add core audio backend for Linux.
* Implement LLVM recompiler backend for SPU. This is actually a tremendous amount of work to make it useful, but it will also give the very important speed improvement (unless the SPU is not used at all).
* Improve LLVM flexibility. For example, it could scan game folder for all executables and SPRX modules and recompile them ahead of time.
* Implement PPU executable chain-loading.
* Improve solution structure, move and rename some files.
* Improve SPRX loading and unloading. This increases compatibility a lot.
* Implement missing syscalls. Allow to LLE more system modules.
* Write automatic tests to minimize bugs.
* Implement savedata manager. Currently it doesn't have user interface.
* GUI: Use Qt instead of wxWidgets.
* Implement precise PPU interpreter.

## Long term goals
* Support booting from original game discs.
* Implement user manager.
* Support mic, camera, USB peripherals, etc.
* Implement network functionality.
* Implement every system module in the emulator. This will allow the emulator to work without the PS3 firmware.
* Continue to improve speed, accuracy, and compatibility. This is a never-ending goal.

## For developers
* Fix undefined behaviour in bf_t (signed shift).
* Implement MFC_DMA_TAG_CMD_STALL_NOTIFY_EVENT and other SPU events.
* Return `error_code` from syscalls and functions to enable error reporting.
* Improve embedded debugging tools (CPU, RSX, Kernel Explorer).
* Implement simple thread pool (Thread.cpp)
* Implement MFC thread for SPU DMA and other time-critical tasks.
* Fetch memory attributes in sys_memory_get_page_attribute.
* Implement BPIP for synchronization primitives.
* Implement minimalistic YAML adaptor in "C++11" style which preserves map element order.


## Completed goals
* Implemented priority-based scheduler for PPU threads. This is an important core change, fixing various crashes and freezes. **([#2349](https://github.com/RPCS3/rpcs3/pull/2349))**
* Implemented PS3 firmware installer. Users only need to provide correct PS3UPDAT.PUP file and it is automatically unpacked into /dev_flash. **([#2386](https://github.com/RPCS3/rpcs3/pull/2386), [#2398](https://github.com/RPCS3/rpcs3/pull/2398))**
* Implemented SPRX decryption on the fly ([#2367](https://github.com/RPCS3/rpcs3/pull/2367)).
* Fixed early crashes on Linux. Now also creates dev_hdd0 and other dirs. **([#2423](https://github.com/RPCS3/rpcs3/pull/2423))**
* Cache compiled LLVM modules. You shouldn't recompile the same executable twice. **([#2432](https://github.com/RPCS3/rpcs3/pull/2432))**
* Implemented "Automatic LLE configuration" option (enabled by default). This picks the most appropriate system modules (SPRX files). It may be hard to pick them manually. **([#2459](https://github.com/RPCS3/rpcs3/pull/2459))**