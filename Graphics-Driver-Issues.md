# Graphics Driver Issues
This page quickly summarizes graphics driver quirks and issues present in GPU drivers by different manufacturers.

» [Intel (Proprietary)](#intel-proprietary) <br>
» [AMD (Proprietary)](#amd-proprietary) <br>
» [NVIDIA (Proprietary)](#nvidia-proprietary) <br>
» [AMD (Mesa)](#amd-mesa) <br>
» [Intel (Mesa)](#intel-mesa) <br>
» [**Hall of Fame (List of fixed issues)**](#hall-of-fame)


## Intel (Proprietary) <a name="intel-proprietary"/>
**OpenGL**
- [GLSL compiler is very broken](https://github.com/RPCS3/rpcs3/issues/6199) <br>
» **Workaround** implemented: No <br>
» **Reported**: No <br>
» **Note**: Intel proprietary OpenGL drivers are unsupported by RPCS3 due to their poor state.

- _There are likely other issues as well..._

**Vulkan**
- _No known problems at this time_


## AMD (Proprietary) <a name="amd-proprietary"/>
**OpenGL**
- [glMultiDrawArrays is broken](https://community.amd.com/message/2858799) <br>
» **Workaround** implemented: **Yes** <br>
» **Reported**: **Yes**, on 2018-04-25. No replies. <br>
» **Note**: This seems to be undefined behavior in the spec. The gl_VertexID propagation behavior across MultiDrawArrays is not defined, i.e whether it should continue incrementing of reset to 0 on a new instance. However, due to the comparison with a loop of [first, count] and implied functional equivalence, this may be interpreted as a bug. Either way, RPCS3 provides a workaround using index lookups.

**Vulkan**
- Primitive restart is 'broken', this seems to be a GCN hardware bug as it affects both proprietary and open-source drivers <br>
» **Workaround** implemented: **Yes** (automatic) <br>
» **Note**: Confirmed, see [eae8f49f@mesa3d/mesa](https://github.com/mesa3d/mesa/commit/eae8f49fc65e6e625f5e05d38c3bf1b61b84bd3d)

- [MSAA with sample shading disabled does not work on NAVI when using Vulkan](https://community.amd.com/t5/opengl-vulkan/msaa-with-sample-shading-disabled-does-not-work-on-navi-when/td-p/425122) <br>
» **Workaround** implemented: **Yes** (automatic) <br>
» **Note:** Forcefully enabling sampleRateShading for all pipelines and calculating the minimum ratio works around this problem


## NVIDIA (Proprietary) <a name="nvidia-proprietary"/>
**OpenGL**
- Floating point precision issues with Nan/Inf values<br>
» **Workaround** implemented: **Yes** (automatic) <br>
» **Note**: This is not a driver bug as it can be considered implementation-defined behavior.

**Vulkan**
- Floating point precision issues with Nan/Inf values<br>
» **Workaround** implemented: **Yes** (automatic) <br>
» **Note**: This is not a driver bug as it can be considered implementation-defined behavior.


## AMD (Mesa) <a name="amd-mesa"/>
**OpenGL**
- _No known problems at this time_

**Vulkan**
- Primitive restart is 'broken', this seems to be a GCN hardware bug as it affects both proprietary and open-source drivers <br>
» **Workaround** implemented: **Yes** (automatic) <br>
» **Note**: Confirmed, see [eae8f49f@mesa3d/mesa](https://github.com/mesa3d/mesa/commit/eae8f49fc65e6e625f5e05d38c3bf1b61b84bd3d)

- ~~[LLVM 8 generates broken code on Mesa](https://bugs.freedesktop.org/show_bug.cgi?id=110970)~~ <br>
» **Workaround** implemented: No, use newer versions of Mesa that are based on LLVM 9 or above <br>
» **Reported**: **Yes**, on 2019-06-22. Quick reply. <br>
» **Note**: This is caused by a dependency (LLVM), and not a bug on the driver's implementation. <br>


## Intel (Mesa) <a name="intel-mesa"/>
**OpenGL**
- **i965** Driver: **Not supported.** Games won't render properly with it, it's very broken [[1]](https://www.youtube.com/watch?v=SSprkcc6NZM), [[2]](https://www.youtube.com/watch?v=0qjqblFDdFw), [[3]](https://www.youtube.com/watch?v=ZwKmYBMMdvE).
- **iris** Driver: _No known problems at this time._

**Vulkan**
- [Diagonal corruption line](https://gitlab.freedesktop.org/mesa/mesa/issues/2671) <br>
» **Workaround** implemented: **Yes**, use Strict Rendering Mode <br>
» **Reported**: **Yes**, on 2020-03-22. Quickly replied. <br>

- [Missing `shaderStorageImageMultisample` Vulkan feature support on Intel iGPUs (RPCS3 crashes if MSAA is enabled)](https://gitlab.freedesktop.org/mesa/mesa/-/issues/3355) <br>
» **Workaround** implemented: None, disable Anti-Aliasing <br>
» **Reported**: **Yes**, on 2020-08-03. No solution given from the driver developers, feature unsupported in hardware. <br>

---

# Hall of Fame <a name="hall-of-fame"/>
List of reported graphics driver bugs that are now fixed. We'd like to thank the developers who fixed these!

- **CRITICAL:** [OpenGL no longer renders **any** game on **any** AMD GPU! (Windows)](https://community.amd.com/message/2949336) <br>
» **Affected** drivers: Radeon Software Adrenalin 19.12.1, 19.12.2, 19.12.3, 20.1.1, 20.1.2, 20.1.3 <br>
» **Workaround** used: None, not possible <br>
» **Fixed** on: Radeon Software Adrenalin 20.1.4

- **High:** [AMD RADV driver crash when using ACO due to unusual control flow (Mesa)](https://gitlab.freedesktop.org/mesa/mesa/issues/2557) <br>
» **Affected** drivers: Mesa 20.0.2 and earlier <br>
» **Workaround** used: None, using RADV with LLVM instead of ACO <br>
» **Fixed** on: Mesa 20.0.3

- **High:** Incorrectly rendered Vulkan shaders due to broken SPIR-V optimization on NVIDIA <br>
» **Affected** drivers: NVIDIA Windows 452.06 and earlier, NVIDIA Linux 450.56.06 and earlier <br>
» **Workaround** used: None <br>
» **Fixed** on: NVIDIA Windows 452.28, NVIDIA Linux 450.56.11

- **Normal:** [OpenGL's glGetTexImage/glGetTextureImage/glGetTextureImageEXT do not work with immutable textures if pack/unpack byteswap is requested on **any** AMD GPU (Windows)](https://community.amd.com/thread/227876) <br>
» **Affected** drivers: Radeon Software Adrenalin 19.4.2 and earlier <br>
» **Workaround** used: [Manually byteswap texel data](https://github.com/RPCS3/rpcs3/commit/f56a6548b0a7a520301372f8e456c7174b514a68#diff-6067ceb43fa31f7dc9558bdf0b776ad8) (now removed) <br>
» **Fixed** on: Radeon Software Adrenalin 19.4.3

- **Normal:** [Unnecessary implicit subpass dependencies caused performance regression on AMD RADV (Mesa)](https://gitlab.freedesktop.org/mesa/mesa/issues/2502) <br>
» **Affected** drivers: Mesa 20.0.0, 20.0.1 <br>
» **Workaround** used: [Explicitely injecting null subpass dependencies](https://github.com/RPCS3/rpcs3/pull/7909/commits/943cbb1e39fec9cc02ac6193e9b05482c4a36c92#diff-d0082402e2ea9309446e3dc7818f8394) (now removed) <br>
» **Fixed** on: Mesa 20.0.2

- **Normal:** [vkGetQueryPoolResults returns incorrect values when VK_QUERY_RESULT_PARTIAL_BIT is set on NVIDIA (Windows)](https://forums.developer.nvidia.com/t/vkgetquerypoolresults-returns-incorrect-values-when-vk-query-result-partial-bit-is-set/110137) <br>
» **Affected** drivers: NVIDIA GeForce 442.59 and earlier <br>
» **Workaround** used: [Keeping NVIDIA driver from using partial results](https://github.com/RPCS3/rpcs3/pull/7909/commits/c4f539a9cf43e946364a3931f6e5b8c36457d4b4#diff-c9e6fd1ef5ae3e53670d088d2961e556) (now removed) <br>
» **Fixed** on: ~NVIDIA GeForce 442.74

- **Normal:** [Missing `shaderStorageImageMultisample` Vulkan feature support on GCN1 GPUs (RPCS3 crashes if MSAA is enabled)](https://gitlab.freedesktop.org/mesa/mesa/-/issues/2864) <br>
» **Affected** drivers: Mesa 20.0.8 and older <br>
» **Workaround** used: None (disable MSAA on affected drivers) <br>
» **Fixed** on: Mesa 20.1.0

- **Normal:** [Vertex explosion when using ACO shader compiler on AMD RADV (Mesa)](https://gitlab.freedesktop.org/mesa/mesa/-/issues/2848) <br> 
» **Affected** drivers: Mesa 20.2.1 and older <br>
» **Workaround** used: None, not possible. Using the older shader compiler instead of ACO, which was the default prior to Mesa 20.2 <br>
» **Fixed** on: Mesa 20.2.2