#  March

Since iOS 7 we can't send more than 4 concurrent network requests.
Before it was 6. Exceeding this limitations will give you **-1001** error.

You probably want to avoid doing rendering on the CPU, but instead offload it to the GPU. There is one rule of thumb to achieve this: try to avoid `drawRect:`, and instead compose your custom views out of existing views.

You can use AVFoundation to speak text. Now only usable at US Phones

- Changing bounds does not affect on center
- Also changing center does not affect on bounds
- But frame affects both, on bounds and on center
- If you change bounds within superview - you subview are not moved
- default keyword in Swift is not valid, it means there is some default value but you are not allowed to see it (or maybe the generator cannot compile it right for you to see it)
- You can use UILayoutGuide instead of dummy views. Otherwise, better use UIStackView
- You can disable ambiguity for view in IB(starting Xcode 8)
- AppState could be converted in state machine. If it needed for very complex and big applications
- Создав блок асинк и запустив его, а также послав сообщение релиз ему. Он выполнится. Так же само и с NSOperation
- **Tagged pointer - используется для NSNumber, когда число маленькое и передаётся непосредственно. Определяется первым битом**
- We can tile and stretch image using methods from UIImage class. This is important thing, that you do not need to go deep to CA

Difference between IUO and optional:

- can call methods
- can simply cast to value
- used for deferring initialization
- in all suitable cases cast to Optional

About drawing in context. There are three ways to do it:

- Implicit context for UIKit
- Explicit for CG
- Context that passed in CALayer delegate `draw(:in:)`

You should push or pop it. Although, there is graphics renderer for convenience since iOS 10.

[NSHashTable & NSMapTable](http://nshipster.com/nshashtable-and-nsmaptable/) such is beautiful stuff for solving nob-trivial tasks. In general, there are set and dictionary - for most than 99% of problems. UIVideoEditorController like uiimage picker.

Interesting thing about how iOS animations really work: there are actions, CAAction, some KVC, method `run`, `action(forKey:)`, few dictionaries - styles and actions.

Better use gesture recognisers other than touches. 

**MVC - triangle, MVA - one line. So Apple MVC is almost MVA.**

**If you know mechanism of view replacing during presentation, that means overFullScreen just WONT remove previous view**

- Define presentation context and setup modal presentation style for `.currentContext`.
- Delegate for reverse communication 
- Navigation item per each controller. Navigation bar itself a stack of items
- To use images appropriate, we can use bar items and assign image as a transparency mask
- `parent` property of UIViewController  

```swift
import WebKit
import CFNetwork
```
There are frameworks if you’re rejected during IPv6 framework.

Calling `type(of:)` on an instance, or self on a Class/Structure `.self` is used on a Type to returns its metatype `type(of:)` is used on an instance to return its type.

Variable annotated with String.Type or any Struct.Type can only store that struct meta-type.

How segues are worked including unwind ones. They are searching all UIViewController tree. **JS & Swift could exchange information**, and even function calls

- SwiftProtocol.Type
- No weak self in UIView animate closure
- Type properties declared in this way are generally preferred over global constants because they are easier to distinguish from instance properties. For empty arrays and dictionaries, use type annotation. For an array or dictionary assigned to a large, multi-line literal, use type annotation.

