`bool PollNextOverlayEvent( VROverlayHandle_t ulOverlayHandle, VREvent_t *pEvent )`

Returns true and fills the event with the next event on the overlay's event queue, if there is one. If there are no events this method returns false.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to retrieve events for
* `VREvent_t *pEvent` - Receives the next event off the queue

