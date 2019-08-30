## Patches for RPCS3's Game Patching System

This page lists the current existing community patches for RPCS3's game patching system. To use them, create a `patch.yml` file on RPCS3's root directory and add one or more of the following patches to it.

**To get the PPU hash from your executable:** Boot the game once, open RPCS3.log afterwards with a text editor and search for 'PPU executable hash'. On that line, you'll find your executable's PPU hash, which you can then replace on game patches when required.

---


### Demon's Souls

<details>
<summary>
<b>60 / 120 FPS Patch</b> by <a href="https://github.com/Whatcookie" target="_blank">Whatcookie</a>
<br>
<b>Game versions:</b> Disc (EU, US)
<br>
<b>Notes:</b> This patch MUST be used with the following settings: Clocks Scale: 200, Vblank Rate: 120
</summary>

```
# 1.0.1

PPU-83681f6110d33442329073b72b8dc88a2f677172: #BLUS30443
# OPTIONAL: Disable dynamic exposure (can turn off WCB for 20% faster performance)
# Enable this if you experience flickering
#  - [be16, 0x00025EDC, 0x981f]

# Alter fixed timestep
  - [ bef32, 0x018c8db4, 0.01666667 ] # for 60fps
#  - [ bef32, 0x018c8db4, 0.00833334 ] # for 120fps

PPU-5446a2645880eefa75f7e374abd6b7818511e2ef: #BLES00932
# OPTIONAL: Disable dynamic exposure (can turn off WCB for 20% faster performance)
# Enable this if you experience flickering
#  - [be16, 0x00026AC4, 0x981f]

# Alter fixed timestep
  - [ bef32, 0x018c8f20, 0.01666667 ] # for 60fps
#  - [ bef32, 0x018c8f20, 0.00833334 ] # for 120fps
```
</details>



### Genji: Days of the Blade

<details>
<summary>
<b>21:9 Patch</b> by <a href="https://github.com/Esppiral" target="_blank">Esppiral</a>
<br>
<b>Game versions:</b> Disc (EU)
</summary>

```
# Genji: Days of the Blade [BCES00002]
PPU-4aeb132cdf86d9c4ab20e48ae70cc823e455e05d:
  - [be32, 0x100FA8B0, 0x4017B9AA] # 21:9 
```

</details>

<details>
<summary>
<b>60 FPS Patch</b> by <a href="https://github.com/Esppiral" target="_blank">Esppiral</a>
<br>
<b>Game versions:</b> Disc (EU)
</summary>

```
# Genji: Days of the Blade [BCES00002]
PPU-4aeb132cdf86d9c4ab20e48ae70cc823e455e05d:
  - [be32, 0x100FA964, 0x00000000] # for 60fps
```

</details>



### Hatsune Miku: Project Diva F

<details>
<summary>
<b>60 FPS Patch</b> by <a href="https://github.com/Brolijah" target="_blank">Brolijah</a>
<br>
<b>Game versions:</b> Disc v1.00 (JP, US) and Digital v1.00 (EU, JP, US)
<br>
<b>Notes:</b> Patch accelerates some game effects by 2x. Does not affect playability.
</summary>

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

</details>



### Hatsune Miku: Project Diva F 2nd

<details>
<summary>
<b>60 FPS Patch</b> by <a href="https://github.com/Brolijah" target="_blank">Brolijah</a>
<br>
<b>Game versions:</b> Disc v1.00 (AS, JP, US), Disc v1.01 (JP), Disc v1.02 (JP), Digital v1.00 (AS, EU, JP), Digital v1.02 (JP)
<br>
<b>Notes:</b> Patch accelerates some game effects by 2x. Does not affect playability.
</summary>

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

</details>



### Kingdom Hearts HD 1.5 ReMIX

<details>
<summary>
<b>21:9 Patch</b> by <a href="https://github.com/Esppiral" target="_blank">Esppiral</a>
<br>
<b>Game versions:</b> Disc (US)
</summary>

```
PPU-d626d9832ed48d1ff0d8d97e53a4e23df50cfae6:
  - [be32, 0xEB170, 0x3FAAAAAB] # VERT+ (21.9)
  - [be32, 0xEB16C, 0x3FC00000] # ZOOM+ (21.9)
```

