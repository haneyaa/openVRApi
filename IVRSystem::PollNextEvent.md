`bool PollNextEvent( `[`VREvent_t`](https://github.com/ValveSoftware/openvr/wiki/VREvent_t)` *pEvent )`<br>
`bool PollNextEventWithPose( TrackingUniverseOrigin eOrigin, vr::`[`VREvent_t`](https://github.com/ValveSoftware/openvr/wiki/VREvent_t)` *pEvent, vr::TrackedDevicePose_t *pTrackedDevicePose )`

Returns the next event in the queue.

* [`VREvent_t`](https://github.com/ValveSoftware/openvr/wiki/VREvent_t)` *pEvent` - An event structure to fill with the next event.
* `TrackingUniverseOrigin eOrigin` - The tracking system to return the event's pose in.
* `TrackedDevicePose_t *pTrackedDevicePose` - A pose struct to fill with the returned event's pose. Must not be NULL.

**Description**

Returns true and fills pEvent with the next event in the queue. If there is no event waiting, PollNextEvent returns false.

If the application needs to know exactly where the tracked device associated with the event was when the event occured, it can use the PollNextEventWithPose function. The pose returned with this function will always be older than now and should not be used for rendering. For events with no associated device this function returns an invalid pose. 

See also: [VREvent_t](https://github.com/ValveSoftware/openvr/wiki/VREvent_t)
