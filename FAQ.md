**What is RPCS3?**
> RPCS3 is an open-source Sony PlayStation 3 emulator for Windows written in C++. It currently runs only small homebrew applications. The source code for RPCS3 is hosted at: https://github.com/DHrpcs3/rpcs3/

**Where can I get it?**
> There are more then one place to download RPCS3 builds, we recommend getting it at: https://github.com/DHrpcs3/rpcs3/releases

**What do I need to run it?**
> The requirements for running RPCS3 are still not fully known and may change a lot in its current development stage. The absolute minimum requirements for running the program are a modern CPU that supports SSE and a OpenGL 3.3 compatible graphics card.

**Why doesn't RPCS3 support commercial games? Will it support them in the future?**
> RPCS3 cannot run commercial games yet because it's on an early stage of development. A lot of features required to run commercial games still have not been implemented. Commercial games will be supported when the hardware emulation is accurate enough to run them.

**How can I decrypt SELF files? Why do I get the `scetool: Cound not load keys` error?**
> All the commercial games and the signed homebrew have their main executable encrypted (SELF) and it's usually named: *EBOOT.BIN*. In order to run these games, RPCS3 needs a key to decrypt them. Due to copyright reasons, you have to obtain a **legal** copy of the SELF decryption keys and place them in a folder named "*data*" next to the RPCS3 executable in a format that is readable for *scetool*. In the end, you should have three files inside this folder named: "*keys*", "*ldr_curves*" and "*vsh_curves*".

**Will RPCS3 be ported to platform X?**
> As long as this platform is powerful enough to emulate the PlayStation 3, yes, there is a high chance that RPCS3 will be ported there. However, at the moment we only target Windows and Linux.

**Will RPCS3 include feature X?**
> If that feature is feasible and requested by enough people, we will probably agree and implement it. However, for now we consider the emulator itself our biggest priority rather than all the other secondary features (language selector, higher rendering resolutions, PlayStation Move support, etc.).

**How many time will you need until RPCS3 boots a commercial game successfully?**
> You can safely ignore any estimation you find on the Internet: There is no accurate answer for this. It all depends on the amount of developers working on this project, their skills and free time among many other parameters.