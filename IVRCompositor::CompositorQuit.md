Tells the compositor process to clean up and exit. You do not need to call this function at shutdown. Under normal circumstances the compositor will manage its own life cycle based on what applications are running.

	virtual void CompositorQuit() = 0;
