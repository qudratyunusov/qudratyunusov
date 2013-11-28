List of features that RPCS3 will support in the future and their corresponding status. It's not required for developers to write down here the tasks they are working on. It's just recommended, and if you do so, remember to delete those entries once you finish them, or move them to another category if you couldn't do it. The current categories are:
* **Short term goals:** Tasks that developers are currently doing.
* **Medium term goals:** Stuff that developers could do.
* **Long term goals:** Tasks that are not a priority right now.

Thank you for supporting RPCS3!

***
### Short term goals
* Implement post-drawing, vfsDir and SPU: _[DH]_
* Add support for compressed SDATA files: _Hykem_
* Add support for PSARC containers: _AlexAltea_ (Stopped: Can someone send me an ELF that loads PSARCs?)
* Add unimplemented GCM commands and cellGame functions: _AlexAltea_
* Alternative Qt based GUI and replace wxWidgets datatypes with the ones of std: _xsacha_


### Medium term goals
* cellFs: Implement SDATA loader, that is, read the contents of the SDATA file on the fly.
* cellFs: Add/Improve the handling of streams and folders.
* cellJpgDec: Allow to downscale JPG images while decoding them.
* Change PKG installation directory to dev_hdd0/game.
* Implement PRX loader. (Related: http://psx-scene.com/forums/f338/prx-loader-v1-02-w-source-user-118916/)
* Implement more lv2 SysCalls.
* Find bugs and fix them.


### Long term goals
* Implement PSGL.
* Implement a JIT compiler for PPU / SPU.
* Fix wxWidgets 2.8.12 problem (See https://github.com/DHrpcs3/rpcs3/issues/6)