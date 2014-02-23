List of features that RPCS3 will support in the future and their corresponding status. It's not required for developers to write down here the tasks they are working on. It's just recommended, and if you do so, remember to delete those entries once you finish them, or move them to another category if you couldn't do it. The current categories are:
* **Short term goals:** Tasks that developers are currently doing.
* **Medium term goals:** Stuff that developers could do.
* **Long term goals:** Tasks that are not a priority right now.

Thank you for supporting RPCS3!

***
### Short term goals
* Implement post-drawing, shaders decompiler and PPU x64 recompiler: _DH_
* Work in cellPamf, cellDmux and threads, mutexes, events: _NekotekinaHito_
* Work in memory and GCM & RSX: _elisha464_
* Add support for PSARC containers: _AlexAltea_ (Stopped: Can someone send me an ELF that loads PSARCs?)
* Implement RSX Debugger: _AlexAltea_
* Alternative Qt based GUI and replace wxWidgets datatypes with the ones of std: _xsacha_
* Implement a User Account Manager: Generate and manage the directories like: */dev\_hdd0/home/00000001/*: _Oil_


### Medium term goals
* sys_fs: Implement SDATA loader, that is, read the contents of the SDATA file on the fly.
* sys_fs: Add/Improve the handling of streams.
* cellJpgDec: Allow to downscale JPG images while decoding them.
* Add unimplemented GCM commands.
* Implement loading SPU code from encrypted file.
* Implement PRX/SPRX loader. (See also: PRX Loader v1.02, libkirk / kirk_engine, etc.)
* Fix the `read: reading from stdout or stderr (fd 1 & 2) not allowed` error of some homebrews like _SNES9x for PS3_.
* Fix the `libpng error: incorrect data check` error present in many homebrews like _Cubicle Shooter City_.
* Enable sorting by Title / Serial / etc. in the panel "_Game List_".
* Reverse cache files in /dev_hdd1/. Ask _BlackDaemon_ to get them.
* Implement new module functions. Specifically (ordered from more to less important):
    * cellPamf: Used by games like _Disgaea 3: Absence of Justice_.
    * cellNet: Used by games like _Pinballistik_.
* Implement more lv2 SysCalls. Specifically (ordered from more to less important):
    * 350 used by games like _PixelJunk Eden_.
    * 82, 86, 87 used by games like _Diablo 3_.
* Implement core dumps.
* Find bugs and fix them.


### Long term goals
* Add support for PSGL.
* Implement a recompiler for SPU.
* Implement an ID Manager debugger: Useful for debugging VFS, and other ID based items. (requires a new ID Manager first).
* Implement Trophies Manager (requires a User Account Manager first).
* sys_fs: Add/Improve the handling of folders (requires vfsDir first).
* Add support for loading and running ELFs from the command line (first step to automated tests).
* Prepare _PS3 Autotests_, for automated functionality tests in new revisions:
    * PPU, SPU, RawSPU tests.
    * File tests: Open, Read, Write, Close with sys_fs.
    * Modules and lv2 SysCalls tests.
    * Vertex/Fragment recompilers tests.
* Improve the _Restart_ function: Some games still change their behaviour after restarting.