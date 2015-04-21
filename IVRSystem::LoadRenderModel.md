`bool LoadRenderModel( const char *pchRenderModelName, RenderModel_t *pRenderModel )`
	
Loads and returns a render model for use in the application.

* `pchRenderModelName` - Name of the render model to load.
* `RenderModel_t *pRenderModel` - struct to receive the render model.

**Description**
Loads and returns a render model for use in the application. pchRenderModelName should be a render model name
from the Prop_RenderModelName_String property or an absolute path name to a render model on disk. 

The resulting render model is valid until VR_Shutdown() is called or until FreeRenderModel() is called. When the 
application is finished with the render model it should call FreeRenderModel() to free the memory associated
with the model.

The method returns false if the model could not be loaded.

The API expects that this function will be called at startup or when tracked devices are connected and disconnected.
If it is called every frame it will hurt performance.

