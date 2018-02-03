### Hatsune Miku: Project Diva F
* Renders at a base resolution of 2048x1152 _(kd-11)_;

### Red Dead Redemption
* Renders at a base resolution of 1152x648 _(kd-11)_;

### The Evil Within
* The evil within uses the GPU to decompress streaming texture resources by faking them as draw calls, using pixel shaders to do the heavy lifting. Then it copies the decoded dxt data using blit engine to merge into an atlas _(kd-11)_;