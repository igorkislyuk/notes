# 2016

- UIActivityIndicator view can be used as tableview accessory view
- to display popover on iPhone - set delegate and return none from style method
- better include primitives in complex data types, rather than subclass it. Override only need to re-implement low-level behaviour
- UIStackView: hidden property animatable and hidden views are not displayed
- **initWithFrame: - code & initWithCoder: - xib**
- target and action doesn’t work for UIBarButton with custom view
- layoutIfNeeded animatable change constraints
- UILayoutGuide instead of dummy views
- NSDictionaryOfVariableBindings
- No deallocation in size-classes between elements
- @syncronized(self.property) { read/write self.property}
- when frame of the view changes
	- view removed from the superview then it will be called on superview
	- in UIScrollview, during scrolling
	- while adding the view to superView
	- during orientation 

- write specific code for specific cell types
- perform rounding of all pixel-relating data: point coordinates, heights/widths
- track your graphical resources: **images must be pixel-perfect**, else when they will be rendered on Retina displays, it will be doing with unnecessary antialiasing
- **periodically recheck your situation** with this problem because it can changes very quickly
- find render bottlenecks which don’t allow you to return cells very fast
move operations to background thread and refresh displayed content on the main thread
- last resort is setting up your CALayers for asynchronous displaying mode (even if they are about simple text or images) — this will help you to increase FPS
- **more subviews you have, less quickly autolayout works**

- **UIRequiresFullScreen** used this to disable split mode in iPad
- nullable — Think UIView?
- nonnull — Think UIView
- null_unspecified — Think UIView!
- scroll inset affects on initial layout (own experience)

#### CoreAnimation Notes

- four different tree in iOS: view/layer(model)/presentation/render
- contents(id), contentsScale, contentsGravity, maskToBounds
- sprites. contentsRect & contentsCenter
- CALayerDelegate, displayLayer: or drawLayer:: better use drawRect: in UIView
- **why Apple recommends NOT use empty `drawRect:`?**
- properties: position(a. k. a. center), frame, bounds
- **frame is just computed from bounds, transform, position**
- anchorPoint in unit
- zPosition is very low value
- prefer views over layers
- hitTest & convertPoint
- beginReceivingRemoteControlEvents / endReceivingRemoteControlEvents in UIApplication
- **border inside and before all inner contents**
- shadowOpacity (0) / shadowColor / shadowOffset (CGSize) / shadowRadius
- shadow match contents
- if content overflows - shadow will be dropped with clipsToBounds
- shadowPath
- mask for CALayer
- minificationFilter / magnificationFilter with bilinear / trilinear / nearest
- UIViewGroupOpacity YES
- shouldRasterize / rasterizatoinScale
- **shear transform - not an affine transform**
- `CATransform3D`
- **m34** perspective
- backfaces and **doubleSided** property
- **handling events rely on zIndex nor on appearance order**
- layer containsPoint and convertPoint
- **mainBundle is immutable for writing**
- layerClass class method in the UIView class
- keyframe animation and transition with view - that works with snapshots
- **leading (line spacing) & kerning (spacing between letters)**
- substringFromIndex - from index do not include
- CATiledLayer integrates nicely with scroll view using CALayer delegate
- CA not support autoresizing or auto layout
- **viewForKey: in animation could be nil**

- **it’s slower to insert or delete elements from a mutable array than a set or a dictionary**
- diff -u $FILE-OLD $FILE-NEW
- CALayer animated automatically
- CATransaction / begin / commit / duration / completion block
- UIView beginAnimations:context: / commitAnimations
- **WHY DOES UIVIEW DISABLE IMPLICIT ANIMATIONS?**
- CATransaction setDisableActions:
- `CATransition`
- long and long long - int types
- blur - **CIFilter** & **UIImage+ImageEffects** (slower)
- better use in background thread

#### Google search master
 
- Site:
- `-word`
- time ranges
- define:word

- leave from value nil. Will use current value - for animation where specify **from** and **to**
- scrollPoint scrollRectToVisible
- smb 445 - for connection windows and mac
- *addAnimation:forKey:* - key uniquely identifies animation
- CAKeyframeAnimation doesn’t know about initial value
- CATransition. Always key @"transition"
- there are difference between type and subtype
- difference push / move in / reveal
- capture layer in context to image
- repeatCount and repeatDuration
- CAMediaTimingProtocol
- beginTime & timeOffset, speed
- duration / **begin time** / **time offset** / **speed** / repeat count / repeat duration will impact on children layer / animation 
- fill mode - when animation could take frame before or after itself
- if you are not use remove on completion -> use custom key for remove it manually
- media time for device

- **the fewer conditions you test for, the better your code “tastes"**
- voip to prevent close socket, location to wake up program, for leaving location, and local notification to wake up program
- UIControl subclass of UIView with adding target / action pattern
- media timing function
- easing
- keyframe animation - timing functions [keyframes - 1 for count]
- get values at index for point in timing function
- two approach - timer base animation and keyframe based - 60 frames per second
- every thread in running in nsrunloop
- CADisplayLink - specific draw timer
- different work in cadisplay link versus nstimer
- **NSDefaultRunLoopMode**
- **NSRunLoopCommonModes**
- **UITrackingRunLoopMode**
- add in run loop with several modes

#### 16.11

- instance variable in initializer
- strong or weak reference to outlet? Depends on root
- for in faster than for
- formal and informal protocol - as NSObject category

#### 17.11

