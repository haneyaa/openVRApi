`VROverlayError SetDashboardOverlaySceneProcess( VROverlayHandle_t ulOverlayHandle, uint32_t unProcessId )`
`VROverlayError GetDashboardOverlaySceneProcess( VROverlayHandle_t ulOverlayHandle, uint32_t *punProcessId )`

Sets or gets  the dashboard overlay to only appear when the specified process ID has scene focus.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to set/get the scene process for
* `uint32_t unProcessId` - The dashboard overlay will only be offered for this scene process
* `uint32_t *punProcessId` - Receives the process ID that the dashboard overlay will be offered for

