`HmdMatrix44_t GetProjectionMatrix( Hmd_Eye eEye, float fNearZ, float fFarZ, GraphicsAPIConvention eProjType )`

Returns the projection matrix to use for the specified eye.

* `eEye` - Eye_Left or Eye_Right. Determines which eye the function should return the projection for.
* `fNearZ` - distance to the near clip plane in meters
* `fFarZ` - distance to the far clip plane in meters
* `eProjType` - Modifies the return value to match the conventions of the specified API. One of:
  * `API_DirectX`
  * `API_OpenGL`
