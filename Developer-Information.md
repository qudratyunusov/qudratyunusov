If you are wondering about websites and documents in order to gather information about certain parts of the PlayStation 3 here is a nice list to start with. Probably more things should be added here, but for now it is a good compilation of useful sources. If what your are looking for isn't below, remember that Google is your friend. If it's not, remember that other RPCS3 developers are your friends too. Ask them!

Best wishes and happy coding!

---

## Links

### Cell
* [Cell Broadband Engine Architecture (Version 1.02 / October 11, 2007)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/1AEEE1270EA2776387257060006E61BA/$file/CBEA_v1.02_11Oct2007_pub.pdf)
* [Cell Broadband Engine Programming Handbook (Version 1.12 / April 3, 2009)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/7A77CCDF14FE70D5852575CA0074E8ED/$file/CellBE_Handbook_v1.12_3Apr09_pub.pdf)
* [Cell Broadband Engine Registers (Version 1.5 / April 2, 2007)](http://cell.scei.co.jp/pdf/CBE_Public_Registers_v15.pdf)
* [SPU Application Binary Interface Specification (Version 1.9 / July 18, 2008)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/02E544E65760B0BF87257060006F8F20/$file/SPU_ABI-Specification_1.9.pdf)
* [SPU Assembly Language Specification (Version 1.7 / July 18, 2008)](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/EFA2B196893B550787257060006FC9FB/$file/SPU_Assembly_Language_Specification_1.7.pdf)
* [SPU Instruction Set Architecture (Version 1.2 / January 27, 2007)](http://cell.scei.co.jp/pdf/SPU_ISA_v12.pdf)

### RSX
* RSX Commands: [http://www.psdevwiki.com/ps3/RSXFIFOCommands](http://www.psdevwiki.com/ps3/RSXFIFOCommands) (Partially incomplete)
* Ask other developers.


### HLE
* [http://www.psdevwiki.com/ps3/](http://www.psdevwiki.com/ps3/)
* Module SysCalls: Ask other developers.
* lv2 SysCalls: [http://www.psdevwiki.com/ps3/LV2\_Functions\_and\_Syscalls](http://www.psdevwiki.com/ps3/LV2_Functions_and_Syscalls) (A bit incomplete)
* lv2 SysCalls: Ask other developers.


## Information

####OE bit
Some instructions contain an optional `OE`(overflow excpetion) flag. We currently do not implement those versions of the instructions. For example we emulate `add`, `addze`, `subfme` but not `addo`, `addzeo`, `subfmo` which are just the prior operations with the `OE` flag set.

This flag writes to the `OV` and `SO` (overflow and summary overflow) bits of the XER (Fixed-Point Exception Register) register. The reason why it's not implemented is that the [GCC code emitter](http://repo.or.cz/w/official-gcc.git/blob_plain/c2c80e70905bc2e5dedf8352588fc8cb10e3ec7d:/gcc/config/rs6000/rs6000.md) does not use these instructions and so we haven't found any PS3 software that uses it.

If we find some software that has some handwritten assembly that use those instructions we'll need to implement it (or just for completeness). A good reference for XER bits can be found in [PowerPC Microprocessor Family: The Programmer's Reference Guide ](https://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/852569B20050FF778525699600741775) chapter 1.3 and other linked references.

For the implementation of the interpreter it would probably be best to refrain from x86 assembly or compiler intrinsics like `__readeflags` to determine a overflow. Probably something from the [answers to this SO question](http://stackoverflow.com/questions/199333/best-way-to-detect-integer-overflow-in-c-c) is what we should consider.


####Misc
(Some of this information can be deleted, or at least it should be properly organized).
* `sizeof(char)` = 1 (= 8 bits)
* `sizeof(short)` = 2
* `sizeof(int)` = 4
* `sizeof(long)` = 4
* `sizeof(long long)` = 8
* `sizeof(size_t)` = 4
* `sizeof(void*)` = 4

Reading from invalid addresses / Trying to execute code from invalid addresses (e.g. stack) / Trying to write to invalid addresses (e.g. functions) makes the application exit on real PS3s.