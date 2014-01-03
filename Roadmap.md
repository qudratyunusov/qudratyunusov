List of features that RPCS3 will support in the future and their corresponding status. It's not required for developers to write down here the tasks they are working on. It's just recommended, and if you do so, remember to delete those entries once you finish them, or move them to another category if you couldn't do it. The current categories are:
* **Short term goals:** Tasks that developers are currently doing.
* **Medium term goals:** Stuff that developers could do.
* **Long term goals:** Tasks that are not a priority right now.

Thank you for supporting RPCS3!

***
### Short term goals
* Implement post-drawing, shaders, PPU recompiler, vfsDir and improve SPU: _[DH]_
* Add support for compressed SDATA files: _Hykem_
* Work in SPU: _NekotekinaHito_ (_Magn3s1um:_ Have you uncommited changes?)
* Add support for PSARC containers: _AlexAltea_ (Stopped: Can someone send me an ELF that loads PSARCs?)
* Implement cellFont and RSX Debugger: _AlexAltea_
* Alternative Qt based GUI and replace wxWidgets datatypes with the ones of std: _xsacha_


### Medium term goals
* cellFs: Implement SDATA loader, that is, read the contents of the SDATA file on the fly.
* cellFs: Add/Improve the handling of streams and folders.
* cellJpgDec: Allow to downscale JPG images while decoding them.
* Add unimplemented GCM commands.
* Implement PRX loader. (See also: PRX Loader v1.02, libkirk / kirk_engine, etc.)
* Fix the `libpng error: IHDR: CRC error` error present in many homebrews like _Cubicle Shooter City_.
* Enable sorting by Title / Serial / etc. in the panel "_Game List_".
* Implement new module functions. Specifically:
    * cellPamf: cellPamfGetHeaderSize used by games like _Disgaea 3: Absence of Justice_.
* Implement more lv2 SysCalls. Specifically:
    * 82, 86, 87 used by games like _Diablo 3_.
* Find bugs and fix them.


### Long term goals
* Add support for PSGL.
* Implement a dynamic recompiler for SPU.
* Fix wxWidgets 2.8.12 problem (See https://github.com/DHrpcs3/rpcs3/issues/6)