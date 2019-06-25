## Overview
This page quickly summarizes graphics driver quirks and issues present in GPU drivers by different manufacturers.

### Intel (proprietary)
**OpenGL.**
- GLSL compiler is broken. There are likely other issues as well. This driver is unsupported by RPCS3.

**Vulkan.**
- No known problems at this time.

### AMD (proprietary)
**OpenGL.**
- glMultiDrawArrays is broken. Workaround implemented and problem reported to AMD. No replies yet.<br>
  [NOTE] This seems to be undefined behavior in the spec. The gl_VertexID propagation behavior across MultiDrawArrays is not defined, i.e whether it should continue incrementing of reset to 0 on a new instance. However, due to the comparison with a loop of [first, count] and implied functional equivalence, this may be interpreted as a bug. Either way, RPCS3 provides a workaround using index lookups.
- ~~glGetTexImage/glGetTextureImage/glGetTextureImageEXT do not work with immutable textures if pack/unpack byteswap is requested. Workaround implemented.~~ Fixed in driver version 19.4.3

**Vulkan.**
- Primitive restart is 'broken'. This seems to be a GCN hardware bug as it also affects mesa drivers to some extent. Workaround implemented. (confirmed - see [this commit](https://github.com/mesa3d/mesa/commit/eae8f49fc65e6e625f5e05d38c3bf1b61b84bd3d))

### NVIDIA (proprietary)
**OpenGL.**
- FP precision issues with Nan/Inf values. Workaround implemented.

**Vulkan.**
- FP precision issues with Nan/Inf values. Workaround implemented.

### Mesa
**OpenGL.**
- The debug overlay is not visible

**Vulkan.**
- Primitive restart is 'broken'. This seems to be a GCN hardware bug as it also affects proprietary drivers. Workaround implemented. (confirmed - see [this commit](https://github.com/mesa3d/mesa/commit/eae8f49fc65e6e625f5e05d38c3bf1b61b84bd3d))
- LLVM8 codegen is broken. Use mesa with LLVM9 codegen to avoid this issue. Padoka PPA has the updated LLVM9 drivers for ubuntu users. See [this bug report.](https://bugs.freedesktop.org/show_bug.cgi?id=110970)