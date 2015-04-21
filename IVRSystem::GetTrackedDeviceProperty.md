`bool IsTrackedDeviceConnected( vr::TrackedDeviceIndex_t unDeviceIndex )`

`bool GetBoolTrackedDeviceProperty( vr::TrackedDeviceIndex_t unDeviceIndex, TrackedDeviceProperty prop, TrackedPropertyError *pError = 0L )`

`float GetFloatTrackedDeviceProperty( vr::TrackedDeviceIndex_t unDeviceIndex, TrackedDeviceProperty prop, TrackedPropertyError *pError = 0L )`

`int32_t GetInt32TrackedDeviceProperty( vr::TrackedDeviceIndex_t unDeviceIndex, TrackedDeviceProperty prop, TrackedPropertyError *pError = 0L )`

`uint64_t GetUint64TrackedDeviceProperty( vr::TrackedDeviceIndex_t unDeviceIndex, TrackedDeviceProperty prop, TrackedPropertyError *pError = 0L )`

`HmdMatrix34_t GetMatrix34TrackedDeviceProperty( vr::TrackedDeviceIndex_t unDeviceIndex, TrackedDeviceProperty prop, TrackedPropertyError *pError = 0L )`

`uint32_t GetStringTrackedDeviceProperty( vr::TrackedDeviceIndex_t unDeviceIndex, TrackedDeviceProperty prop, char *pchValue, uint32_t unBufferSize, TrackedPropertyError *pError = 0L )`

* `vr::TrackedDeviceIndex unDeviceIndex` - Index of the device to get the property for.
* `vr::TrackedDeviceProperty prop` - Which property to get.
* `vr::TrackedPropertyError *pError` - The error returned when attempting to fetch this property. This can be NULL if the caller doesn't care about the source of a property error.
* `char *pchValue` - The buffer to store string properties in. `unBufferSize` should be the size of this buffer.
* `uint32_t unBufferSize` - The size of the buffer pointed to by `pchValue`.

**Description**

Returns a static property for a tracked device. The different typed GetXTrackedDeviceProperty functions return a value on failure that is generally reasonable for that type:
* GetBoolTrackedDeviceProperty - false
* GetFloatTrackedDeviceProperty - 0.0
* GetInt32TrackedDeviceProperty - 0
* GetUint64TrackedDeviceProperty - 0
* GetMatrix34TrackedDeviceProperty - identity matrix
* GetStringTrackedDeviceProperty - 0 (and 0-length string)

**String Properties**

Because the application owns the buffer to fill with a string property, retrieving a string property is a little different. `GetStringTrackedDeviceProperty` returns the number of bytes necessary to hold the string, including the trailing null. If the buffer wasn't large enough it passes back TrackedProp_StringExceedsMaximumLength as the error and doesn't fill the string into the buffer.

Strings will generally fit in buffers of k_unTrackingStringSize characters.
