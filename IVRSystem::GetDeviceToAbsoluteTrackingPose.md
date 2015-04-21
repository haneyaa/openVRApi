`void GetDeviceToAbsoluteTrackingPose( TrackingUniverseOrigin eOrigin, float fPredictedSecondsToPhotonsFromNow, VR_ARRAY_COUNT(unTrackedDevicePoseArrayCount) TrackedDevicePose_t *pTrackedDevicePoseArray, uint32_t unTrackedDevicePoseArrayCount )`

Calculates updated poses for all devices.

* `eOrigin` - Tracking universe that returned poses should be relative to. This will be one of:
  * `TrackingUniverseSeated`
  * `TrackingUniverseStanding`
  * `TrackingUniverseRaw`
* `float fPredictedSecondsToPhotonsFromNow` - Number of seconds from now to predict poses for. Positive numbers are in the future. Pass 0 to get the sate at the instant the function is called. See below for details on how to compute a good value here.

**Description**

The pose that the tracker thinks that the HMD will be in at the specified number of seconds into the 
future. Pass 0 to get the state at the instant the method is called. Most of the time the application should
calculate the time until the photons will be emitted from the display and pass that time into the method.

This is roughly analogous to the inverse of the view matrix in most applications, though 
many games will need to do some additional rotation or translation on top of the rotation
and translation provided by the head pose.

For devices where bPoseIsValid is true the application can use the pose to position the device
in question. The provided array can be any size up to k_unMaxTrackedDeviceCount. 

Seated experiences should call this method with TrackingUniverseSeated and receive poses relative
to the seated zero pose. Standing experiences should call this method with TrackingUniverseStanding 
and receive poses relative to the chaperone soft bounds. TrackingUniverseRawAndUncalibrated should 
probably not be used unless the application is the chaperone calibration tool itself, but will provide
poses relative to the hardware-specific coordinate system in the driver.

**Computing seconds to photons**

The number of seconds from now to when the next photons will come out of the HMD can be computed automatically. This assumes that the rendering pipeline doesn't have any extra frames buffering.

Example:
	// for somebody asking for the default figure out the time from now to photons.
	float fSecondsSinceLastVsync;
	pVRSystem->GetTimeSinceLastVsync( &fSecondsSinceLastVsync, NULL );

	float fDisplayFrequency = pVRSystem->GetFloatTrackedDeviceProperty( vr::k_unTrackedDeviceIndex_Hmd, vr::Prop_DisplayFrequency_Float );
	float fFrameDuration = 1.f / fDisplayFrequency;
	float fVsyncToPhotons = pVRSystem->GetFloatTrackedDeviceProperty( vr::k_unTrackedDeviceIndex_Hmd, vr::Prop_SecondsFromVsyncToPhotons_Float );
	
	float fPredictedSecondsFromNow = fFrameDuration - fSecondsSinceLastVsync + fVsyncToPhotons;
