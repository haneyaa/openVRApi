# Overview

The vr::IVRExtended display interface provides access to display configuration information. It is only available when the compositor is not running, and `vr::VR_GetGenericInterface` will return `nullptr` and `VRInitError_Init_NotSupportedWithCompositor` if the compositor is running. 

It should be rare to need to use this interface. It is primarily provided for research purposes. Most applications should use the [IVRCompositor](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor_Overview) interface instead.

# Interface Functions

The vr::IVRSystem interface contains the following functions:
* [GetWindowBounds](https://github.com/ValveSoftware/openvr/wiki/IVRExtendedDisplay::GetWindowBounds)
* [GetEyeOutputViewport](https://github.com/ValveSoftware/openvr/wiki/IVRSystem::GetEyeOutputViewport)
* [GetDXGIOutputInfo](https://github.com/ValveSoftware/openvr/wiki/IVRSystem::GetDXGIOutputInfo)