</details>

<details>
<summary>
<b>60 FPS Patch</b> by <a href="https://github.com/Esppiral" target="_blank">Esppiral</a>
<br>
<b>Game versions:</b> Disc (US)
</summary>

```
PPU-d626d9832ed48d1ff0d8d97e53a4e23df50cfae6:
  - [be32, 0x20D1016, 0x00000000] # 60fps
```

</details>



### LittleBigPlanet 2

<details>
<summary>
<b>21:9 Patch</b> by <a href="https://github.com/slashiee" target="_blank">slashiee</a>
<br>
<b>Game versions:</b> Digital v1.00 (US)
<br>
</summary>

```
# LittleBigPlanet 2 1.33 [NPUA80662]
lbp2AspectRatio_133_NPUA80662: &lbp2AspectRatio_133_NPUA80662
    - [ bef32, 0x00D9C8EC, 2.37037037 ]
PPU-a74423ca913fc18e46cfe926db1d48e41f9858a9: # NPUA80662
    - [ load, lbp2AspectRatio_133_NPUA80662 ]
```

</details>



### NieR

<details>
<summary>
<b>60 FPS Patch</b> by <a href="https://github.com/Whatcookie" target="_blank">Whatcookie</a>
<br>
<b>Game versions:</b> Disc (EU, JP, US)
<br>
<b>Notes:</b> Use vSync if you have a 60hz display, otherwise use the builtin frame-limiter. Game speed will be unstable if you do not have a constant 30 or 60 FPS.
</summary>

```
PPU-13950b2e29e05a115fe317815d3da9d2b2baee65: #BLUS30481/BLES00826
- [ be32, 0x00f7c3b8, 0x386003e8 ] # li  r3, 3e8

PPU-f098ee8410599c81c89f90d698340a078dc69a90: #BLJM60223
- [ be32, 0x00f7cbcc, 0x386003e8 ] # li  r3, 3e8
```

</details>



### Persona 5

<details>
<summary>
<b>60 FPS Patch</b> by <a href="https://github.com/TGEnigma" target="_blank">TGEnigma</a>
<br>
<b>Game versions:</b> Unspecified (Use your executable hash)
<br>
<b>Notes:</b> Patch may accelerate some game effects by 2x.
</summary>

