### What is RPCS3 and where can I get it?
RPCS3 is an open-source Sony PlayStation 3 emulator for Windows and Linux written in C++. It is currently capable of booting and playing a decent amount of commercial games (see [Compatibility List](https://rpcs3.net/compatibility)), with many more to become playable with further development.
The source code for RPCS3 is hosted here on [GitHub](https://github.com/RPCS3/rpcs3/). You may grab the latest compiled revisions for Windows from [RPCS3.net](https://rpcs3.net/download).

---

### What are the system requirements I need to run it?
The requirements for running RPCS3 are still not fully known and may change a lot during its current development stage. The absolute **minimum requirements** for running the program are:
* **CPU:** An x64 CPU;
* **GPU:** An OpenGL 4.3 capable graphics card. Integrated Intel GPUs such as the *Intel HD Graphics* may not work correctly and are not supported. A modern Vulkan compatible graphics card is **highly** recommended;
* **OS:** Windows 7/8/10, Linux, BSD (Must be a 64-bits OS).

Windows only software requirements: 
* [Visual C++ 2019 Redistributable](https://aka.ms/vs/16/release/VC_redist.x64.exe);

---

### Does RPCS3 support commercial games? When will it support the game I want to play?
**Yes, some**. You can currently play hundreds of titles on RPCS3! However, a lot of titles don't work yet because the emulator is in an early stage of development and a several of the features required to run those haven't been implemented yet. 
Check out the [Compatibility List](https://rpcs3.net/compatibility) or the [Forums](https://forums.rpcs3.net) to see if there's any information on the game you want to play. More games will be supported when the hardware/firmware emulation is accurate enough to run them. It all depends on the amount of developers working on this project, their skills, and free time, etc. Ignore any estimates and guesses you find out there.

---

### How can I get started using RPCS3?
Please read the [Quickstart Guide](https://rpcs3.net/quickstart) on our website for complete information on how to get started.

---

### Can I play multiplayer games online with real consoles or other RPCS3 users?
Unfortunately, this is not something we're even remotely close to implementing just yet in RPCS3's current stage of development. Online multiplayer is something we're thinking about, but we may not focus on it until RPCS3 is as stable and as accurate as possible. 

Playing games online with real PlayStation 3 systems would require the user to connect to PlayStation Network which isn't very feasible due to obvious technical and legal limitations.

---

### Can I play local-multiplayer games with RPCS3?
Local-multiplayer is completely possible. We support up to 7 concurrent controllers (just like the PlayStation 3) with a flexible system: these controllers can be mixed so that one player uses the keyboard, while a 2nd one uses a gamepad. This setting is found under the menu Configuration > Pads.

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
Good, you can do it through the [GitHub Issue Tracker](https://github.com/RPCS3/rpcs3/issues) (development-related issues) or the [Forums](https://forums.rpcs3.net) (general questions, support and commercial/homebrew games discussion). Please follow this guidelines before sending anything:
- Check if your system matches all the system minimum requirements;
- Check if the issue is meaningful for the team (e.g. The Last of Us doesn't work is obvious and therefore useless);
- Search older issues/forum threads to see if your issue was already submitted;
- Use understandable English. It doesn't need to be perfect, but clear enough to understand your message;
- While reporting issues, don't forget to include details about your system (OS, CPU, GPU, etc.), as well as the RPCS3.log file.