#### What is RPCS3 and where can I get it?
* RPCS3 is an open-source Sony PlayStation 3 emulator for Windows and Linux written in C++. It currently runs some [commercial games](https://rpcs3.net/compatibility). The source code for RPCS3 is hosted on [GitHub](https://github.com/RPCS3/rpcs3/). You may grab the latest compiled revisions from [AppVeyor](https://ci.appveyor.com/project/rpcs3/rpcs3/branch/master/artifacts).

#### What are the hardware requirements I need to run it?
The requirements for running RPCS3 are still not fully known and may change a lot during its current development stage. The absolute minimum requirements for running the program are:
* **CPU:** A modern x86 CPU that supports SSSE3
* **GPU:** A modern OpenGL 4.3 compatible graphics card. Integrated GPUs such as the *Intel HD Graphics* may not work correctly. A modern DirectX 12 and Vulkan compatible graphics card is **highly** recommended.
* **OS:** Windows 7 64-bits and up, Linux 64-bits
* [Visual C++ Redistributable Packages for Visual Studio 2015](http://www.microsoft.com/en-us/download/details.aspx?id=48145)

#### Does RPCS3 support commercial games? When will it support the game I want to play?
* **Yes, some**. RPCS3 currently runs some commercial games. However, various titles can't be run yet because the emulator is in an early stage of development. Note that a lot of features required to run several commercial games still have not been implemented. Check out the [compatibility list](https://rpcs3.net/compatibility) or the [Forums](http://www.emunewz.net/forum/forumdisplay.php?fid=172) to see if there's any information on the game you want to play. More games will be supported when the hardware/firmware emulation is accurate enough to run them. It all depends on the amount of developers working on this project, their skills, and free time, etc. Ignore any estimates and guesses you find out there.

#### How can I get started using RPCS3?
* Please read the [newcomers' guide](http://www.emunewz.net/forum/showthread.php?tid=174352) on our forums for information on how to get started.

#### Will RPCS3 be ported to platform *X* or include feature *Y*?
* As long as the platform is powerful enough to emulate the PlayStation 3, probably yes. However, at the moment we only target Windows and Linux (Mac OS X is not supported at the moment because it only has OpenGL support up to 4.1 and doesn't support Vulkan). The same applies to features, if they are reasonable and requested by enough people, we will probably agree and implement it. However, for now, we consider the emulator itself our biggest priority rather than all the other secondary features (multiple languages, higher rendering resolutions, PlayStation Move support, etc.).

#### I'd like to make a patch/develop/contribute to the project.
* That's awesome, contributions are welcome! Please start by [forking the project](https://github.com/RPCS3/rpcs3/fork), then read the wiki pages (specially [Coding Style](https://github.com/RPCS3/rpcs3/wiki/Coding-Style) and [Developer Information](https://github.com/RPCS3/rpcs3/wiki/Developer-Information)), find something you want to add or improve (broken games, bugs, missing features, [Roadmap](https://github.com/RPCS3/rpcs3/wiki/Roadmap) stuff, etc.), work on it, test your changes and send a [pull request](https://help.github.com/articles/using-pull-requests). Feel free to ask any developers on [the Forums](http://emunewz.net/forum/forumdisplay.php?fid=172) or on [Discord](https://discord.me/RPCS3) if you have questions.

#### There is some issue/feedback/comment that I want to report
* Good, you can do it through the [Github Issue Tracker](https://github.com/RPCS3/rpcs3/issues) (development-related issues) or [the Forums](http://www.emunewz.net/forum/forumdisplay.php?fid=172) (general questions, support and commercial/homebrew games discussion). Please follow this guidelines before sending anything:
  - Check if the issue is meaningful for the team (e.g. *GTAV doesn't work* is obvious and therefore useless).
  - Search older issues/threads to see if your issue was already submitted.
  - Please use an **understandable** English. It doesn't need to be perfect, but clear enough to understand your message.
  - While reporting issues, don't forget to include details about your system (OS, CPU, GPU, etc.), as well as the `RPCS3.log` file.
  - When reporting issues on the forum, read [how to report issues](http://www.emunewz.net/forum/showthread.php?tid=171465).