# August

## 10

- better reload whole table than single row / section using table director
- carthage can be useful for dynamic libraries where only static for objc
- optional enum for switch case

## 13

- **trait** also has the actual method bodies. In other words, a trait adds code to an interface. This is the new thing that Swift 2.0 lets us do today with protocol extensions.
- **mixin** is like a trait but it also has state. We can’t really do this yet with Swift 2.0 as you’re not allowed to add stored properties to protocols.

## Unsafe Swift

- withUnsafeMemory

- **UnsafePointer<T>, UnsafeRowPointer**
- **UnsafeMutablePointer<T>, UnsafeMutableRowPointer**

- withUnsafeBytes

- same 4 pointer types, except there are operation with buffer instead of single pointer
- **implicit conversion from variable to pointer using inout syntax**

- 2 rules working with pointer types:
	1. never escape the pointer you get in a withUnsafe- function, and
	2. never, ever get the pointer to a variable through implicit conversion

## 14

- for sequence generation use stride or sequence 

## 19

- compare `NaN` with any other number, including `NaN` results false
- to test use `isNaN`

## 21

- android setting locale same as iOS. But timezone init from String

## 23

- in Metal, the default coordinate system is the normalized coordinate system, which means that by default you are looking at a 2x2x1 cube centered at (0, 0, 0.5)
- you can click the little menu that appears when you click in the filled circle to navigate to the destination object

## 29

- `NSLock` faster than `@synchronise`

## 30

- from a technical standpoint, a thread is a combination of the kernel-level and application-level data structures needed to manage the execution of code