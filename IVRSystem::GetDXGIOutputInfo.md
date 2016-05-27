`void GetDXGIOutputInfo( int32_t *pnAdapterIndex )`

**D3D10/11 Only**

Returns the adapter index that the user should pass into EnumAdapters 
to create the device and swap chain in DX10 and DX11. If an error occurs the index will be set to -1.

* `pnAdapterIndex` - The index of the adapter to use for this display.

