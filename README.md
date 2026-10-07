# Non-ScreenSaver_ScreenSaver
Non-Screen Saver Screen Save for long running processes that will break if the actual screen saver cuts on

On load: it requests a screen wake lock right away. If the browser wants a user gesture first, it retries on your first click or keypress, so entering full screen will do it.
Fallback: if the browser doesn't support the Wake Lock API, it feeds the canvas into a tiny hidden muted video. Browsers treat playing video as active viewing and hold off the screen saver. I couldn't test the fallback in my headless setup, only that the page loads and the W toggle runs without errors.
Tab switches: the lock drops whenever the tab is hidden, so the page re-grabs it when you come back or change full-screen state.
W: now turns the keep-awake off and on, in case you ever want the normal screen saver back.
