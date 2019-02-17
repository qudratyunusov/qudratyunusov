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
- Primitive restart is 'broken'. This seems to be a GCN hardware bug as it also affects mesa drivers to some extent. Workaround implemented. (confirmed - see [this commit](https://github.com/mesa3d/mesa/commit/eae8f49fc65e6e625f5e05d38c3bf1b61b84bd3d))

### NVIDIA (proprietary)
**OpenGL.**
- FP precision issues with Nan/Inf values. Workaround implemented.

**Vulkan.**
- FP precision issues with Nan/Inf values. Workaround implemented.
- (Linux only) Problems with SPIRV, compiler does not properly read exponent style values (e.g 1.e-2 vs 0.01)
- (Windows only) Driver may lock up if RPCS3 is in fullscreen and the present mode is not FIFO. Enable vsync in the emulator to help prevent this issue.

### Mesa
**OpenGL.**
- The debug overlay is not visible

**Vulkan.**
- RADV: Raster pattern requires 'Strict Mode' to be enabled to deal with framebuffer feedback loops, otherwise a diagonal line may be observed on screen between triangle edges.
- Primitive restart is 'broken'. This seems to be a GCN hardware bug as it also affects proprietary drivers. Workaround implemented. (confirmed - see [this commit](https://github.com/mesa3d/mesa/commit/eae8f49fc65e6e625f5e05d38c3bf1b61b84bd3d))