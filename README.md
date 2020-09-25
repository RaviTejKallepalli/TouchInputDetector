# Touch and input
The following section covers basics about the user inputs.

- Touch input
- Gestures
- Keyboards inputs

## Input events overview

- Event listeners
- Event handlers
- Touch mode
- Handling focus
    
There are more than one way for the user to interact with our application. 
When considering events within our UI, the approach is to capture the events 
from the specific View object that the user interacts with. 
The View class provides the various methods for this purpose. 
These methods are called by the Andriod framework when the respective actions occurs on the View object. 
For example: When a Button(View) is touched, the onTouchEvent() method is called one the object. 
However inorder to intercept this, you must extend the class 
and override the method callbacks **(Event listeners)** that you can use.
  
### Event listeners

- onClick()
- onLongClick()
- onFocusChange()
- onKey()
- onTouch()

**Note:** returns a boolean to indicate whether you have consumed the event and it should not be carried further. That is, 
**return true** to indicate that *you have handled* the event and it should stop here;
**return false** if *you have not handled it* and/or the event should continue to any other on-click listeners.


### Event handlers

When building a custom component from View, then you'll be able to define several callback methods used as default event handlers

- onKeyDown(int, KeyEvent) - Called when a new key event occurs.
- onKeyUp(int, KeyEvent) - Called when a key up event occurs.
- onTrackballEvent(MotionEvent) - Called when a trackball motion event occurs.
- onTouchEvent(MotionEvent) - Called when a touch screen motion event occurs.
- onFocusChanged(boolean, int, Rect) - Called when the view gains or loses focus.

When managing more complex events inside a layout, consider these other methods:

- Activity.dispatchTouchEvent(MotionEvent) = This allows your Activity to intercept all touch events before they are dispatched to the window.
- ViewGroup.onInterceptTouchEvent(MotionEvent) = This allows a ViewGroup to watch events as they are dispatched to child Views.
- ViewParent.requestDisallowInterceptTouchEvent(boolean) = Call this upon a parent View to indicate that it should not intercept touch events with onInterceptTouchEvent(MotionEvent).


### Touch mode

When a user is navigating a user interface with directional keys or a trackball, it is necessary to give focus to actionable items (like buttons) so the user can see what will accept input. If the device has touch capabilities, however, and the user begins interacting with the interface by touching it, then it is no longer necessary to highlight items, or give focus to a particular View. Thus, there is a mode for interaction named "touch mode."

For a touch-capable device, once the user touches the screen, the device will enter touch mode. From this point onward, only Views for which isFocusableInTouchMode() is true will be focusable, such as text editing widgets. Other Views that are touchable, like buttons, will not take focus when touched; they will simply fire their on-click listeners when pressed.

**To query the current you can call isInTouchMode() to verify if the device is currently in touch mode or not**