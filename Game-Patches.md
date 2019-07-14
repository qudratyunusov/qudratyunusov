## Game Patches for RPCS3's Game Patching System

This page lists the current existing community patches for RPCS3's game patching system. To use them, create a `patch.yml` file on RPCS3's root directory and add one or more of the following patches to it.

**To get the PPU hash from your executable:** Boot the game once, open RPCS3.log afterwards with a text editor and search for 'PPU executable hash'. On that line, you'll find your executable's PPU hash, which you can then replace on game patches when required.

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

### Hatsune Miku: Project Diva F 2nd

**60 FPS Patch** by [Brolijah](https://github.com/Brolijah)
<br>
**Notes:** Patch accelerates some game effects by 2x. Does not affect playability.
```
# Project DIVA F 2nd USA Disc 1.00 (Maybe also PSN?)
PPU-092c43e2bcacccfe3cdc22b0ab8062b91d4e1cf9: # BLUS31431 ver. 1.00
  - [be32, 0x0423C8, 0x3F800000]
  - [be16, 0x6AF44E, 0x0001]
  - [be16, 0x6AF46E, 0x0001]
  - [be16, 0x6AF492, 0x0001]
  - [be16, 0x6AF4B6, 0x0001]

# Project DIVA F 2nd EUR PSN 1.00 (Maybe also Disc?)
PPU-67e0e7c9b2a7a340c914a0d078e25aac1047e4d4: # NPEB02013 ver. 1.00
  - [be32, 0x0423C8, 0x3F800000]
  - [be16, 0x6AF44E, 0x0001]
  - [be16, 0x6AF46E, 0x0001]
  - [be16, 0x6AF492, 0x0001]
  - [be16, 0x6AF4B6, 0x0001]

# Project DIVA F 2nd ASIA Disc 1.00
PPU-51d336edfa3774f2db83ed030611f462c097c40b: # BLAS50723 ver. 1.00
  - [be32, 0x042390, 0x3F800000]
  - [be16, 0x6AF0B6, 0x0001]
  - [be16, 0x6AF0D6, 0x0001]
  - [be16, 0x6AF0FA, 0x0001]
  - [be16, 0x6AF11E, 0x0001]

# Project DIVA F 2nd ASIA PSN 1.00
PPU-c70b15d3f6694af74fa329dd4fc25fe28a59e9cc: # NPHB00671 ver. 1.00
  - [be32, 0x042390, 0x3F800000]
  - [be16, 0x6AF0B6, 0x0001]
  - [be16, 0x6AF0D6, 0x0001]
  - [be16, 0x6AF0FA, 0x0001]
  - [be16, 0x6AF11E, 0x0001]

# Project DIVA F 2nd JAP Disc & PSN 1.00 
PPU-c3291f5919ca147ac854de10f7436f4ad494233f: # BLJM61079/NPJB00435 ver. 1.00
  - [be32, 0x041F40, 0x3F800000]
  - [be16, 0x6A48F6, 0x0001]
  - [be16, 0x6A4916, 0x0001]
  - [be16, 0x6A493A, 0x0001]
  - [be16, 0x6A495E, 0x0001]

# Project DIVA F 2nd JAP Disc 1.01
PPU-058cf39c07fd13f100c1f6dc40a0ead9bf3ad51b: # BLJM61079 ver. 1.01
  - [be32, 0x041F40, 0x3F800000]
  - [be16, 0x6A48F6, 0x0001]
  - [be16, 0x6A4916, 0x0001]
  - [be16, 0x6A493A, 0x0001]
  - [be16, 0x6A495E, 0x0001]

# Project DIVA F 2nd JAP Disc 1.02
PPU-8fc9f26ed77cc9237db0e6348dcf9d6c451b6220: # BLJM61079 ver. 1.02
  - [be32, 0x041F40, 0x3F800000]
  - [be16, 0x6A48F6, 0x0001]
  - [be16, 0x6A4916, 0x0001]
  - [be16, 0x6A493A, 0x0001]
  - [be16, 0x6A495E, 0x0001]

# Project DIVA F 2nd JAP PSN 1.02
PPU-311fcd98af6adc5e64e6a833eb959f43b0976193: # NPJB00435 ver. 1.02
  - [be32, 0x041F78, 0x3F800000]
  - [be16, 0x6AB316, 0x0001]
  - [be16, 0x6AB336, 0x0001]
  - [be16, 0x6AB35A, 0x0001]
  - [be16, 0x6AB37E, 0x0001]
```

---

### LittleBigPlanet 2


**21:9 Patch** by [slashiee](https://github.com/slashiee)
<br>
**Notes:** This patch is only for the US PSN version of the game.
<br>

```
# LittleBigPlanet 2 1.33 (NPUA80662)
lbp2AspectRatio_133_NPUA80662: &lbp2AspectRatio_133_NPUA80662
    - [ bef32, 0x00D9C8EC, 2.37037037 ]
PPU-a74423ca913fc18e46cfe926db1d48e41f9858a9: # NPUA80662
    - [ load, lbp2AspectRatio_133_NPUA80662 ]
```

---

### NieR


**60 FPS Patch** by [Whatcookie](https://github.com/Whatcookie)
<br>
**Notes:** Use vSync if you have a 60hz display, otherwise use the builtin frame-limiter. Game speed will be unstable if you do not have a constant 30 or 60 FPS.
```
PPU-13950b2e29e05a115fe317815d3da9d2b2baee65: #BLUS30481/BLES00826
- [ be32, 0x00f7c3b8, 0x386003e8 ] # li  r3, 3e8

PPU-f098ee8410599c81c89f90d698340a078dc69a90: #BLJM60223
- [ be32, 0x00f7cbcc, 0x386003e8 ] # li  r3, 3e8
```

---

### Persona 5

**60 FPS Patch** by [TGEnigma](https://github.com/TGEnigma)
<br>
**Notes:** Patch may accelerate some game effects by 2x.
<br>
**Patch URL:** https://pastebin.com/TFVsG6xF
<br>

**Disable Blur Filter** by [TGEnigma](https://github.com/TGEnigma), [ruipin](https://github.com/ruipin), [kd-11](https://github.com/kd-11)
```
p5_DisableBlur: &p5_DisableBlur
    - [ be32, 0x00FEE27A, 0x9E001700 ]
    - [ be32, 0x00FEE27E, 0xC801001D ]
    - [ be32, 0x00FEE282, 0x00000000 ]
    - [ be32, 0x00FEE286, 0x00000000 ]
    - [ be32, 0x00FEE28A, 0x1E810100 ]
    - [ be32, 0x00FEE28E, 0xC800001D ]
    - [ be32, 0x00FEE292, 0x00000000 ]
    - [ be32, 0x00FEE296, 0x00000000 ]
# Replace the PPU hash by the one from your executable
PPU-d0b4d4ba47cab3d5d8328ade1af75f0ae4861488:
   - [ load, p5_DisableBlur ]
```


**Disable Normal Distortion Filter (<=99% Alert & Velvet Room)** by [TGEnigma](https://github.com/TGEnigma), [ruipin](https://github.com/ruipin), [kd-11](https://github.com/kd-11)
```
p5_DisableDistortion: &p5_DisableDistortion
    - [ be32, 0x00FE2E28, 0x9E001700 ]
    - [ be32, 0x00FE2E2C, 0xC801001D ]
    - [ be32, 0x00FE2E30, 0x00000000 ]
    - [ be32, 0x00FE2E34, 0x00000000 ]
    - [ be32, 0x00FE2E38, 0x1E810100 ]
    - [ be32, 0x00FE2E3C, 0xC800001D ]
    - [ be32, 0x00FE2E40, 0x00000000 ]
    - [ be32, 0x00FE2E44, 0x00000000 ]
# Replace the PPU hash by the one from your executable
PPU-d0b4d4ba47cab3d5d8328ade1af75f0ae4861488:
   - [ load, p5_DisableDistortion ]
```


**Disable Angery Distortion Filter (100% Alert)** by [TGEnigma](https://github.com/TGEnigma), [ruipin](https://github.com/ruipin), [kd-11](https://github.com/kd-11)
```
p5_Disable100PctDistortion: &p5_Disable100PctDistortion
    - [ be32, 0x00FE31CC, 0x9E001700 ]
    - [ be32, 0x00FE31D0, 0xC801001D ]
    - [ be32, 0x00FE31D4, 0x00000000 ]
    - [ be32, 0x00FE31D8, 0x00000000 ]
    - [ be32, 0x00FE31DC, 0x1E810100 ]
    - [ be32, 0x00FE31E0, 0xC800001D ]
    - [ be32, 0x00FE31E4, 0x00000000 ]
    - [ be32, 0x00FE31E8, 0x00000000 ]
# Replace the PPU hash by the one from your executable
PPU-d0b4d4ba47cab3d5d8328ade1af75f0ae4861488:
   - [ load, p5_Disable100PctDistortion ]
```


**Disable HUD Elements** by [TGEnigma](https://github.com/TGEnigma)
<br>
**Notes:** Elements can disabled separately by adding/removing their respective lines from the patch.
```
# Replace the PPU hash by the one from your executable
PPU-d0b4d4ba47cab3d5d8328ade1af75f0ae4861488:
    - [ be32, 0xDE4EC, 0x60000000 ] # mission list
    - [ be32, 0xE83F4, 0x60000000 ] # place pict
    - [ be32, 0xE5920, 0x60000000 ] # check
    - [ be32, 0x69CC4, 0x38600001 ] # alert
    - [ be32, 0x5F678, 0x60000000 ] # date
    - [ be32, 0x38A0D0, 0x4838A186 ] # misc field hud
    - [ be32, 0x28FBA0, 0x38600000 ] # party panel
    - [ be32, 0x28FBA4, 0x4E800020 ] # party panel
    - [ be32, 0xD6B48, 0x60000000 ] # mini map
    - [ be32, 0xD6490, 0x60000000 ] # mini map
```

---
