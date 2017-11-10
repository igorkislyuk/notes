# September

## 01

- `NSSet` & `NSOrderedSet` & `NSCountedSet`

## 02

- `direct` dispatch
- `table` dispatch
- `message` dispatch
- dynamic enables message dispatch on a method defined in a class
- final enables direct dispatch on a method defined in a class
- it is also possible to mark a method as finaland make the method available to message dispatch with `@objc`. This will cause invocations of the method to use direct dispatch, and will register the selector with the Objective-C runtime
- `Optional` covariant not working

## 04

- `DateInterval` from iOS 10

## 05

- `Optional` as `AnyObject`

## 06

- Buttons dispatch table
- nil-target events. Works to first selector in Responder Chain
- to disable non-english keyboards. Use keyboard settings for uitextfield

## 07

- to disable shadow on `UISlider` simply set up image
- for increasing hot spot override `pointInside:withEvent`
- `xcrun ibtool --export-strings-file output.strings XIBNAME`
- `xcrun genstrings SOURCE-CODE-PATH`

## 08

- `addTarget(self, action: SELECTOR, for: .primaryActionTriggered)` from iOS 9

## 09

- `NSTimer` retains object until it invalidated

## 10

- You must use `copy` for all basic Objective-C type (aka `NSString`, `NSArray`), because you can pass mutable subclass and change object behinds back.

## 30

- optional can be compared
- `typedef NS_OPTIONS();`
- `lexicographicallyPrecedes`
- **type constructors — such as optionals or arrays — that support a map operation are sometimes referred to as functors**
- контракт чего либо - инвариант
- в своих трудах Барбара Лисков строила свой анализ на основе контрактов класса: **предусловий, постусловий и инвариантов**
- **group.com.littlebites.cache, group.com.littlebites.user** - Apple encourages to begin these with the group
- cannot retain self on value type

### Kotlin

- object expressions are executed (and initialized) immediately, where they are used
- object declarations are initialized lazily, when accessed for the first time
- a companion object is initialized when the corresponding class is loaded (resolved), matching the semantics of a Java static initializer
- the default upper bound (if none specified) is Any?
- the name of the companion object can be omitted, in which case the name Companion will be used
- in addition to `out`, Kotlin provides a complementary variance annotation: `in`. It makes a type parameter contravariant: it can only be consumed and never produced. A good example of a contravariant class is Comparable
- deferred initialisation
 - `If not null and else` shorthand
 - execute `if not null`
 - `return when`
- `with` calling
- labels for loops, return labels for functions
- custom setters for must call functions that will set values to other properties
- backing field `field`
- compile time constants with `const`
- you can declare properties in interfaces. A property declared in an interface can either be abstract, or it can provide implementations for accessors. Properties declared in interfaces **can't have backing fields**, and therefore accessors declared in interfaces can't reference them
- extensions resolved statically 
- in case of a name conflict between the members of the dispatch receiver and the extension receiver, the extension receiver takes precedence
- extensions declared as members can be declared as open and overridden in subclasses. This means that the dispatch of such functions is virtual with regard to the dispatch receiver type, but static with regard to the extension receiver type
- **in Kotlin, there is a way to explain this sort of thing to the compiler. This is called declaration-site variance: we can annotate the type parameter T of Source to make sure that it is only returned (produced) from members of Source<T>, and never consumed. To do this we provide the out modifier**
- for maximum flexibility, use wildcard types on input parameters that represent producers or consumers
wildcard type argument `?`

### Git

- checkout to branch with dirty option
- fast import
- fast export
