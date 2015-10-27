Notes:
* GetPlayAreaSize is the width/depth of the Play Area in meters.
* GetPlayAreaRect (formerly GetSoftBoundsInfo) is a rectangle defining where the player has clear VR space floor to ceiling. Keep required reachable interactions in this space. It's always centered around standing tracking space origin.
* (DEPRECATED) GetHardBoundsInfo, see GetPlayAreaRect.
* Calibrations are saved per "universe" which with lighthouse corresponds to a set of basestations.  We attempt to update the universe when basestations are moved.  These functions will only return valid data once we've determined which known universe you are currently in.  Therefore, you may need to poll the functions until they return true (which will happen after establishing tracking for the hmd).
* You can (and likely should) also poll for VREvent_ChaperoneDataHasChanged to update things if the chaperone data changes.

### Accessors ###

[GetCalibrationState](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetCalibrationState)

[GetPlayAreaSize](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetPlayAreaSize)

[GetPlayAreaRect](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetPlayAreaRect)