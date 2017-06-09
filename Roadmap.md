This is a non-exhaustive list of current goals made possible with the support of our generous [patrons](https://www.patreon.com/Nekotekina).

## Short term goals

* Investigate game specific bugs like the overly bright bloom in Persona 5 or the overly dark lighting in Demon’s Souls.
* Improve performance and compatibility of all renderers.
* Implement missing functionality that will fix various bugs in different games. For example, the broken shadows in many games including Demon’s Souls depend on this task.
* Automatically add disc games running from external locations to the game list.
* Parse .eh_frame section in PPU analyser and use this information in LLVM recompiler.
* Configure a buildbot to automatically upload Linux binaries.
* Investigate Linux specific bugs. Avoid using executable dir completely.
* Start to improve compatibility by fixing bugs and missing functionality.

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
* Improve SPRX loading and unloading. This increases compatibility a lot.
* Implement missing syscalls. Allow to LLE more system modules.
* Write automatic tests to minimize bugs.
* Implement savedata manager. Currently it doesn't have user interface.
* Implement precise PPU interpreter.
* Enable hardware acceleration for decryption (AES-NI). **([#2457](https://github.com/RPCS3/rpcs3/pull/2457))**

## Long term goals
* Enable higher rendering resolution to play games at any resolution, for example 4k instead of 720p in Demon’s Souls or Persona 5.
* Enable extra graphics options to support extra rendering features, such as custom anti-aliasing modes.
* Support booting from original game discs.
* Implement user manager.
* Support mic, camera, USB peripherals, etc.
* Implement network functionality.
* Implement every system module in the emulator. This will allow the emulator to work without the PS3 firmware.
* Continue to improve speed, accuracy, and compatibility. This is a never-ending goal.

## For developers
* Implement MFC_DMA_TAG_CMD_STALL_NOTIFY_EVENT and other SPU events.
* Return `error_code` from syscalls and functions to enable error reporting.
* Improve embedded debugging tools (CPU, RSX, Kernel Explorer).
* Implement simple thread pool (Thread.cpp)
* Implement BPIP for synchronization primitives.
* Implement minimalistic YAML adaptor in "C++11" style which preserves map element order.


## Completed goals
* Implemented priority-based scheduler for PPU threads. This is an important core change, fixing various crashes and freezes. **([#2349](https://github.com/RPCS3/rpcs3/pull/2349))**
* Implemented PS3 firmware installer. Users only need to provide correct PS3UPDAT.PUP file and it is automatically unpacked into /dev_flash. **([#2386](https://github.com/RPCS3/rpcs3/pull/2386), [#2398](https://github.com/RPCS3/rpcs3/pull/2398))**
* Implemented SPRX decryption on the fly **([#2367](https://github.com/RPCS3/rpcs3/pull/2367))**.
* Fixed early crashes on Linux. Now also creates dev_hdd0 and other dirs. **([#2423](https://github.com/RPCS3/rpcs3/pull/2423))**
* Cache compiled LLVM modules. You shouldn't recompile the same executable twice. **([#2432](https://github.com/RPCS3/rpcs3/pull/2432))**
* Implemented "Automatic LLE configuration" option (enabled by default). This picks the most appropriate system modules (SPRX files). It may be hard to pick them manually. **([#2459](https://github.com/RPCS3/rpcs3/pull/2459))**
* Implemented MSELF and SDAT decryption on the fly. No more temporary files and additional steps. Before some games silently failed to boot due to the presence of encrypted SDAT files. **([#2468](https://github.com/RPCS3/rpcs3/pull/2468))**
* Added ALSA core audio backend for Linux. **([#2654](https://github.com/RPCS3/rpcs3/pull/2654))**
* Controller support: DualShock 4 native support. **([#2733](https://github.com/RPCS3/rpcs3/pull/2733), [#2792](https://github.com/RPCS3/rpcs3/pull/2792))**
* GUI: Use Qt instead of wxWidgets. **([#2645](https://github.com/RPCS3/rpcs3/pull/2645))**
* Enabled Vulkan on Linux, which brought a tremendous performance improvement for some games. **([#2842](https://github.com/RPCS3/rpcs3/pull/2842))**