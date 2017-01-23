## Short term goals
* Implement PS3 firmware installer. Users only need to provide correct PS3UPDAT.PUP file and it will be automatically unpacked into /dev_flash.
* Implement decryption on the fly. No more temporary files and additional steps. This affects, for example, EBOOT, SELF, SPRX, EDAT, and MSELF embedded files.
* Implement SDAT decryption. No need to decrypt them manually. Currently some games may silently fail to boot.
* New "Automatic LLE configuration" option (enabled by default). This will pick the most appropriate system modules (SPRX files) for a particular PS3 executable. It may be hard to pick them manually.
* Cache compiled LLVM modules. You shouldn't recompile the same executable twice.
* Configure Travis to automatically upload Linux binaries on GitHub.
* Implement priority-based scheduler for PPU threads. This is an important core change, it will fix various crashes and freezes.
* Investigate early crashes on Linux.
* Start to improve compatibility by fixing bugs and missing functionality.

## Medium term goals
* Enable hardware acceleration for decryption (AES-NI).
* Improve audio and video decoders for better speed and compatibility.
* Implement MSELF support without intermediate files. Currently it doesn't work at all. Depends on "decryption on the fly" task.
* Improve controller support. This includes emulated controllers (with mouse or keyboard) and real controllers as well.
* Enable Vulkan graphic renderer for Linux.
* Add low-latency ASIO audio backend for Windows. With ASIO4ALL, it will work great on most modern hardware.
* Add core audio backend for Linux.
* Implement LLVM recompiler backend for SPU. This is actually a tremendous amount of work to make it useful, but it will also give the very important speed improvement (unless the SPU is not used at all).
* Improve LLVM flexibility. For example, it could scan game folder for all executables and SPRX modules and recompile them ahead of time.
* Implement PPU executable chain-loading.
* Improve solution structure, move and rename some files.
* Improve SPRX loading and unloading. This increases compatibility a lot.
* Improve embedded debugger.
* Implement missing syscalls. Allow to LLE more system modules.
* Write automatic tests to minimize bugs.
* Implement savedata manager. Currently it doesn't have user interface.

## Long term goals
* Implement user manager.
* Implement network functionality.
* Implement every system module in the emulator. This will allow the emulator to work without the PS3 firmware.
* Continue to improve speed, accuracy, and compatibility. This is a never-ending goal.