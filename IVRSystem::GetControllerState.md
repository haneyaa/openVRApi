`bool GetControllerState( vr::TrackedDeviceIndex_t unControllerDeviceIndex, vr::VRControllerState_t *pControllerState )`<br>
`bool GetControllerStateWithPose( TrackingUniverseOrigin eOrigin, vr::TrackedDeviceIndex_t unControllerDeviceIndex, vr::VRControllerState_t *pControllerState, TrackedDevicePose_t *pTrackedDevicePose )`

Fills the supplied struct with the current state of the controller.

* `vr::TrackedDeviceIndex_t unControllerDeviceIndex` - The tracked device index of the controller to trigger a haptic pulse on.
* `vr::VRControllerState_t *pControllerState` - A struct to fill with the controller state.
* `TrackingUniverseOrigin eOrigin` - The tracking coordinate system to return the pose in.
* `TrackedDevicePose_t *pTrackedDevicePose` - A pose struct to fill with the pose of the controller when the last button event occurred.

Fills the supplied struct with the current state of the controller. Returns false if the controller index is invalid or if state is not available from the controller for some reason.

GetControllerStateWithPose will also fill the provided pose struct with the pose of 
the controller when the controller button state was updated most recently. Use this form if you need a precise controller pose as input to your application when the user presses or releases a button. This pose is always older than the current time, so it should not be used for rendering.

