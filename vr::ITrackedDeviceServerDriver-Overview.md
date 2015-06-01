The `vr::ITrackedDeviceServerDriver` interface represents a single physical tracked device in the system. It is implemented in driver dynamic libs. 

Once an instance of this interface is provided to vrserver it should remain valid until Cleanup is called on the `ITrackedDeviceServerProvider` object.

**`HmdError Activate( uint32_t unObjectId )`**

This is called before tracked device is returned to the application. It will always be
called before any display or tracking methods. Memory and processor use by the
`vr::ITrackedDeviceServerDriver` object should be kept to a minimum until it is activated. 
The pose listener is guaranteed to be valid until Deactivate is called, but 
should not be used after that point.


**`void Deactivate()`**

This is called when vrserver is switching to another driver.


**`const char *GetId()`**

Returns the serial number of this particular tracked device. This value is opaque to the VR system itself,
but should be unique within the driver because it will be passed back in via FindTrackedDeviceDriver.


**`void DebugRequest( const char *pchRequest, char *pchResponseBuffer, uint32_t unResponseBufferSize )`**

A VR Client has made this debug request of the driver. The set of valid requests is entirely
up to the driver and the client to figure out, as is the format of the response. Responses that
exceed the length of the supplied buffer should be truncated and null terminated.

# Display Methods

**`void GetWindowBounds( int32_t *pnX, int32_t *pnY, uint32_t *pnWidth, uint32_t *pnHeight )`**

Size and position that the window needs to be on the VR display.


**`bool IsDisplayOnDesktop()`**

Returns true if the display is extending the desktop.


**`bool IsDisplayRealDisplay()`**

Returns true if the display is real and not a fictional display.


**`void GetRecommendedRenderTargetSize( uint32_t *pnWidth, uint32_t *pnHeight )`**

Suggested size for the intermediate render target that the distortion pulls from.


**`void GetEyeOutputViewport( Hmd_Eye eEye, uint32_t *pnX, uint32_t *pnY, uint32_t *pnWidth, uint32_t *pnHeight )`**

Gets the viewport in the frame buffer to draw the output of the distortion into.


**`void GetProjectionRaw( Hmd_Eye eEye, float *pfLeft, float *pfRight, float *pfTop, float *pfBottom )`**

The components necessary to build your own projection matrix in case your
application is doing something fancy like infinite Z */


**`HmdMatrix34_t GetHeadFromEyePose( Hmd_Eye eEye )`**

Returns the transform from eye space to the head space. Eye space is the per-eye flavor of head
space that provides stereo disparity. Instead of Model * View * Projection the sequence is Model * View * Eye^-1 * Projection. 

Normally View and Eye^-1 will be multiplied together and treated as View in your application. 


**`DistortionCoordinates_t ComputeDistortion( Hmd_Eye eEye, float fU, float fV )`**
Returns the result of the distortion function for the specified eye and input UVs. UVs go from 0,0 in 
the upper left of that eye's viewport and 1,1 in the lower right of that eye's viewport.

# Assorted capability methods

**`TrackedDeviceDriverInfo_t GetTrackedDeviceDriverInfo()`**

Returns all the static information that will be reported to the clients.
	

# Administrative Methods

**`const char *GetModelNumber()`**

Returns the model number of this tracked device.

**`const char *GetSerialNumber()`**

Returns the serial number of this tracked device.

# IPD Methods

**`float GetIPD()`**

Gets the current IPD (Interpupillary Distance) in meters.

# Tracking Methods

**`DriverPose_t GetPose()`**

Gets the initial pose of the device. Future poses should be provided via `IServerDriverHost::TrackedDevicePoseUpdated()` function.


# Property Methods

**`bool GetBoolTrackedDeviceProperty( TrackedDeviceProperty prop, TrackedPropertyError *pError )
float GetFloatTrackedDeviceProperty( TrackedDeviceProperty prop, TrackedPropertyError *pError ) = 0;
int32_t GetInt32TrackedDeviceProperty( TrackedDeviceProperty prop, TrackedPropertyError *pError ) = 0;
uint64_t GetUint64TrackedDeviceProperty( TrackedDeviceProperty prop, TrackedPropertyError *pError ) = 0;
uint32_t GetStringTrackedDeviceProperty( TrackedDeviceProperty prop, char *pchValue, uint32_t unBufferSize, TrackedPropertyError *pError )`**

Returns a property of the appropriate type.


# Controller Methods


**`VRControllerState_t GetControllerState()`**

Returns the initial state of a controller.


**`bool TriggerHapticPulse( uint32_t unAxisId, uint16_t usPulseDurationMicroseconds )`**

Returns a uint64 property. If the property is not available this function will return 0.
