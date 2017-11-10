# October

## 01 

Observables must issue notifications to observers serially (not in parallel). They may issue these notifications from different threads, but there must be a formal happens-before relationship between the notifications.

A modular header is a header that is included in the module map.

## 02

- Favor map but don’t force it, use a for loop when it makes sense. The purpose of higher-order functions is to make code more readable. An obfuscated use of reduce when a simple for loop would be clearer defeats this purpose.
- Favor immutable variables, default to let unless you know you need mutation. But use mutation when it makes the code clearer or more efficient. Again, don’t force it, a mutating method on structs is often more idiomatic and efficient than returning a brand new struct.
 About hashable techique using XOR. One limitation of this technique is that XOR is symmetric (i.e. `a ^ b == b ^ a`), which, depending on the characteristics of the data being hashed, could make collisions more likely than necessary. You can add a bitwise rotation to the mix to avoid this.

This also means that you can use the self keyword without issues in non-escaping closures because the closure is invoked before the function returns. There is no need to use a weak reference to self in the closure. This is a nice benefit you get for free.

- Sequence
- Collection 
- Bidirectional Collection
- RandomAccessCollection
- RangeReplaceableCollection
- MutableCollection

## 05

- You can set attributes in interface builder and just change text to matching
- Elements are Comparable Range
- Elements are Strideable CountableRange (with integer steps) 
- ClosedRange 
- CountableClosedRange 

## 06

- isKnownUniquelyReferenced 
- capture lists can also be used to initialize new variables 
- `inout` is **pass-by-value-and-copy-back**, not pass-by-reference 

## 08

So today, Unicode is a variable-width format, and it’s variable in two different senses: in the combining of code units into code points, and in the combining of code points into characters 

A “code point” in Unicode is a single value in the Unicode code space with a possible value from 0 to 0x10FFFF. Only about 128,000 of the 1.1 million code points possible are currently in use, so there’s a lot of room for more emoji 

## 10

Swift compiler can make use of an optimization called generic specialization .

Since this is a pretty big limitation, the compiler has a flag to enable whole module optimization. In this mode, all files in the current module are optimized together as if they were one file.

Whole module optimization enables other important optimizations. For example, the optimizer will recognize when an internal class has no subclasses in the entire module. Since the internal modifier makes sure the class isn’t visible outside the module, this means the compiler can replace dynamic dispatch with static dispatch for all methods of this class.

`// About comparing amount of memory for generic function and function with protocol type.`

Where does the size difference of 8 bytes versus 40 bytes come from? Because f takes a generic parameter, the integer 5 is passed straight to the function without any kind of boxing. This is reflected in its size of 8 bytes, which is the size of Int on a 64-bit system. For g, the integer is wrapped in an existential container. For regular protocols, an opaque existential container is used. Opaque existential containers contain a buffer (the size of three pointers, or 24 bytes) for the value; some metadata (one pointer, 8 bytes); and a number of witness tables (zero or more pointers, 8 bytes each). If the value doesn’t fit into the buffer, it’s stored on the heap, and the buffer contains a reference to the storage location. The metadata contains information about the type (for example, so that it can be used with a conditional cast) 

For a class-only protocol, there’s a special existential container called a class existential container, which only has the size of a single pointer because it doesn’t need to store the value (only a reference) or the metadata (which is already in the class) 

Existential containers add a level of indirection and therefore generally cause a performance decrease over generic parameters. In addition to the possibly slower method dispatch, the existential container also acts as a barrier that prevents many compiler optimizations. For the most part, worrying about this overhead is premature optimization. However, if you need maximum performance in a tight loop, it’ll be more efficient to use a generic parameter rather than a parameter that has a protocol type. This way, you can avoid the implicit protocol box 

The **assign attribute** doesn’t perform any kind of memory-management call when assigning a new value to the property. This is the default behavior for primitive data types, and it used to be a way to implement weak references before iOS 5. Like retain, you shouldn’t ever need to explicitly use this in modern applications.

