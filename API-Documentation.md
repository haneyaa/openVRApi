# Overview
The OpenVR API provides a game with a way to interact with Virtual Reality displays without relying on a specific hardware vendor's SDK. It can be updated independently of the game to add support for new hardware or software updates. 

The API is implemented as a set of C++ interface classes full of pure virtual functions. When an application initializes the system it will return the interface that matches the header in the SDK used by that application. Once a version of an interface is published, it will be supported in all future versions, so the application will not need to update to a new SDK to move forward to new hardware and other features.

# Initialization and Cleanup

Because the OpenVR API causes the game to connect to any attached VR hardware, it is not initialized automatically. To initialize the API and get access to the vr::IVRSystem interface call the openvr::VR_Init function. To close down your connection to the hardware and release your vr::IVRSystem interface, call openvr::VR_Shutdown.

`vr::IVRSystem *openvr::VR_Init( vr::`[`HmdError`](https://github.com/ValveSoftware/openvr/wiki/HmdError)` *peError )`

The call will return a vr::IVRSystem pointer that allows the game to call other OpenVR API methods. If something fails the call will return NULL and peError will be set to an error code that indicates what the problem was.
peError - The error code that occurred or vr::HmdError_None if there was no error. See `[vr::HmdError](https://github.com/ValveSoftware/openvr/wiki/HmdError)` for possible error codes.

`void openvr::VR_Shutdown()`

Shuts down the connection to the VR hardware and cleans up the OpenVR API. The vr::IVRSystem pointer returned by vr::VR_Init will be invalid after this call is made. 

# Interfaces

The API is broken down into 3 primary interfaces in the vr namespace:
* [IVRSystem](https://github.com/ValveSoftware/openvr/wiki/IVRSystem_Overview) - Main interface for display, distortion, tracking, controller, and event access.
* [IVRChaperone](https://github.com/ValveSoftware/openvr/wiki/IVRChaperone_Overview) - Provides access to chaperone soft and hard bounds.
* [IVRCompositor](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor_Overview) - Allows an application to render 2D or 3D content through the VR compositor.

# Other Functions

`bool openvr::VR_IsHmdPresent()`

Returns true if the system believes that an HMD is present on the system. This function is much faster than initializing all of OpenVR just to check for an HMD. Use it when you have a piece of UI that you want to enable only for users with an HMD.

This function will return true in situations where vr::VR_Init() will return NULL. It is a quick way to eliminate users that have no VR hardware, but there are some startup conditions that can only be detected by starting the system.


`const char *VR_GetStringFor HmdError( vr::HmdError error );`

This function returns an English translation of vr::HmdError enum values. It can be called any time, regardless of whether the VR system is started up.


`void *VR_GetGenericInterface( const char *pchInterfaceVersion, vr::`[`HmdError`](https://github.com/ValveSoftware/openvr/wiki/HmdError)` *peError )`

Requests an interface by name from OpenVR. It will return NULL and pass back an error in peError if the interface can't be found. It will always return NULL if openvr::VR_Init() has not been called successfully.

