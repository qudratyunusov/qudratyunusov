List of features that RPCS3 will support in the future and their corresponding status. It's not required for developers to write down here the tasks they are working on. It's just recommended, and if you do so, remember to delete those entries once you finish them, or move them to another category if you couldn't do it. The current categories are:
* **Short term goals:** Tasks that developers are currently doing.
* **Medium term goals:** Stuff that developers could do.
* **Long term goals:** Tasks that are not a priority right now.

Thank you for supporting RPCS3!

***
### Short term goals
* Implement post-drawing, shaders decompiler and PPU x64 recompiler: _DH_
* Work on an asmjit-based PPU recompiler: _jfhs_
* Splitting RPCS3s project in two projects (GUI + Core): _Bigpet_
* Crypto Engine, EDATA loader and cellSpurs: _Hykem_
* Work in cellDmux, Audio and asmjit-based SPU recompiler: _NekotekinaHito_
* [PS3 Autotests](https://github.com/DHrpcs3/ps3autotests/) and PSARC containers: _AlexAltea_ (Can someone confirm me if PSARC files are handled properly?)
* Work in Audio: _Oil_


### Medium term goals
* sys_fs: Implement SDATA loader, that is, read the contents of the SDATA file on the fly.
* Replace wxWidgets datatypes inside the emulator with std ones if possible.
* **Work in RSX and add unimplemented GCM commands**.
* Implement loading SPU code from encrypted file.
* Improve RSX Debugger: Add frame stepping (pause the emulator and advance just one frame).
* Implement PRX/SPRX loader. (See also: PRX Loader v1.02, libkirk / kirk_engine, etc.)
* Fix the `libpng error: incorrect data check` error present in many homebrews like _Cubicle Shooter City_.
* Fix the ds4x.ppu.elf sample: KeyUp events are not properly handled in cellPad.
* Enable sorting by Title / Serial / etc. in the panel "_Game List_".
* Reverse cache files in /dev_hdd1/. Ask _BlackDaemon_ to get them.
* Implement new module functions. Specifically (ordered from more to less important):
    * cellJpgDec: Allow to downscale JPG images while decoding them.
* Implement more lv2 SysCalls. Specifically (ordered from more to less important):
    * 150, 154, 151 used by games like _NBA Unrivaled [NPUB30146]_.
    * 84, 88 used by games like _NBA Unrivaled [NPUB30146]_.
    * 177 used by games like _Puzzle Chronicles [NPUB30076]_.
    * 631 used by games like _Prince of Persia Classic [NPUB30031]_. (Is this function really relevant?)
    * 834 which is cellFsChmod. (Is this function really relevant?)
* Find bugs and fix them.
    * Fix PPU instructions that are broken according to [PS3 Autotests](https://github.com/DHrpcs3/ps3autotests/), like some Vector extensions and FPU stuff.
* Implement core dumps.


### Long term goals
* Add support for PSGL.
* Implement an ID Manager debugger: Useful for debugging VFS, and other ID based items. (requires a new ID Manager first).
* Improve the _Restart_ function: Some games still change their behaviour after restarting.