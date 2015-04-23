Fades the view on the HMD to the specified color. The fade will take fSeconds, and the color values are between 0.0 and 1.0. This color is faded on top of the scene based on the alpha parameter. Removing the fade color instantly would be FadeToColor( 0.0, 0.0, 0.0, 0.0, 0.0 ).

	virtual void FadeToColor( float fSeconds, float fRed, float fGreen, float fBlue, float fAlpha, bool bBackground = false ) = 0;
