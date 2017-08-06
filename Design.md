
# Design

## AppDelegate.swift

1.  creates the window where your app’s content is drawn and provides a place to respond to state transitions within the app.
2. creates the entry point to your app and a run loop that delivers input events to your app. This work is done by the UIApplicationMain attribute (@UIApplicationMain), which appears toward the top of the file.
3. In response, the system creates an application object. The application object is responsible for managing the life cycle of the app. The system also creates an instance of your AppDelegate class, and assigns it to the application object. Finally, the system launches your app.
4. The AppDelegate class adopts the UIApplicationDelegate protocol. This protocol defines a number of methods you use to set up your app, to respond to the app’s state changes, and to handle other app-level events.


## set image view
	imageView.image = UIImage(named :"")
## Layout
We often work with `Attributes Inspector`

Automatically make label fit the words inside it: `command+ =`

### Auto Layout
Nest image views inside a View, creating child parent relationship
Auto Layout dynamically calculates the size and position of each element based on these constraints. With a stack view `(UIStackView)` it provides a streamlined interface for laying out a collection of views in either a column or a row. The stack view uses Auto Layout under the hood to calculate the size and position of all the views that it manages. This lets you easily access the full power of Auto Layout, while greatly reducing the complexity of your layout.

To adopt Auto Layout, wrap your existing interface elements in a stack view, and then add the constraints needed to position the stack view in the scene.


1. While pressing the Shift key on your keyboard, select the text field, label, and button. On the bottom right of the canvas, click the Embed In Stack button. (Alternatively, choose Editor > Embed In > Stack View.) Xcode wraps the user interface elements in a stack view, stacking them together. Xcode analyzes your existing layout to figure out that the items should stack vertically, not horizontally.
2. open the outline view. Select the Stack View object.In the Attributes inspector, type 8 in the Spacing field to change spacing, and the stack will grow as well
3. On the bottom right of the canvas, open the Add New Constraints menu.
These constraints indicate spacing to the nearest leading, trailing, and top neighbors. 
In the pop-up menu next to Update Frames, choose Items of New Constraints. This causes Interface Builder to automatically update the frames of the affected views when you create the constraints.
In the Add New Constraints menu, click the Add 3 Constraints button.
The label, text field, and button are now left aligned and laid out with appropriate spacing, but the text field still isn’t stretching to fill the screen’s width. To fix that, you’ll need to add an additional constraint.

### Pining
a fixed distance from the screen, square will expand from small screen to large screen
### Alignment
keep the square the same size, fixed width and height, always in the centre

## Connecting UI and Source Code

