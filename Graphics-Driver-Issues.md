## Overview
This page quickly summarizes graphics driver quirks and issues present in GPU drivers by different manufacturers.

### Intel (proprietary)
**OpenGL.**
- GLSL compiler is broken. There are likely other issues as well. This driver is unsupported by RPCS3.

**Vulkan.**
- Raster pattern requires 'Strict Mode' to be enabled to deal with framebuffer feedback loops, otherwise a diagonal line may be observed on screen between triangle edges.

### AMD (proprietary)
**OpenGL.**
- glMultiDrawArrays is broken. Workaround implemented and problem reported to AMD. No replies yet.
- glGetTexImage/glGetTextureImage/glGetTextureImageEXT do not work with immutable textures if pack/unpack byteswap is requested. Workaround implemented.

**Vulkan.**
- Raster pattern requires 'Strict Mode' to be enabled to deal with framebuffer feedback loops, otherwise a diagonal line may be observed on screen between triangle edges.
- Primitive restart is 'broken'. This seems to be a GCN hardware bug as it also affects mesa drivers to some extent. Workaround implemented.
- Fence reset can trigger a driver crash, epsecially on pre-GCN4 hardware. Workaround implemented.
- Compiling some shaders can crash the driver on driver 18.5.2 and newer. Issue reported, driver update expected to fix the issue.

### NVIDIA (proprietary)
**OpenGL.**
- FP precision issues with Nan/Inf values. Workaround implemented.

**Vulkan.**
- FP precision issues with Nan/Inf values. Workaround implemented.
- (Linux only) Problems with SPIRV, compiler does not properly read exponent style values (e.g 1.e-2 vs 0.01)

### Mesa
**OpenGL.**
- The debug overlay is not visible

**Vulkan.**
- RADV: No major remaining issues identified yet.

