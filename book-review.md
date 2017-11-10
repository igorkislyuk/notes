# Book-review

### Swift 3 Functional Programming by Dr. Fatih Nayebi

>>> Not so bad for newbies. Mark - 5 / 10

- `stride(from:to:by)`
- tail recursion is final expression in recursion call
- memoization is wrapping mutable dictionary in function call
- compound types / named types
- tuple / constant / identifier pattern matching
- generic typealiases
- numeric types
- using generic types in extension
- `functor` is any structure that we can `map` over
- `applicative functor` is functor that we can `apply` over
- `monad` is any structure we can `flatMap` over
- `@noescape` means that argument will no longer lives that the call
- `semigroup` isset of elements with binary operation. 2 elements call create semigroup with associative operation
- `monoid` is a set with binary opearation. Property - associativity, identity of elements
- **Abstract Data Types**: tree / binary tree / list / lazy list.
- `@autoclosure` - auto wrapping argument in closure
- `@escaping` - closure will last longer that lifetime of the scope that it is declared in.
- `Lens` fucntional wrapper over property
- interface segregation
- dependency inversion

### iOS App Reverse Engeneering

>>> Very good book. Recommend. 8 / 10

- `hier` - filesystem on iOS / MacOS
- `rwx/r-x/r-x` = 755. User / group / other users
- distribution over debian packages `.deb` instead of `.ipa`
- `daemon` = plist + executable
- 2 users - mobile and root
- **Tools**: class-dump, Theos, Reveal App, IDA, Logos
- For Hooking used `MSHookMessageEx` is for ObjC. `MSHookFunction` is for C / C++

### objc. Advanced Swift

>>> Very good book, event for intermediate programmers. Mark - 9 / 10

This book full of detail explanation how generics / protocol types works, what are existential containers. Furthemore there are only one chapter for Swift introducing. I suggest that you should read it. 

### Ry’s Objective-C Tutorial

>>> Very good book for ObjC lovers. Recommend for newbies 6 / 10

- **Static Functions**. By default, all functions have a global scope. This means that as soon as you define a function in one file, it’s immediately available everywhere else. The static specifier lets you limit the function’s scope to the current file, which is useful for creating “private” functions and avoiding naming conflicts. Variables declared inside of a function (also called automatic local variables) are reset each time the function is called. This is an intuitive default behavior, as the function behaves consistently regardless of how many times you call it. However, when you use the static modifier on a local variable, the function “remembers” its value across invocations.
- the **`unsafe_unretained`** Attribute. Properties with the `unsafe_unretained` attribute behave similar to weak properties, but they don’t automatically set their value to nil if the referenced object is destroyed. The only reason you should need to use `unsafe_unretained` is to make your class compatible with code that doesn’t support the weak property
- the **assign** Attribute. The assign attribute doesn’t perform any kind of memory-management call when assigning a new value to the property. This is the default behavior for primitive data types, and it used to be a way to implement weak references before iOS 5. Like retain, you shouldn’t ever need to explicitly use this in modern applications


### Pro Objective-C 

>>> Awesome book. 10/10 for all iOS programmers. 

### Beginning objc 

>>> Cool book for newbies. 6/10 for intermediate level programmers