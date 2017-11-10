#  January
 
##  05

- infinite scrolling - **adjust content offset and move content center**
- stationary header view - **insert as another subview in scrollview and reposition it**
- more gestures recognisers - user recognize to fail, and restrict area for it
- redraw - using **setContentScale** multiply by screen scale

## 07

- **locked files** in mac os x & lock mount image file with a password

## 12

- **designated initializer** must call super. It can de defined by initialized its state thoroughly
- secondary or convinience initializer always call designated one
- the NSObject class declares the init method as the default object initializer, so it is always invoked last but returns first

## 13

- animate start screen after splash is possible without constraints

## 14

- **UIView can be tinted**. (Use tintColor to tint bar button items; use barTintColor to tint the bar background)
- you can also provide a custom input accessory view, which is a separate view that appears above the keyboard
- audioTorch - apple sample for FFT, and audio visuzalization
- **strokeEnd** is animatable property

## 15

- awake - load all outlets
- use context to pass data
- notification (quick / long), sash and glance
- **wk app - target for all resources, that will be contained in apple watch physically**
- **wk extension - target for all code, that will be compiled and transfers to watch for execution**
- SF compact text (<19) / display (>20)
- images are with opaque background 
- flat design
- conversational ui
- minimalism & custom graphics 
- microinteractions & scroll animation
- animated tutorials
- unlike using a delegate, instances of picker are configured with a first-class object

## 17

- application:shouldAllowExtensionPointIdentifier
- settings bundle is just added via new file. Register for user defaults and than use standard one ink

## 20

- root interface element of WKInterfaceController is a group
- **we can configure headers and rows using custom data manipulation - watchKit so be careful about it**
- **we can easily setup page controllers, just using techniques for presenting several controllers**
- watchOS will always report the logical interface direction to you regardless of the orientation of the device on the user's wrist. 
- **Up is positive, down is negative**
- we can’t connect IBAction to extension in Swift
- due to this architecture, you can't create objects in code and add them to the interface in code like you might on iOS. 
- in watchOS, you can't use a gesture recognizer on an entire interface. You must attach a gesture recognizer to a specific object in the interface. Usually, you'll want to choose an object that will fill the screen. In this case, the Graph Image object fits the bill. 
- locationInObject() - for *WKGestureRecognizer*
- snapshot can be different from UI, but it should not be completely another
- we can increase fonts and other stuff especially for snapshot
- **watchOS automatically schedules snapshots to update on your behalf in many different scenarios**: 
	- when the Apple Watch boots up
	- when a complication update occurs
	- when the user exits the app
	- when the user views a long look notification
	- one hour after the user last interacted with the app
	- at least once an hour for apps in the Dock. (The Dock takes one snapshot every six minutes rotating through each app in sequence. If the user has fewer than ten apps in the Dock, then each app will receive more frequent snapshot tasks than one per hour.)
	- at optional, scheduled times, with the Background Refresh API  
- restoredDefaultState for root controller
- estimatedSnapshotExpiration - as default - use **Date.distantFuture**
- we can simulate UI snapshot in Xcode
- importance of Watch App Name
- tvOS is great platform: we can use two approach - one is native development, and the second one is using JavaScript with TV Markup Language

>>>Телевизор отупляет и убивает много времени. Отключите его, и вы сохраните немного серого вещества. Но будьте осторожны – отупеть можно и за компьютером Apple.

- `NSEC_PER_SEC`

## Notifications

- appears in iOS 3
- remote silent in iOS 7
- actionable in iOS 8
- notification will be displayed on current device, otherwise at watch
- there are static vs dynamic notifications
- **you can not add interactive elements in notifications in watch**
- if you run watch app before iPhone app, the iPhone does not install itself in the simulator
- diawi - platform for distribute .ipa files