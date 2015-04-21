`HiddenAreaMesh_t GetHiddenAreaMesh( Hmd_Eye eEye )`

Returns the hidden area stencil mesh for the current HMD. 

* `Hmd_Eye eEye` - The eye to get the hidden area mesh for.

**Description**

Returns the hidden area stencil mesh for the current HMD. If this HMD does not have a stencil mesh the vertex data and count will be NULL and 0 respectively. This mesh is meant to be rendered into the stencil buffer (or into the depth buffer setting nearz) before rendering each eye's view. The pixels covered by this mesh will never be seen by the user after the lens distortion is applied and based on visibility to the panels. This will improve perf by letting the GPU early-reject pixels the user will never see before running the pixel shader.

NOTE: Render this mesh with backface culling disabled since the winding order of the vertices can be different per-HMD or per-eye.
