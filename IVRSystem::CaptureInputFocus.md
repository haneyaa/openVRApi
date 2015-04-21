`bool CaptureInputFocus()`

Tells OpenVR that this process wants exclusive access to controller button states and button events. Other apps will be notified that they have lost input focus with a VREvent_InputFocusLost event. Returns false if input focus could not be captured for some reason.
