# Graphics Driver Issues
This page quickly summarizes graphics driver quirks and issues present in GPU drivers by different manufacturers.

» [Intel (Proprietary)](#intel-proprietary) <br>
» [AMD (Proprietary)](#amd-proprietary) <br>
» [NVIDIA (Proprietary)](#nvidia-proprietary) <br>
» [AMD (Mesa)](#amd-proprietary)


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
- ~~glGetTexImage/glGetTextureImage/glGetTextureImageEXT do not work with immutable textures if pack/unpack byteswap is requested. Workaround implemented.~~ Fixed in driver version 19.4.3
- ~~Critical bug with Adrenalin 2020 drivers (since 19.12.x series). OpenGL no longer works with proprietary AMD drivers. Issue reported to AMD, we're waiting for action from their side.~~ Fixed in driver version 20.1.4

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