# September

## 1

- `NSSet`
- `NSOrderedSet`
- `NSCountedSet`

## 2

- `direct` dispatch
- `table` dispatch
- `message` dispatch
- dynamic enables message dispatch on a method defined in a class
- final enables direct dispatch on a method defined in a class
- it is also possible to mark a method as finaland make the method available to message dispatch with `@objc`. This will cause invocations of the method to use direct dispatch, and will register the selector with the Objective-C runtime
- `Optional` covariant not working

## 4

- `DateInterval` from iOS 10

## 5

- `Optional` as `AnyObject`

## 6

- Buttons dispatch table
- nil-target events. Works to first selector in Responder Chain
- to disable non-english keyboards. Use keyboard settings for uitextfield

## 7

- to disable shadow on `UISlider` simply set up image
- for increasing hot spot override `pointInside:withEvent`
- `xcrun ibtool --export-strings-file output.strings XIBNAME`
- `xcrun genstrings SOURCE-CODE-PATH`

## 8

- `addTarget(self, action: SELECTOR, for: .primaryActionTriggered)` from iOS 9

## 9

- `NSTimer` retains object until it invalidated

## 10

- You must use `copy` for all basic Objective-C type (aka `NSString`, `NSArray`), because you can pass mutable subclass and change object behinds back.


- to be continued...
