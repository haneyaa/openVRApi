`void GetDXGIOutputInfo( int32_t *pnAdapterIndex, int32_t *pnAdapterOutputIndex )`

**D3D10/11 Only**

Returns the adapter index and output index that the user should pass into EnumAdapters adn EnumOutputs 
to create the device and swap chain in DX10 and DX11. If an error occurs both indices will be set to -1.

* `pnAdapterIndex` - The index of the adapter to use for this display.
* `pnAdapterOutputIndex` - The index of the adapter output to use for this display.

