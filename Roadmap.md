List of features that RPCS3 will support in the future and their corresponding status. It's not required for developers to write down here the tasks they are working on. It's just recommended, and if you do so, remember to delete those entries once you finish them, or move them to another category if you couldn't do it. The current categories are:
* **Short term goals:** Tasks that developers are currently doing.
* **Medium term goals:** Stuff that developers could do.
* **Long term goals:** Tasks that are not a priority right now.

Thank you for supporting RPCS3!

***
### Short term goals
* Rewriting VP/FP recompiler: _[DH]_


### Medium term goals
* Implement SDATA loader, that is, read the contents of the SDATA file on the fly.
* Improve RSX and add unimplemented GCM commands.
* Implement loading SPU code from encrypted file.
* Improve RSX Debugger: Add frame stepping (pause the emulator and advance just one frame).
* Implement various HLE functions. Specifically (ordered from more to less important):
    * cellJpgDec: Allow to downscale JPG images while decoding them.
* Implement LV2 SysCalls. Specifically (ordered from more to less important):
    * 631 used by games like _Prince of Persia Classic [NPUB30031]_
    * sys_fs_chmod (834)
* Find bugs, wrong [autotests](https://github.com/DHrpcs3/ps3autotests/) or read the current [issues](https://github.com/DHrpcs3/rpcs3/issues) and fix them.
* Implement core dumps.


### Long term goals
* Add a User Manager to manage folders like: `dev_hdd0/home/00000001`.