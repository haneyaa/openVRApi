# Overview

The vr::IVROverlay interface provides access to draw 2D images over the 3D scene no matter which application is running. Provided functions allow the application to control how each overlay is presented, what it contains, and to receive events.

The most common type is a Dashboard overlay, which adds a tab to the VR Dashboard. The user can select one active tab and the application is signaled when that happens. Simulated mouse events from the user pointing a tracked controller at the dashboard are sent to the application through events. See the [helloworldoverlay sample](https://github.com/ValveSoftware/openvr/tree/master/samples/helloworldoverlay) for an example.

Each overlay has a unique `VROverlayHandle_t`. This handle is used to set attributes, receive events, and render into the overlay. There are several circumstances where an overlay is not known or is otherwise invalid. In those cases the handle will be equal to `k_ulOverlayHandleInvalid`.

# Interface Functions

The vr::IVROverlay interface provides the following functions:
* Overlay Management:
  * [FindOverlay](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::FindOverlay)
  * [CreateOverlay](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::CreateOverlay)
  * [DestroyOverlay](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::DestroyOverlay)
  * [SetHighQualityOverlay](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetHighQualityOverlay)
  * [GetHighQualityOverlay](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::GetHighQualityOverlay)
  * [GetOverlayKey](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::GetOverlayKey)
  * [GetOverlayName](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::GetOverlayName)
  * [GetOverlayImageData](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::GetOverlayImageData)
  * [GetOverlayErrorNameFromEnum](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::GetOverlayErrorNameFromEnum)
* Overlay Rendering:
  * [SetOverlayFlag](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayFlag)
  * [GetOverlayFlag](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayFlag)
  * [SetOverlayColor](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayColor)
  * [GetOverlayColor](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayColor)
  * [SetOverlayAlpha](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayAlpha)
  * [GetOverlayAlpha](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayAlpha)
  * [SetOverlayGamma](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayGamma)
  * [GetOverlayGamma](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayGamma)
  * [SetOverlayWidthInMeters](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayWidthInMeters)
  * [GetOverlayWidthInMeters](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayWidthInMeters)
  * [SetOverlayAutoCurveDistanceRangeInMeters](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayAutoCurveDistanceRangeInMeters)
  * [GetOverlayAutoCurveDistanceRangeInMeters](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayAutoCurveDistanceRangeInMeters)
  * [SetOverlayTextureBounds](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayTextureBounds)
  * [GetOverlayTextureBounds](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayTextureBounds)
  * [GetOverlayTransformType](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::GetOverlayTransformType)
  * [SetOverlayTransformAbsolute](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayTransformAbsolute)
  * [GetOverlayTransformAbsolute](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayTransformAbsolute)
  * [SetOverlayTransformTrackedDeviceRelative](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayTransformTrackedDeviceRelative)
  * [GetOverlayTransformTrackedDeviceRelative](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayTransformTrackedDeviceRelative)
  * [ShowOverlay](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::ShowOverlay)
  * [HideOverlay](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::ShowOverlay)
  * [IsOverlayVisible](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::IsOverlayVisible)
* Overlay Input:
  * [PollNextOverlayEvent](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::PollNextOverlayEvent)
  * [SetOverlayInputMethod](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayInputMethod)
  * [GetOverlayInputMethod](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayInputMethod)
  * [SetOverlayMouseScale](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayMouseScale)
  * [GetOverlayMouseScale](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayMouseScale)
  * [ComputeOverlayIntersection](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::ComputeOverlayIntersection)
  * [HandleControllerOverlayInteractionAsMouse](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::HandleControllerOverlayInteractionAsMouse)
* Setting Overlay Textures:
  * [SetOverlayTexture](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayTexture)
  * [ClearOverlayTexture](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::ClearOverlayTexture)
  * [SetOverlayRaw](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayRaw)
  * [SetOverlayFromFile](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetOverlayFromFile)
* Dashboard Overlays:
  * [CreateDashboardOverlay](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::CreateDashboardOverlay)
  * [IsDashboardVisible](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::IsDashboardVisible)
  * [IsActiveDashboardOverlay](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::IsActiveDashboardOverlay)
  * [SetDashboardOverlaySceneProcess](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::SetDashboardOverlaySceneProcess)
  * [GetDashboardOverlaySceneProcess](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::GetDashboardOverlaySceneProcess)
  * [ShowDashboard](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::ShowDashboard)