```
# Update 4/30/2018: Fix various timings, incl. battle, fix voice cutoff during cutscenes
p5_60FPS: &p5_60FPS
    - [ be32, 0x00010268, 0x9061009C ] # set update rate to 60 -> r3, 0xE0+var_44(r1)
    - [ be32, 0x008FC864, 0x60000000 ] # nop cellGcmSetSecondVFrequency
    - [ bef32, 0x00012484, 0.01666667 ]
    - [ bef32, 0x00045678, 0.01666667 ]
    - [ bef32, 0x000616F0, 0.01666667 ]
    - [ bef32, 0x00073F20, 0.01666667 ]
    # - [ bef32, 0x000753A0, 0.01666667 ] Doubles camera speed
    - [ bef32, 0x00077E54, 0.01666667 ]
    - [ bef32, 0x00078A70, 0.01666667 ]
    - [ bef32, 0x0007A238, 0.01666667 ]
    - [ bef32, 0x00081864, 0.01666667 ]
    - [ bef32, 0x000885C8, 0.01666667 ]
    - [ bef32, 0x0008C550, 0.01666667 ]
    - [ bef32, 0x0008D6D0, 0.01666667 ]
    - [ bef32, 0x000D058C, 0.01666667 ]
    - [ bef32, 0x000D0B4C, 0.01666667 ]
    - [ bef32, 0x000E4754, 0.01666667 ]
    - [ bef32, 0x000E50F0, 0.01666667 ]
    - [ bef32, 0x000E8190, 0.01666667 ]
    - [ bef32, 0x000F8B78, 0.01666667 ]
    - [ bef32, 0x00101CE8, 0.01666667 ]
    - [ bef32, 0x001E7344, 0.01666667 ]
    - [ bef32, 0x001EB0D4, 0.01666667 ]
    - [ bef32, 0x001EB328, 0.01666667 ]
    - [ bef32, 0x001EB814, 0.01666667 ]
    - [ bef32, 0x001EB940, 0.01666667 ]
    - [ bef32, 0x001EBA04, 0.01666667 ]
    - [ bef32, 0x001EBBA0, 0.01666667 ]
    - [ bef32, 0x001EBCD0, 0.01666667 ]
    - [ bef32, 0x001ECCA0, 0.01666667 ]
    - [ bef32, 0x00234C64, 0.01666667 ]
    - [ bef32, 0x0023F4BC, 0.01666667 ]
    - [ bef32, 0x002400BC, 0.01666667 ]
    - [ bef32, 0x00240BB0, 0.01666667 ]
    - [ bef32, 0x0029231C, 0.01666667 ]
    - [ bef32, 0x00294A70, 0.01666667 ]
    - [ bef32, 0x002952F8, 0.01666667 ]
    #- [ bef32, 0x002B027C, 0.01666667 ] Makes it impossible to run < 60 fps
    - [ bef32, 0x002B0688, 0.01666667 ]
    - [ bef32, 0x002B6154, 0.01666667 ]
    - [ bef32, 0x002B71F8, 0.01666667 ]
    - [ bef32, 0x002B82C8, 0.01666667 ]
    - [ bef32, 0x002B98F8, 0.01666667 ]
    - [ bef32, 0x002B9F8C, 0.01666667 ]
    - [ bef32, 0x002BA614, 0.01666667 ]
    - [ bef32, 0x002BC84C, 0.01666667 ]
    - [ bef32, 0x002BCD2C, 0.01666667 ]
    - [ bef32, 0x002C550C, 0.01666667 ]
    - [ bef32, 0x002D1328, 0.01666667 ]
    #- [ bef32, 0x002D230C, 0.01666667 ] Doubles movement speed
    - [ bef32, 0x002D2DDC, 0.01666667 ]
    - [ bef32, 0x002D8A10, 0.01666667 ]
    - [ bef32, 0x002D8A18, 0.01666667 ]
    - [ bef32, 0x002DA46C, 0.01666667 ]
    - [ bef32, 0x002FBB00, 0.01666667 ]
    - [ bef32, 0x0030E258, 0.01666667 ]
    - [ bef32, 0x003181D4, 0.01666667 ]
    - [ bef32, 0x0031CE24, 0.01666667 ]
    - [ bef32, 0x0031DBE0, 0.01666667 ]
    - [ bef32, 0x0033DBD0, 0.01666667 ]
    - [ bef32, 0x00358664, 0.01666667 ]
    - [ bef32, 0x00359020, 0.01666667 ]
    - [ bef32, 0x0035AD10, 0.01666667 ]
    - [ bef32, 0x00364A98, 0.01666667 ]
    - [ bef32, 0x0037429C, 0.01666667 ]
    - [ bef32, 0x00376E7C, 0.01666667 ]
    - [ bef32, 0x00379B08, 0.01666667 ]
    - [ bef32, 0x0037AAAC, 0.01666667 ]
    - [ bef32, 0x0037CF54, 0.01666667 ]
    - [ bef32, 0x0037DB7C, 0.01666667 ]
    - [ bef32, 0x003803F4, 0.01666667 ]
    - [ bef32, 0x00387A80, 0.01666667 ]
    - [ bef32, 0x00388684, 0.01666667 ]
    - [ bef32, 0x003ACBC0, 0.01666667 ]
    - [ bef32, 0x003BDDD0, 0.01666667 ]
    - [ bef32, 0x003E944C, 0.01666667 ]
    - [ bef32, 0x003F35EC, 0.01666667 ]
    - [ bef32, 0x003F6FF4, 0.01666667 ]
    - [ bef32, 0x0058CE18, 0.01666667 ]
    - [ bef32, 0x0058DE64, 0.01666667 ]
    - [ bef32, 0x0058E82C, 0.01666667 ]
    - [ bef32, 0x0058E958, 0.01666667 ]
    - [ bef32, 0x0058F47C, 0.01666667 ]
    - [ bef32, 0x0058FA00, 0.01666667 ]
    - [ bef32, 0x0058FAB4, 0.01666667 ]
    - [ bef32, 0x0058FBE4, 0.01666667 ]
    - [ bef32, 0x0058FD2C, 0.01666667 ]
    - [ bef32, 0x0058FE6C, 0.01666667 ]
    - [ bef32, 0x00590A04, 0.01666667 ]
    - [ bef32, 0x005B6914, 0.01666667 ]
    - [ bef32, 0x005F1C6C, 0.01666667 ]
    - [ bef32, 0x0062076C, 0.01666667 ] # battle related stuff
    - [ bef32, 0x007072BC, 0.01666667 ]
    - [ bef32, 0x00722D7C, 0.01666667 ]
    - [ bef32, 0x0073C840, 0.01666667 ]
    - [ bef32, 0x00772E50, 0.01666667 ]
    - [ bef32, 0x0087B338, 0.01666667 ]
    - [ bef32, 0x00B10110, 0.01666667 ]
    - [ bef32, 0x00B6AA14, 0.01666667 ]
    - [ bef32, 0x00B6AA38, 0.01666667 ]
    - [ bef32, 0x00B70B48, 0.01666667 ]
    - [ bef32, 0x00B70BC8, 0.01666667 ]
    - [ bef32, 0x00B71CF4, 0.01666667 ]
    - [ bef32, 0x00B72F38, 0.01666667 ]
    - [ bef32, 0x00CFF46C, 0.01666667 ]
    - [ bef32, 0x00061700, 0.1666667 ]
    - [ bef32, 0x00069AA4, 0.1666667 ]
    - [ bef32, 0x0007A1EC, 0.1666667 ]
    - [ bef32, 0x00081880, 0.1666667 ]
    - [ bef32, 0x000C8258, 0.1666667 ]
    - [ bef32, 0x000C991C, 0.1666667 ]
    - [ bef32, 0x00101CCC, 0.1666667 ]
    - [ bef32, 0x001E2C44, 0.1666667 ]
    - [ bef32, 0x001E61E8, 0.1666667 ]
    - [ bef32, 0x001E7338, 0.1666667 ]
    - [ bef32, 0x00250C50, 0.1666667 ]
    - [ bef32, 0x00256B20, 0.1666667 ]
    - [ bef32, 0x00292100, 0.1666667 ]
    - [ bef32, 0x00294A60, 0.1666667 ]
    - [ bef32, 0x002952E4, 0.1666667 ]
    - [ bef32, 0x0029FD98, 0.1666667 ]
    - [ bef32, 0x002A1BB8, 0.1666667 ]
    - [ bef32, 0x002A41D0, 0.1666667 ]
    - [ bef32, 0x002A6124, 0.1666667 ]
    - [ bef32, 0x002B4FF0, 0.1666667 ]
    - [ bef32, 0x002B60DC, 0.1666667 ]
    - [ bef32, 0x002B7174, 0.1666667 ]
    - [ bef32, 0x002B82F4, 0.1666667 ]
    - [ bef32, 0x002B8E74, 0.1666667 ]
    - [ bef32, 0x002BA600, 0.1666667 ]
    - [ bef32, 0x002BAB30, 0.1666667 ]
    - [ bef32, 0x002BB4E0, 0.1666667 ]
    - [ bef32, 0x002BB808, 0.1666667 ]
    - [ bef32, 0x002BC368, 0.1666667 ]
    - [ bef32, 0x002BC844, 0.1666667 ]
    - [ bef32, 0x002BD414, 0.1666667 ]
    - [ bef32, 0x002C4F54, 0.1666667 ]
    - [ bef32, 0x002C4FF0, 0.1666667 ]
    - [ bef32, 0x002C69E4, 0.1666667 ]
    - [ bef32, 0x002D4378, 0.1666667 ]
    - [ bef32, 0x002DD968, 0.1666667 ]
    - [ bef32, 0x002DE538, 0.1666667 ]
    - [ bef32, 0x002DEA04, 0.1666667 ]
    - [ bef32, 0x0030D7A0, 0.1666667 ]
    - [ bef32, 0x0030E6BC, 0.1666667 ]
    - [ bef32, 0x003181B8, 0.1666667 ]
    - [ bef32, 0x0031AFE0, 0.1666667 ]
    - [ bef32, 0x0031CE38, 0.1666667 ]
    - [ bef32, 0x0031DBF0, 0.1666667 ]
    - [ bef32, 0x0031EC74, 0.1666667 ]
    - [ bef32, 0x00322FB4, 0.1666667 ]
    - [ bef32, 0x00356560, 0.1666667 ]
    - [ bef32, 0x003586BC, 0.1666667 ]
    - [ bef32, 0x00358F90, 0.1666667 ]
    - [ bef32, 0x0035A380, 0.1666667 ]
    - [ bef32, 0x0035AA3C, 0.1666667 ]
    - [ bef32, 0x00364A9C, 0.1666667 ]
    - [ bef32, 0x003688C8, 0.1666667 ]
    - [ bef32, 0x00368A88, 0.1666667 ]
    - [ bef32, 0x00368E30, 0.1666667 ]
    - [ bef32, 0x00376FD0, 0.1666667 ]
    - [ bef32, 0x00377538, 0.1666667 ]
    - [ bef32, 0x00377CD8, 0.1666667 ]
    - [ bef32, 0x0037C2B0, 0.1666667 ]
    - [ bef32, 0x0037D310, 0.1666667 ]
    - [ bef32, 0x0037D418, 0.1666667 ]
    - [ bef32, 0x0037D5B4, 0.1666667 ]
    - [ bef32, 0x0037DD08, 0.1666667 ]
    - [ bef32, 0x0037DE10, 0.1666667 ]
    - [ bef32, 0x0037DF78, 0.1666667 ]
    - [ bef32, 0x00382F38, 0.1666667 ]
    - [ bef32, 0x003845F0, 0.1666667 ]
    - [ bef32, 0x00387A6C, 0.1666667 ]
    - [ bef32, 0x00398208, 0.1666667 ]
    - [ bef32, 0x00398460, 0.1666667 ]
    - [ bef32, 0x003999F8, 0.1666667 ]
    - [ bef32, 0x003A7C64, 0.1666667 ]
    - [ bef32, 0x003AA418, 0.1666667 ]
    - [ bef32, 0x003AE0E4, 0.1666667 ]
    - [ bef32, 0x003AE3A0, 0.1666667 ]
    - [ bef32, 0x003B25D8, 0.1666667 ]
    - [ bef32, 0x003BC448, 0.1666667 ]
    - [ bef32, 0x003C58C0, 0.1666667 ]
    - [ bef32, 0x003C67B0, 0.1666667 ]
    - [ bef32, 0x003C6D6C, 0.1666667 ]
    - [ bef32, 0x003EBC20, 0.1666667 ]
    - [ bef32, 0x003EE5F0, 0.1666667 ]
    - [ bef32, 0x003F1FE0, 0.1666667 ]
    - [ bef32, 0x003F6FC0, 0.1666667 ]
    - [ bef32, 0x004EB808, 0.1666667 ]
    - [ bef32, 0x0055251C, 0.1666667 ]
    - [ bef32, 0x0055EC48, 0.1666667 ]
    - [ bef32, 0x0055F4A8, 0.1666667 ]
    - [ bef32, 0x0057DC08, 0.1666667 ]
    - [ bef32, 0x0057E498, 0.1666667 ]
    - [ bef32, 0x005C5364, 0.1666667 ]
    - [ bef32, 0x00620714, 0.1666667 ]
    - [ bef32, 0x00635CB4, 0.1666667 ]
    - [ bef32, 0x00642B98, 0.1666667 ]
    - [ bef32, 0x00654EE8, 0.1666667 ]
    - [ bef32, 0x00662B04, 0.1666667 ]
    - [ bef32, 0x006AFF98, 0.1666667 ]
    - [ bef32, 0x006CAA44, 0.1666667 ]
    - [ bef32, 0x006E0224, 0.1666667 ]
    - [ bef32, 0x006E31A0, 0.1666667 ]
    - [ bef32, 0x006FCD3C, 0.1666667 ]
    - [ bef32, 0x00772E54, 0.1666667 ]
    - [ bef32, 0x00797508, 0.1666667 ]
    - [ bef32, 0x00B52E3C, 0.1666667 ]
    - [ bef32, 0x00B6AD00, 0.1666667 ]
    - [ bef32, 0x00B6B71C, 0.1666667 ]
    - [ bef32, 0x00B6E478, 0.1666667 ]
    - [ bef32, 0x00B6E880, 0.1666667 ]
    - [ bef32, 0x00B6E8B8, 0.1666667 ]
    - [ bef32, 0x00B6E8F0, 0.1666667 ]
    - [ bef32, 0x00B6E928, 0.1666667 ]
    - [ bef32, 0x00B6E960, 0.1666667 ]
    - [ bef32, 0x00B6E998, 0.1666667 ]
    - [ bef32, 0x00B6E9D0, 0.1666667 ]
    - [ bef32, 0x00B6EA08, 0.1666667 ]
    - [ bef32, 0x00B6EA40, 0.1666667 ]
    - [ bef32, 0x00B6EA78, 0.1666667 ]
    - [ bef32, 0x00B6EAB0, 0.1666667 ]
    - [ bef32, 0x00B6EAE8, 0.1666667 ]
    - [ bef32, 0x00B6EB20, 0.1666667 ]
    - [ bef32, 0x00B6EB58, 0.1666667 ]
    - [ bef32, 0x00B6EB90, 0.1666667 ]
    - [ bef32, 0x00B6EBC8, 0.1666667 ]
    - [ bef32, 0x00B6EC00, 0.1666667 ]
    - [ bef32, 0x00B6EC38, 0.1666667 ]
    - [ bef32, 0x00B6EC70, 0.1666667 ]
    - [ bef32, 0x00B6ECA8, 0.1666667 ]
    - [ bef32, 0x00B70A54, 0.1666667 ]
    - [ bef32, 0x00B70AF0, 0.1666667 ]
    - [ bef32, 0x00B70AF8, 0.1666667 ]
    - [ bef32, 0x00B70B00, 0.1666667 ]
    - [ bef32, 0x00B70B08, 0.1666667 ]
    - [ bef32, 0x00B70B10, 0.1666667 ]
    - [ bef32, 0x00B70B20, 0.1666667 ]
    - [ bef32, 0x00B70B78, 0.1666667 ]
    - [ bef32, 0x00B70B88, 0.1666667 ]
    - [ bef32, 0x00B70BB4, 0.1666667 ]
    - [ bef32, 0x00B70BC4, 0.1666667 ]
    - [ bef32, 0x00B70F60, 0.1666667 ]
    - [ bef32, 0x00B71BAC, 0.1666667 ]
    - [ bef32, 0x00B71BBC, 0.1666667 ]
    - [ bef32, 0x00B9BD30, 0.1666667 ]
    - [ bef32, 0x00CF96AC, 0.1666667 ]
    - [ bef32, 0x00CFA1E8, 0.1666667 ]
    - [ bef32, 0x00CFA20C, 0.1666667 ]
    - [ bef32, 0x00CFB210, 0.1666667 ]
    - [ bef32, 0x00CFB778, 0.1666667 ]
    - [ bef32, 0x00CFBC30, 0.1666667 ]
    - [ bef32, 0x00CFBCA8, 0.1666667 ]
    - [ bef32, 0x00CFBFD4, 0.1666667 ]
    - [ bef32, 0x00CFC0A8, 0.1666667 ]
    - [ bef32, 0x00CFF3CC, 0.1666667 ]
    - [ bef32, 0x00CFF3D4, 0.1666667 ]
    - [ bef32, 0x00CFF470, 0.1666667 ]
    - [ bef32, 0x00CFF478, 0.1666667 ]
    - [ bef32, 0x00CFF480, 0.1666667 ]
    - [ bef32, 0x00D06840, 0.1666667 ]
    - [ bef32, 0x00D06848, 0.1666667 ]
    - [ be32, 0x000FB71C, 0x3C603C88 ]
    - [ be32, 0x00109B14, 0x3C603C88 ]
    - [ be32, 0x0023FBDC, 0x3CA03C88 ]
    - [ be32, 0x00240620, 0x3CA03C88 ]
    - [ be32, 0x00241258, 0x3C803C88 ]
    - [ be32, 0x003CA4BC, 0x3C603C88 ]
    - [ be32, 0x0087B448, 0x3C603C88 ]
    - [ be32, 0x00589358, 0x60000000 ] # Fix cutscene voice cutoff

# Replace the PPU hash by the one from your executable
PPU-b8c34f774adb367761706a7f685d4f8d9d355426:
    - [ load, p5_60FPS ]
```

