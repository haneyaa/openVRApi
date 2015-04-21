`bool GetTimeSinceLastVsync( float *pfSecondsSinceLastVsync, uint64_t *pulFrameCounter )`

Returns the number of elapsed seconds since the last recorded vsync event. This 
will come from a vsync timer event in the timer if possible or from the application-reported
time if that is not available. If no vsync times are available the function will 
return zero for vsync time and frame counter and return false from the method.

* `pfSecondsSinceLastVsync` - Fractional number of seconds since the last vsync event. This will never exceed the length of a single frame
* `pulFrameCounter` - The number of frames since vrserver.exe started.


