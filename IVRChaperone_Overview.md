Notes:
* GetSoftBoundsInfo is being deprecated.  We are planning to adopt a series of discrete play volumes which will allow devs to target, and consumers to verify they have enough room to play.
* GetHardBoundsInfo currently returns a single quad which is used to define the extents of the playable space (typically aligned to the physical walls of the room).  To be forward compatible, you should check that the count is 1 since this may return higher detailed geometry in the future, resulting in the first quad not necessarily representing the total available space.
* Calibrations are saved per "universe" which with lighthouse corresponds to a set of basestations.  We attempt to update the universe when basestations are moved.  These functions will only return valid data once we've determined which known universe you are currently in.  Therefore, you may need to poll the functions until they return true (which will happen after establishing tracking for the hmd).
* You can (and likely should) also poll for VREvent_ChaperoneDataHasChanged to update things if the chaperone data changes.

### Accessors ###

[GetCalibrationState](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetCalibrationState)

[GetSoftBoundsInfo](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetSoftBoundsInfo)

[GetHardBoundsInfo](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetHardBoundsInfo)

[GetSeatedBoundsInfo](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetSeatedBoundsInfo)







