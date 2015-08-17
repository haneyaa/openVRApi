`bool HandleControllerOverlayInteractionAsMouse( VROverlayHandle_t ulOverlayHandle, TrackedDeviceIndex_t unControllerDeviceIndex )`

Processes mouse input from the specified controller as though it were a mouse pointed at the overlay.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to test the controller against
* `TrackedDeviceIndex_t unControllerDeviceIndex` - Device index of the controller to test

**Description** 

Processes mouse input from the specified controller as though it were a mouse pointed at the overlay. The controller is treated like a laser pointer on the -z axis. The point where the laser pointer would intersect with the overlay is the mouse position, the trigger is left mouse, and the track pad is right mouse. 

Returns true if the controller is pointed at the overlay and an event was generated.
