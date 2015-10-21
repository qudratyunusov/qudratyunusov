#### What is RPCS3 and where can I get it?
* RPCS3 is an open-source Sony PlayStation 3 emulator for Windows and Linux written in C++. It currently runs only small number of applications. The source code for RPCS3 is hosted at [GitHub](https://github.com/RPCS3/rpcs3/). You may look for [official releases](https://github.com/RPCS3/rpcs3/releases) or grab the latest compiled revisions [there](https://github.com/Bigpet/rpcs3/releases/).

#### What are the hardware requirements I need to run it?
* The requirements for running RPCS3 are still not fully known and may change a lot in its current development stage. The absolute minimum requirements for running the program are x86-64 OS, a modern x86 CPU that supports SSSE3 (and SSE4 for the recompiler) and a modern OpenGL 4.2 compatible graphics card. Integrated GPUs such as the *Intel HD Graphics* may not work correctly.

#### Does RPCS3 support commercial games? When will it support them?
* **No**. RPCS3 cannot run commercial games yet because it's in an early stage of development. A lot of features required to run commercial games still have not been implemented. Commercial games will be supported when the hardware/firmware emulation is accurate enough to run them. It all depends on the amount of developers working on this project, their skills, and free time, etc. so ignore any estimates and guesses you find out there.

#### Will RPCS3 be ported to platform *X* or include feature *Y*?
* As long as the platform is powerful enough to emulate the PlayStation 3, probably yes. However, at the moment we only target Windows and Linux. The same applies to features, if they are reasonable and requested by enough people, we will probably agree and implement it. However, for now, we consider the emulator itself our biggest priority rather than all the other secondary features (multiple languages, higher rendering resolutions, PlayStation Move support, etc.).

#### I'd like to make a patch/develop/contribute to the project.
* That's awesome, contributions are welcome! Please start by [forking the project](https://github.com/RPCS3/rpcs3/fork), then read the wiki pages (specially [Coding Style](https://github.com/RPCS3/rpcs3/wiki/Coding-Style) and [Developer Information](https://github.com/RPCS3/rpcs3/wiki/Developer-Information)), find something you want to add or improve (broken games, bugs, missing features, [Roadmap](https://github.com/RPCS3/rpcs3/wiki/Roadmap) stuff, etc.), work on it, test your changes and send a [pull request](https://help.github.com/articles/using-pull-requests). Feel free to ask any developers on [EmuNewz](http://emunewz.net/forum/forumdisplay.php?fid=162) or IRC if you have questions.

#### There is some issue/feedback/comment that I want to report
* Good, you can do it through the [Github Issue Tracker](https://github.com/RPCS3/rpcs3/issues) (development-related issues) or [Emunewz](http://www.emunewz.net/forum/forumdisplay.php?fid=162) (generic inquiries and support). Please follow this guidelines before sending anything:
  - Check if the issue is meaningful for the team (e.g. *GTAV doesn't work* is obvious and therefore useless).
  - Search older issues/threads to see if your issue was already submitted.
  - Please use an **understandable** English. It doesn't need to be perfect, but clear enough to understand your message.
  - While reporting issues, don't forget to include details about your system (OS, CPU, GPU, etc.), as well as the `RPCS3.log` file.