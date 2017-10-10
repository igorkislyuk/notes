# Ry’s Objective-C Tutorial

>>> Very good book for ObjC lovers. Recommend for newbies 6 / 10

Good reminders for 3 things:

- **Static Functions**. By default, all functions have a global scope. This means that as soon as you define a function in one file, it’s immediately available everywhere else. The static specifier lets you limit the function’s scope to the current file, which is useful for creating “private” functions and avoiding naming conflicts. Variables declared inside of a function (also called automatic local variables) are reset each time the function is called. This is an intuitive default behavior, as the function behaves consistently regardless of how many times you call it. However, when you use the static modifier on a local variable, the function “remembers” its value across invocations.
- the **`unsafe_unretained`** Attribute. Properties with the `unsafe_unretained` attribute behave similar to weak properties, but they don’t automatically set their value to nil if the referenced object is destroyed. The only reason you should need to use `unsafe_unretained` is to make your class compatible with code that doesn’t support the weak property
- the **assign** Attribute. The assign attribute doesn’t perform any kind of memory-management call when assigning a new value to the property. This is the default behavior for primitive data types, and it used to be a way to implement weak references before iOS 5. Like retain, you shouldn’t ever need to explicitly use this in modern applications
