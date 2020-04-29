# Graphics Driver Issues
This page quickly summarizes graphics driver quirks and issues present in GPU drivers by different manufacturers.

» [Intel (Proprietary)](#intel-proprietary) <br>
» [AMD (Proprietary)](#amd-proprietary) <br>
» [NVIDIA (Proprietary)](#nvidia-proprietary) <br>
» [AMD (Mesa)](#amd-mesa)


## Intel (Proprietary) <a name="intel-proprietary"/>
**OpenGL** _(This driver is unsupported by RPCS3)_
- GLSL compiler is broken
- _There are likely other issues as well..._

**Vulkan**
- _No known problems at this time_


## AMD (Proprietary) <a name="amd-proprietary"/>
**OpenGL**
- glMultiDrawArrays is broken. Workaround implemented and problem reported to AMD. No replies yet. See [this report.](https://community.amd.com/message/2858799)<br>
  [NOTE] This seems to be undefined behavior in the spec. The gl_VertexID propagation behavior across MultiDrawArrays is not defined, i.e whether it should continue incrementing of reset to 0 on a new instance. However, due to the comparison with a loop of [first, count] and implied functional equivalence, this may be interpreted as a bug. Either way, RPCS3 provides a workaround using index lookups.

**Vulkan**
- Primitive restart is 'broken'. This seems to be a GCN hardware bug as it also affects mesa drivers to some extent. Workaround implemented. (confirmed - see [this commit](https://github.com/mesa3d/mesa/commit/eae8f49fc65e6e625f5e05d38c3bf1b61b84bd3d))


## NVIDIA (Proprietary) <a name="nvidia-proprietary"/>
**OpenGL**
- FP precision issues with Nan/Inf values. Workaround implemented.<br>
  NOTE: This is not a driver bug as it can be considered implementation-defined behavior.

**Vulkan**
- FP precision issues with Nan/Inf values. Workaround implemented.<br>
  NOTE: This is not a driver bug as it can be considered implementation-defined behavior.

## AMD (Mesa) <a name="amd-mesa"/>
**OpenGL**
- _No known problems at this time_

**Vulkan**
- Primitive restart is 'broken'. This seems to be a GCN hardware bug as it also affects proprietary drivers. Workaround implemented. (confirmed - see [this commit](https://github.com/mesa3d/mesa/commit/eae8f49fc65e6e625f5e05d38c3bf1b61b84bd3d))
- ~~LLVM8 codegen is broken. Use mesa with LLVM9 codegen to avoid this issue. Padoka PPA has the updated LLVM9 drivers for ubuntu users. See [this bug report.](https://bugs.freedesktop.org/show_bug.cgi?id=110970)~~ Fixed in newer versions of mesa based on later LLVM versions.
- If using the experimental Southern Islands amdgpu support, enabling MSAA may cause the emulator to crash. This is a limitation of the driver, disable MSAA to work around this issue.

---

# Hall of Fame
List of reported graphics driver bugs that are now fixed. We'd like to thank the developers who fixed these!

- **CRITICAL:** [OpenGL no longer renders **any** game on **any** AMD GPU! (Windows)](https://community.amd.com/message/2949336) <br>
» **Affected** drivers: Radeon Software Adrenalin 19.12.1, 19.12.2, 19.12.3, 20.1.1, 20.1.2, 20.1.3 <br>
» **Workaround** used: None, not possible <br>
» **Fixed** on: Radeon Software Adrenalin 20.1.4

- **Normal:** [OpenGL's glGetTexImage/glGetTextureImage/glGetTextureImageEXT do not work with immutable textures if pack/unpack byteswap is requested on **any** AMD GPU (Windows)](https://community.amd.com/thread/227876) <br>
» **Affected** drivers: Radeon Software Adrenalin 19.4.2 and earlier <br>
» **Workaround** used: [Manually byteswap texel data](https://github.com/RPCS3/rpcs3/commit/f56a6548b0a7a520301372f8e456c7174b514a68#diff-6067ceb43fa31f7dc9558bdf0b776ad8) (now removed) <br>
» **Fixed** on: Radeon Software Adrenalin 19.4.3

- **High:** [AMD RADV driver crash when using ACO due to unusual control flow (Mesa)](https://gitlab.freedesktop.org/mesa/mesa/issues/2557) <br>
» **Affected** drivers: Mesa 20.0.2 and earlier <br>
» **Workaround** used: None, using RADV with LLVM instead of ACO <br>
» **Fixed** on: Mesa 20.0.3

- **Medium:** [Unnecessary implicit subpass dependencies caused performance regression on AMD RADV (Mesa)](https://gitlab.freedesktop.org/mesa/mesa/issues/2502) <br>
» **Affected** drivers: Mesa 20.0.0, 20.0.1 <br>
» **Workaround** used: [Explicitely injecting null subpass dependencies](https://github.com/RPCS3/rpcs3/pull/7909/commits/943cbb1e39fec9cc02ac6193e9b05482c4a36c92#diff-d0082402e2ea9309446e3dc7818f8394) <br>
» **Fixed** on: Mesa 20.0.2