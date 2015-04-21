	bool HandleControllerOverlayInteractionAsMouse( 
		const vr::Compositor_OverlaySettings & overlaySettings, 
		vr::HmdVector2_t vecWindowClientPositionOnScreen, vr::HmdVector2_t vecWindowClientSize,
		vr::TrackedDeviceIndex_t unControllerDeviceIndex, 
		vr::EVRControllerEventOutputType eOutputType
		)

Processes input from the controller as though it were a mouse pointed at the compositor overlay.

* `const vr::Compositor_OverlaySettings & overlaySettings` - The overlay settings to treat as a window.
* `vr::HmdVector2_t vecWindowClientPositionOnScreen` - The position of the application window on the screen. Only used when operating system events are being generated for the events.
* `vr::HmdVector2_t vecWindowClientSize` - Size of the application window. Virtual mouse positions will be scaled to this size.
* `vr::TrackedDeviceIndex_t unControllerDeviceIndex` - Tracked device index of the controller to test against the overlay.
* `vr::EVRControllerEventOutputType eOutputType` - Determines how the output should be presented. Must be one of:
  * `ControllerEventOutput_OSEvents` - The function should generate events in the operating system that will be processed by the application with focus in the OS.
  * `ControllerEventOutput_VREvents` - The function should generate internal VR events that can be queried with PollNextEvent.


Processes mouse input from the specified controller as though it were a mouse pointed at a compositor overlay with the specified settings. The controller is treated like a laser pointer on the -z axis. The point where the laser pointer would intersect with the overlay is the mouse position, the trigger is left mouse, and the track pad is right mouse. When using system event output the caller should ensure that it has focus so that it receives the system events. 

Returns true if the controller is pointed at the overlay and an event was generated.
