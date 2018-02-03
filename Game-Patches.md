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
