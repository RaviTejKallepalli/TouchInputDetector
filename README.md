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
    
** There are more than one way for the user to interact with our application. When considering events within our UI, the approach is to capture the events from the specific View object that the user interacts with. The View class provides the various methods for this purpose. These methods are called by the Andriod framework when the respective actions occurs on the View object. For example: When a Button(View) is touched, the onTouchEvent() method is called one the object. However inorder to intercept this, you must extend the class and override the method callbacks(Event listeners) that you can use. **
  


