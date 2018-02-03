## Game Patches for RPCS3's Game Patching System

This page lists the current existing community patches for RPCS3's game patching system. To use them, create a `patch.yml` file on RPCS3's root directory and add one or more of the following patches to it.

---


### Demon's Souls
**60 FPS Patch** by [gibbed](https://github.com/gibbed) 
<br>
**Notes:** Patch accelerates game by 2x.
```
PPU-83681f6110d33442329073b72b8dc88a2f677172: #BLUS30443
  - [be16, 0x25ED8, 0x981f]

PPU-5446a2645880eefa75f7e374abd6b7818511e2ef: #BLES00932
  - [be16, 0x26AC0, 0x981f]
```

---

### Hatsune Miku: Project Diva F

**60 FPS Patch** by [Brolijah](https://github.com/Brolijah)
<br>
**Notes:** Patch accelerates some game effects by 2x. Does not affect playability.
```
# Project DIVA F USA Disc & PSN 1.00
PPU-f3227f57ec001582b253035fd90de77f05ead470:
  - [be32, 0xBF289C, 0x3F800000]
  - [be16, 0x589496, 0x0001]
  - [be16, 0x5894BA, 0x0001]
  - [be16, 0x589802, 0x0001]
  - [be16, 0x58982A, 0x0001]

# Project DIVA F EUR PSN 1.00
PPU-c02e3b52e3d75f52f76fb8f0fb5be7ca4d921949:
  - [be32, 0xBF289C, 0x3F800000]
  - [be16, 0x589496, 0x0001]
  - [be16, 0x5894BA, 0x0001]
  - [be16, 0x589802, 0x0001]
  - [be16, 0x58982A, 0x0001]

# Project DIVA F JAP Disc & PSN 1.00
PPU-1105af0a4d6a4a1481930c6f3090c476cde06c4c:
  - [be32, 0xBF22FC, 0x3F800000]
  - [be16, 0x586202, 0x0001]
  - [be16, 0x586226, 0x0001]
  - [be16, 0x58656E, 0x0001]
  - [be16, 0x586596, 0x0001]
```

---
