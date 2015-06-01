Every driver dynamic library needs to implement the standard driver factory function and use it to return implementations of the OpenVR driver interfaces.

A typical factory function looks like this:

    HMD_DLL_EXPORT void *HmdDriverFactory( const char *pInterfaceName, int *pReturnCode )
    {
    	if( 0 == strcmp( IServerTrackedDeviceProvider_Version, pInterfaceName ) )
    	{
    		return &g_serverDriverNull;
    	}
    	if( 0 == strcmp( IClientTrackedDeviceProvider_Version, pInterfaceName ) )
    	{
    		return &g_clientDriverNull;
    	}
    
    	if( pReturnCode )
    		*pReturnCode = HmdError_Init_InterfaceNotFound;
    
    	return NULL;
    } 