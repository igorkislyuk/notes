#  April
 
- from 10 ios there are property of all scroll view - refresh control

For hashed containers, such as Dictionary and Set, there’s a new type **AnyHashable** that can hold a value of any type conforming to the Swift Hashable protocol.

Interesting but for header and footer NO automatic height. You must specify in table properties or in delegate method, using UITableViewAutomaticDemensions brings you to zero.

To animate change height of table view cell use begin/end updates
class we can override but static is not.

## 13

- We have got `Mirror`. And we can receive children and self type, with naming of structure / class. We can reflect all properties of mirror. We can override `init` if we want to. So for convenient just use `Mirror(reflecting: self)`.
- Revert table view. Just use affineTransform for .pi

## 18

- `automaticallyAdjustScrollViewInsets` works only for first view(recursive).

## 20

- do not show keyboard in willAppear

## 21

- UIImage has got highlight image property
- Use system layout size fitting to determine size of things that using auto layout

## 22

1. triple = for compare within types in swift

## 25

- `NSUserDefaults` set nil is the same as using `removeObjectFor(key)`
- `synchronize()` called meanwhile. Better to force it call sometimes

## 29

- Using unicode in table view decrease performance