</details>

<details>
<summary>
<b>Disable Blur Filter</b> by <a href="https://github.com/TGEnigma" target="_blank">TGEnigma</a>, <a href="https://github.com/ruipin" target="_blank">ruipin</a>, <a href="https://github.com/kd-11" target="_blank">kd-11</a>
<br>
<b>Game versions:</b> Unspecified (Use your executable hash)
</summary>

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

</details>

<details>
<summary>
<b>Disable Normal Distortion Filter (<=99% Alert & Velvet Room)</b> by <a href="https://github.com/TGEnigma" target="_blank">TGEnigma</a>, <a href="https://github.com/ruipin" target="_blank">ruipin</a>, <a href="https://github.com/kd-11" target="_blank">kd-11</a>
<br>
<b>Game versions:</b> Unspecified (Use your executable hash)
</summary>

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

</details>

<details>
<summary>
<b>Disable Angery Distortion Filter (100% Alert)</b> by <a href="https://github.com/TGEnigma" target="_blank">TGEnigma</a>, <a href="https://github.com/ruipin" target="_blank">ruipin</a>, <a href="https://github.com/kd-11" target="_blank">kd-11</a>
<br>
<b>Game versions:</b> Unspecified (Use your executable hash)
</summary>

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

</details>

<details>
<summary>
<b>Disable HUD Elements</b> by <a href="https://github.com/TGEnigma" target="_blank">TGEnigma</a>
<br>
<b>Game versions:</b> Unspecified (Use your executable hash)
<br>
<b>Notes:</b> Elements can disabled separately by adding/removing their respective lines from the patch.
</summary>

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

