`void TriggerHapticPulse( vr::TrackedDeviceIndex_t unControllerDeviceIndex, uint32_t unAxisId, unsigned short usDurationMicroSec )`

Trigger a single haptic pulse on a controller. 

* `vr::TrackedDeviceIndex_t unControllerDeviceIndex` - The tracked device index of the controller to trigger a haptic pulse on.
* `uint32_t unAxisId` - The ID of the axis to trigger a haptic pulse on.
* `unsigned short usDurationMicroSec` - The duration of the desired haptic pulse in microseconds.

**Description**

Trigger a single haptic pulse on a controller. 

Note: After this call the application may not trigger another haptic pulse on this controller and axis combination for 5ms.
