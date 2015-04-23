#Overview#

The vr::IVRCompositor interfaces provides access to the Compositor subsystem.  The Compositor simplifies the process of displaying images to the user by taking care of distortion, prediction, synchronization and other subtle issues that can be a challenge to get operating properly for a solid VR experience.

Applications call [WaitGetPoses](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::WaitGetPoses) to get the set of poses used to render the camera and other tracked objects, render the left and right eyes as normal (using the info provided by IVRSystem) and finally [Submit](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::Submit) those undistorted textures for the Compositor to display in its own window.

It is recommended that you continue Presenting your application's own window, reusing either the left or right eye camera render target to draw a single quad (perhaps cropped to a lower fov to hide the hidden area mask).

Example:

    SetGraphicsDevice
    while Running:
        WaitGetPoses
        Render Left and Right cameras
        Submit Left and Right render targets
        Update game logic

Alternatively, you may wish to render serially in order to share a single render target across cameras:

    SetGraphicsDevice
    while Running:
        WaitGetPoses
        Render(L)
        Submit(L)
        Render(R)
        Submit(R)
        Update game logic

When the application exits, or otherwise stops calling Submit for more than 10 frames in a row, it will fade back to an empty grid scene.  This is to avoid ever leaving the user in an untracked environment so users don't fall over or run into walls.  When all applications have disconnected from the compositor, it will exit automatically after two seconds, unless launched with the --keepalive command line argument.

#Enumerations#

[Compositor_DeviceType](https://github.com/ValveSoftware/openvr/wiki/Compositor_DeviceType)

[Compositor_FrameTiming](https://github.com/ValveSoftware/openvr/wiki/Compositor_FrameTiming)

[Compositor_TextureBounds](https://github.com/ValveSoftware/openvr/wiki/Compositor_TextureBounds)

#Interfaces#

The vr::IVRCompositor interface contains the following functions:

[GetLastError](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::GetLastError)

[SetVSync](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::SetVSync)

[GetVSync](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::GetVSync)

[SetGamma](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::SetGamma)

[GetGamma](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::GetGamma)

[SetGraphicsDevice](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::SetGraphicsDevice)

[WaitGetPoses](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::WaitGetPoses)

[Submit](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::Submit)

[ClearLastSubmittedFrame](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::ClearLastSubmittedFrame)

[GetOverlayDefaults](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::GetOverlayDefaults)

[SetOverlay](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::SetOverlay)

[SetOverlayRaw](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::SetOverlayRaw)

[SetOverlayFromFile](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::SetOverlayFromFile)

[ClearOverlay](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::ClearOverlay)

[GetFrameTiming](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::GetFrameTiming)

[FadeToColor](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::FadeToColor)

[FadeGrid](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::FadeGrid)

[CompositorBringToFront](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::CompositorBringToFront)

[CompositorGoToBack](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::CompositorGoToBack)

[CompositorQuit](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::CompositorQuit)

[IsFullscreen](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::IsFullscreen)

[ComputeOverlayIntersection](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::ComputeOverlayIntersection)

[SetTrackingSpace](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::SetTrackingSpace)

[GetTrackingSpace](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::GetTrackingSpace)