## 13

Многопоточность не предлагает настоящей параллельной обработки данных. Одновременно работает только один процесс, но время переключения между процессами сведено до наносекунд. 

## 19

- **@private:** The instance variable is only accessible within the class that declares it and other instances of this class type
- **@protected:** The instance variable is accessible within the class that declares it and the instance methods of any of its subclasses. This is the default scope if a protection level is not specified for an instance variable
- **@public:** The instance variable is accessible from everywhere
- **@package:** The instance variable is accessible from any other class instance or function, but outside the package, it is treated as private. This scope can be useful for libraries or framework classes 

Through use of the **@synthesize** keyword, the compiler can autogenerate property definitions. A property is synthesized in the corresponding class implementation section.

Fast forwarding: Classes that descend from NSObject can implement fast forwarding by overriding the NSObject `forwardingTargetForSelector:` method to forward the method to another object. This technique makes it appear like the implementations of your object and the forwarding object are combined. This simulates the behavior of multiple inheritance of class implementations. It works well if you have a target class that defines all the possible messages that your object can consume.

You can’t cast directly between `id` and `(void *)` types. **ARC only manages Objective-C objects and blocks**, thus the compiler needs to know the types of the objects it is processing. Because a pointer to `void` `(void *)` is a generic pointer type that can be converted to any other pointer type (even those that are not Objective-C pointer types), this restriction is necessary. This scenario is common when casting between Foundation Framework objects and Core Foundation types (Core Foundation is an Apple software library that provides C-language APIs). A set of APIs is provided for ownership transfer of variables between ARC and non-ARC environments.

- Header file name between double quotes ("HeaderFileName"). The compiler first searches for the file in the same directory that includes the file containing the directive. If the file is not found there, the compiler searches for the file in the default directories, where it is configured to look for the system-standard header files

- Header file name between angle brackets (<HeaderFileName>). The compiler searches for the file in the default directories, where it is configured to look for the standard header file   - The import directive (`#import`) also performs header file inclusion. Like the `#include` directive, the included header file is enclosed in either double quotes or angle brackets. This directive differs from `#include` in that it ensures a header file is only included once in a source file, thereby preventing recursive includes 
### ARC

ARC bridged casts enable the use of toll-free bridged types when using ARC. These casting operations are prefaced with the special annotations `__bridge`, `__bridge_retained`, and `__bridge_transfer`. 

- The `__bridge` annotation casts an object from a Core Foundation data type to a Foundation object (or vice-versa) without transfer of ownership. In other words, if you dynamically create a Foundation Framework object, and then cast it to a Core Foundation type (via toll-free bridging), the `__bridge` annotation informs the compiler that the object’s life cycle is still managed by ARC. Conversely, if you create a Core Foundation data type and then cast it to a Foundation Framework object, the `__bridge` annotation informs the compiler that the object’s life cycle must still be managed programmatically (and is not managed by ARC). Note that this annotation removes the compiler error but doesn’t transfer ownership; thus, care is required when using it to avoid memory leaks or dangling pointers
- The `__bridge_retained` annotation is used to cast a Foundation Framework object to a Core Foundation data type and transfer ownership from the ARC system. You are then responsible for programmatically managing the lifetime of the bridged data type
- The `__bridge_transfer` annotation is used to cast a Core Foundation data type to a Foundation object and also transfer ownership of the object to the ARC system. ARC will then programmatically manage the lifetime of the bridged object. The syntax for using a bridged cast annotation in a cast operation is `(annotation castType)variableName` 
## 20

`NSPointerArray` is a mutable collection similar to `NSMutableArray` that can hold arbitrary pointers and NULL values. It also allows you to manage the collection by setting the count for the array, such that if the number of elements in the collection is less than the count, then the collection is padded with NULL values; or if the number of elements in the collection is greater than the count, then the elements in the collection above the count value are removed.

## 22

- Roman in English это прямой шрифт

## 23

- Lock properties in IB