</details>



### Red Dead Redemption 

<details>
<summary>
<b>21:9 Patch</b> by <a href="https://github.com/Esppiral" target="_blank">Esppiral</a>
<br>
<b>Game versions:</b> Digital (EU)
</summary>

```
# Red Dead Redemption [NPEB00833]
PPU-8a18a0314cade28526874128b253acd98863b83d:
  - [be32, 0x474F24, 0x4017B9AA] # 21.9 Aspect Ratio
  - [be32, 0x954B8, 0x4017B9AA] # 21.9 HUD fix for 21.9 AR
```

</details>



### Sonic Adventure

<details>
<summary>
<b>Fullscreen 16:9</b> by <a href="https://github.com/Esppiral" target="_blank">Esppiral</a>
<br>
<b>Game versions:</b> Digital (EU)
</summary>

```
#  Sonic Adventure [NPEB00304] Fullscreen  16:9 rendering
PPU-5fc2b4ea8ae9cd7a4247f28dc6af65ca1a6a9fa4:
  - [be32, 0x05043F18, 0x3F400000]
  - [be32, 0x00909260, 0x009B1604]
  - [be32, 0x0090E5B0, 0x40A00000]
  - [be32, 0x00909270, 0x40400000]
  - [be32, 0x00909274, 0xC0400000]
  - [be32, 0x00909278, 0xBF400000]
```

</details>



### Space Channel 5 Part 2

<details>
<summary>
<b>21:9 Patch</b> by <a href="https://github.com/Esppiral" target="_blank">Esppiral</a>
<br>
<b>Game versions:</b> Digital (US)
</summary>

```
# Space Channel 5 Part 2 [NPUB30353]
PPU-2f6778a8e97be84833e47ef273ff10cc2bd6809e:
  - [be32, 0x5839D4, 0x3F99999A] # ZOOM+ (21.9)
  - [be32, 0x57EF84, 0x3F400000] # VERT+ (21.9)
```

</details>



### WipEout HD

<details>
<summary>
<b>21:9 Patch</b> by <a href="https://github.com/Esppiral" target="_blank">Esppiral</a>
<br>
<b>Game versions:</b> Digital v2.51 (EU)
</summary>

```
# WipEout HD [NPEA00057] v2.51
PPU-0e95b58ae209a37060f3388434b59bcce8a708ab:
  - [be32, 0x7E4190, 0x4017B9AA] # 21:9 Aspect Ratio
  - [be32, 0x7EB4A4, 0x4017B9AA] # Render Fix
```

</details>
