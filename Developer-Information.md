If you are wondering about websites and documents in order to gather information about certain parts of the PlayStation 3 here is a nice list to start with. Probably more things should be added here, but for now it is a good compilation of useful sources. If what you are looking for isn't below, remember that Google is your friend. If it's not, remember that other RPCS3 developers are your friends too. Ask them!

**Developement channel:** #development at [RPCS3's Discord](https://discord.me/RPCS3)
<br>
Old IRC channel: #rpcs3 at freenode.net

Best wishes and happy coding!

---

## Documentation
You can find a **compendium of public documentation** released by IBM and Sony regarding Cell and the SPU at our website under [Download](https://rpcs3.net/download) which contains:
- Cell Broadband Engine Architecture v1.01
- Cell Broadband Engine Architecture v1.02 [(Direct link @ ibm.com)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/1AEEE1270EA2776387257060006E61BA/$file/CBEA_v1.02_11Oct2007_pub.pdf)
- Cell Broadband Engine Architecture C/C++ Language Extensions v2.2.1 [(Direct link @ ncsu.edu)](http://moss.csc.ncsu.edu/~mueller/cluster/ps3/C++_Language_Extensions_for_CBEA.v2.2.1.pdf)
- Cell Broadband Engine Architecture C/C++ Language Extensions v2.3
- Cell Broadband Engine Architecture C/C++ Language Extensions v2.5 [(Direct link @ sbg.ac.at)](http://www.cosy.sbg.ac.at/~rkutil/dsp08/Language_Extensions_for_CBEA_2.5.pdf)
- Cell Broadband Engine Architecture C/C++ Language Extensions v2.6 [(Direct link @ ibm.com)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/30B3520C93F437AB87257060006FFE5E/$file/Language_Extensions_for_CBEA_2.6.pdf)
- Cell Broadband Engine Programming Handbook v1.1 [(Direct link @ ncsu.edu)](http://moss.csc.ncsu.edu/~mueller/cluster/ps3/CBE_Tutorial_v1.1_15June2006.pdf)
- Cell Broadband Engine Programming Handbook v2.0 [(Direct link @ ncsu.edu)](http://moss.csc.ncsu.edu/~mueller/cluster/ps3/CBE_Tutorial_v2.0_15December2006.pdf)
- Cell Broadband Engine Registers v1.5
- Cell Broadband Engine Registers v1.5.1 [(Direct link @ ibm.com)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/6ED822DD7E97D889872570B200607EEC/$file/CellBE_Registers_v1.51_18SEP2007.pdf)
- Cell Broadband Engine Architecture SIMD Math Library Specification v1.0
- Cell Broadband Engine Architecture SIMD Math Library Specification v1.2 [(Direct link @ ibm.com)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/6BFB9899CEA5456800257360001938B3/$file/SIMD_Library_Specification_for_CBEA_1.2.pdf)
- SPU Application Binary Interface Specification v1.6
- SPU Application Binary Interface Specification v1.9 [(Direct link @ ibm.com)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/02E544E65760B0BF87257060006F8F20/$file/SPU_ABI-Specification_1.9.pdf)
- SPU Assembly Language Specification v1.4
- SPU Assembly Language Specification v1.7 [(Direct link @ ibm.com)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/EFA2B196893B550787257060006FC9FB/$file/SPU_Assembly_Language_Specification_1.7.pdf)
- SPU Instruction Set Architecture v1.2 (IBM) [(Direct link @ ibm.com)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/76CA6C7304210F3987257060006F2C44/$file/SPU_ISA_v1.2_27Jan2007_pub.pdf)
- SPU Instruction Set Architecture v1.2 (Sony)
- Preventing SPE Indefinite Stalls Resulting from Instruction Depletion in Cell Broadband Engine Processor v1.0 [(Direct link @ ibm.com)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/C5996EDB722D3A478725728E0074B465/$file/SPUstall_app_V1.0_26Feb2007.pdf)


### RSX
* RSX Commands: [http://www.psdevwiki.com/ps3/RSXFIFOCommands](http://www.psdevwiki.com/ps3/RSXFIFOCommands) (Partially incomplete)
* Ask other developers.


### HLE
* [http://www.psdevwiki.com/ps3/](http://www.psdevwiki.com/ps3/)
* LV2 SysCalls: Ask other developers. [http://www.psdevwiki.com/ps3/LV2\_Functions\_and\_Syscalls](http://www.psdevwiki.com/ps3/LV2_Functions_and_Syscalls) (A bit incomplete)
* Modules: Ask other developers. Basically optional HLE implementaions of prx modules found in `/dev_flash/sys/external/`.


---


## Information

_(Some of this information can be deleted, or at least it should be properly organized)_
* `sizeof(char)` = 1 (= 8 bits)
* `sizeof(short)` = 2
* `sizeof(int)` = 4
* `sizeof(long)` = 4
* `sizeof(long long)` = 8
* `sizeof(size_t)` = 4
* `sizeof(sys_memory_container_t)` = 4
* `sizeof(void*)` = 4

Reading from invalid addresses / Trying to execute code from invalid addresses (e.g. stack) / Trying to write to invalid addresses (e.g. functions) makes the application exit on real PS3s.