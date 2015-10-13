Notes:
* GetSoftBoundsInfo is a rectangle defining where the player has clear VR space floor to ceiling. Keep required reachable interactions in this space. It's always centered around standing tracking space origin.
* GetHardBoundsInfo either returns a single quad or a list on N quads. If it's a single quad then this is the 2D extents of the available space (typically aligned to the physical walls of the room). For >1 one quads, each quad is a wall in the space. These extents are shown as alerts for players in the compositor, but developers should almost always use GetSoftBoundsInfo instead to fit within the player's designated VR space.
* Calibrations are saved per "universe" which with lighthouse corresponds to a set of basestations.  We attempt to update the universe when basestations are moved.  These functions will only return valid data once we've determined which known universe you are currently in.  Therefore, you may need to poll the functions until they return true (which will happen after establishing tracking for the hmd).
* You can (and likely should) also poll for VREvent_ChaperoneDataHasChanged to update things if the chaperone data changes.

### Accessors ###

[GetCalibrationState](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetCalibrationState)

[GetSoftBoundsInfo](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetSoftBoundsInfo)

[GetHardBoundsInfo](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetHardBoundsInfo)

[GetSeatedBoundsInfo](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone::GetSeatedBoundsInfo)







