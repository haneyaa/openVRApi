`HmdMatrix44_t GetEyeToHeadTransform( Hmd_Eye eEye )`

Returns the transform between the view space and eye space. Eye space is the per-eye flavor of view space that provides stereo disparity. Instead of Model * View * Projection the model is Model * View * Eye * Projection. Normally View and Eye will be multiplied together and treated as View in your application.

This matrix incorporates the user's interpupillary distance (IPD).

* `eEye` - `Eye_Left` or `Eye_Right`. Determines which eye the function should return the eye matrix for.
