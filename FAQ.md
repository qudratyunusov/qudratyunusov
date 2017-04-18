### What is RPCS3 and where can I get it?
RPCS3 is an open-source Sony PlayStation 3 emulator for Windows and Linux written in C++. It is currently capable of booting and playing a decent amount of commercial games (see [Compatibility List](https://rpcs3.net/compatibility)), with many more to become playable with further development.
The source code for RPCS3 is hosted here on [GitHub](https://github.com/RPCS3/rpcs3/). You may grab the latest compiled revisions for Windows from [AppVeyor](https://ci.appveyor.com/project/rpcs3/rpcs3/branch/master/artifacts).

---

### What are the system requirements I need to run it?
The requirements for running RPCS3 are still not fully known and may change a lot during its current development stage. The absolute minimum requirements for running the program are:
* **CPU:** A modern x86 CPU that supports SSSE3;
* **GPU:** A modern OpenGL 4.3 compatible graphics card. Integrated GPUs such as the *Intel HD Graphics* may not work correctly. A modern DirectX 12 and Vulkan compatible graphics card is **highly** recommended;
* **OS:** Windows 7 x64 and up or Linux x64.

Windows only software requirements: 
* [Visual C++ Redistributable Packages for Visual Studio 2015](http://www.microsoft.com/en-us/download/details.aspx?id=48145);
* [DirectX End-User Runtime Web Installer](https://www.microsoft.com/en-us/download/details.aspx?id=35). 

---

### Does RPCS3 support commercial games? When will it support the game I want to play?
**Yes, some**. You can currently play dozens of titles on RPCS3! However, most titles don't work yet because the emulator is in an early stage of development and a lot of features required to run those haven't been implemented yet. 
Check out the [Compatibility List](https://rpcs3.net/compatibility) or the [Forums](http://www.emunewz.net/forum/forumdisplay.php?fid=172) to see if there's any information on the game you want to play. More games will be supported when the hardware/firmware emulation is accurate enough to run them. It all depends on the amount of developers working on this project, their skills, and free time, etc. Ignore any estimates and guesses you find out there.

---

### How can I get started using RPCS3?
Please read the [Quickstart Guide](https://rpcs3.net/quickstart) on our website for complete information on how to get started.

---

### Can I play multiplayer games online with real consoles or other RPCS3 users?
Unfortunately, this is not something we're even remotely close to implementing just yet in RPCS3's current stage of development. Online multiplayer is something we're thinking about, but we may not focus on it until RPCS3 is as stable and as accurate as possible. 

Playing games online with real PlayStation 3 systems would require the user to connect to PlayStation Network which isn't very feasible due to obvious technical and legal limitations.

---

### Can I play local-multiplayer games with RPCS3?
We currently do not have support for multiple controllers in RPCS3 just yet, but we plan to in the future once we're farther in development. The foundation for multiple controllers is already there, but it just isn't priority for now. 

Similarly to how the a PlayStation 3 has support for up to 7 concurrent controllers, we plan to replicate that feature in its entirety.

---

### Can I import my save data from my real PlayStation 3?
Yes, saves can be imported from a real PlayStation 3 system using the standard USB flash drive transfer method. Due to how the user account system works on a real PlayStation 3 system, in some cases, you may need to re-sign your save. 

For more information on how to manage your save data within RPCS3, please refer to the [Quickstart Guide](https://rpcs3.net/quickstart).

---

### Will RPCS3 be ported to platform *X* or include feature *Y*?
As long as the platform is powerful enough to emulate the PlayStation 3, probably yes. 

At the moment we only target Windows and Linux. macOS is not supported at the moment because it only supports up to OpenGL 4.1 and doesn't support Vulkan either. The same applies to additional features. If they are reasonable and are requested by enough people, we will most likely agree and implement it. 

For now, we consider the emulator itself our biggest priority rather than all the other secondary features such as GUI translations, higher rendering resolutions, PlayStation Move support, etc.

---

### I'd like to create a patch, contribute, or possibly become a developer. Where do I start?
That's awesome, contributions are welcome! Check the [Coding Style Guidelines](https://github.com/RPCS3/rpcs3/wiki/Coding-Style), and [Developer Information](https://github.com/RPCS3/rpcs3/wiki/Developer-Information).

Find something you want to implement or improve (such as broken games, bugs, missing features, [Roadmap](https://github.com/RPCS3/rpcs3/wiki/Roadmap) goals, etc.), work on it, test your changes and send a [Pull Request](https://help.github.com/articles/using-pull-requests).

If you have any questions, hit us up on our [Discord Server](https://discord.me/RPCS3) in the **#development** channel.

---

### There is some issue/feedback/comment that I want to report.
Good, you can do it through the [GitHub Issue Tracker](https://github.com/RPCS3/rpcs3/issues) (development-related issues) or the [Forums](http://www.emunewz.net/forum/forumdisplay.php?fid=172) (general questions, support and commercial/homebrew games discussion). Please follow this guidelines before sending anything:
- Check if your system matches all the system minimum requirements;
- Check if the issue is meaningful for the team (e.g. The Last of Us doesn't work is obvious and therefore useless);
- Search older issues/forum threads to see if your issue was already submitted;
- Use understandable English. It doesn't need to be perfect, but clear enough to understand your message;
- While reporting issues, don't forget to include details about your system (OS, CPU, GPU, etc.), as well as the RPCS3.log file.