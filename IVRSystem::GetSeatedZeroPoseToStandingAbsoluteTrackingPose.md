`HmdMatrix34_t GetSeatedZeroPoseToStandingAbsoluteTrackingPose()`

Returns the transform from the seated zero pose to the standing absolute tracking system. This allows 
applications to represent the seated origin to used or transform object positions from one coordinate
system to the other. 

The seated origin may or may not be inside the soft or hard bounds returned by IVRChaperone. Its position 
depends on what the user has set in the chaperone calibration tool and previous calls to ResetSeatedZeroPose.