- **layout -> display -> prepare (in render server) -> commit -> calculates values -> render**
- cpu-bound: geometry - overdraw - offscreen drawing - large images
- gpu-bound: layout calculation, lazy view loading, cg drawing, image decompression
- **measure, don’t guess!**

#### 18.11

- cg for vector drawing
- dirty rectangles - means rect need to be redrawn
- async drawing
- image decompression
- for fast decompression image can drawn at cg context - **deferred decompression**
- imageNamed - auto cached and decompression or use tile layer for same effect
- resolution swapping for fast-scrolling collection
- NSCache
- offscreen rendering
- **shape layer better than pure CGDrawing**
- blending, clipping
- reduce layer count
- load as demand
- renderInContext:
- **if layer is not attached to view hierarchy it will not impact on render process**

#### 21.11

- **string additionally wraps with quotes in predicate**
- @dynamic tell that accessor will be provided at runtime
- predicate **%K** for key
- indexOfObjectPassingTest:
- **complete / none / complete until already open / complete until first authenticate**
- **check if Class object is nil - for newer iOS**
- call window method makeAnyKey from will finish
- SF-UI in iOS 

#### 22.11

- runloop with current thread. As default is not launched
- autorelease at each iteration
- autorelease for whole application - why? Generate new object. Directly Application
- reason for using NSThread
- NSPort and successors for communication between threads
- when we need runloop? - for task which will have own thread
- for all objects <NSCopying> use copy instead of retain (strong)

#### 23.11

- read - do not make from READING list
- do - do not read from DOING LIST
- be consistent
- and make your plan alive with 2 weeks goal

#### 25.11

- use similar conventions for test
- don't let ourselves in HDD(Hype)
- triple A - arrange, act, assert
- mocks and stubs
- for test use primates equal and non-primitives equalObjects

#### 26.11

- **no dictionaries use objects**
- **copy, new, mutable copy, alloc** implicitly call retain 
- Property set: **retain new, release old, assign to instance**
- cocoa establishes a **convention**, therefore, that a “parent” object should maintain strong references to its “children,” and that the children should have weak references to their parents
- **collections own objects**

#### 26.11

- **print[p] and expression[e]. What else can we get from debugger?**
- finish
- thread return 
- **frame info - frame from stack**
- modifying program
- custom actions

#### 30.11

- lazy loading difference in xib / storyboards. What you can say about it?

#### 04.12

- hash for set
- DispatchQueue
- System Sound Services 

#### 05.12

- 0.0 in **graphics context impacts give retina scale** - 1/2/3

#### 06.12

- NSFilemanager / defaultManager / currentDirectoryPath
- NSTemporaryDirectory
- remove directory - remove item at path
- contents of directory at path

#### 07.12

- UIPresentationController - what is it and for what?

#### 09.12

- custom operation, that can be cancelled. Async operation

#### File Manager

- check if file exists
- compare two files
- check if file read/write/exec/deletable
- move / remove / extract to data
- file handle 
- working with offset of cursor
- writing data on with cursor always override existing data

#### 11.12

- centre line **⌃ + L**
- delete entire line **⌃ + K**
- auto adjust scroll insets - property in UIViewController
- sassume unchanged
- **atomic always read proper data**
- **nonatomic little faster**
- **readwrite in extension**

#### 13.12

- uisearchcontroller
- ui search bar can defines scope underneath
- memory barrier - for multithread programming
- PersonNameComponents

#### 21.12

- ascii 7bit
- code page - one encoding
- unicode transformation format
- **byte order mask**
- **utf-8**
- **directory read vs directory execute**
- if we need compare unicode strings -> use normalised form of it

#### 22.12

- work with round corner. Don’t need to rechange underlaying layer. Just apply the mask
- **traits** - methods bodies
- **mixin** has state
- it’s recommended to remove “Host Application” from your Unit Test target configuration and run your tests without your application running on simulator

#### 23.13

- updating table will not give 60 fps - begin/end
- we can catch gesture for web view
- opaque layers
- way to cache - offscreen rendering
- green/yellow/red for offscreen rendering 
- context stack for ui kit
- argb vs xrgb
- context per thread 

####  24.12

- unix: ok -> doesn't show anything
- code signing works with no exceptions
- entitlement is for specific system resources 
- PEM and CMS formats for encoding
- provision profile list all available certificates 
- we can use images, gifs and videos in custom notifications 

#### 25.12

- load vs initialise for class. Load always invokes
- swizzling in dispatch once
- selector - string, that represents function name
- `typedef struct objc_selector *SEL`
- `typedef struct objc_method *Method`
- imp - pointer to the start of the function
- **class - table of methods - each method - table with selector and implementation**
- **storyboards can load custom fonts**

#### 26.12

- contents rating
- responds to selector either instance or class
- C function is NULL

#### 27.12

- Restoration process
- encoding
- ask for restoration class / app delegate / restoration identifier / miss it
- encode / decode restorable state of controller
- selection range for text fields
- application encode additional state
- force quit does not allow to preserve state of application
- voip push notification
- NSStackBlock / NSGlobalBlock
- **for stack block use copy, it is located at stack, and retain has no power**
- if you need a genuinely separate copy, recreate the block, don't copy it

#### 28.12

- SwiftyJSON is the niece lib for extracting values from json. Not for mapping

#### 31.12

- entry point as a destination controller for testing
- the best way to perform expandable cell - deal with plist
- get IMP of current method is a little tricky, so we can use
- `__builtin_return_address(0)` in gcc
- action sheet, popover and alert
- full screen with main done/save/agree and cancel

