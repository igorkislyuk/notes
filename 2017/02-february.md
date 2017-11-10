#  February
 
##  01

- it’s a good idea to get into the habit of setting a name for every node you create in SpriteKit because the name can be useful during debugging
- it’s good to use SpriteKit and SceneKit for animations in your apple watch. Restrictions are minimal. Use effects and action in SK
- it is possible to include SceneKit in notification to display animated stuff like particles, animated paths, and message
- you can transfer **userInfo**, **context** and **file** with WatchConnectivity
- userInfo is guaranteed
- WatchSession in AppleWatch is always supported

- In watchOS, the counterpart iPhone app is considered active, or reachable, when a matching session is enabled and the iPhone is within range of communication. The iPhone app doesn’t have to be in the foreground to be reachable. 
- In iOS, the Watch app is considered reachable when the paired Watch is in range and the Watch app is running in the foreground. If the Watch app isn’t running or is in the background, then it’s not reachable. 

## 2

- Create advanced complication for time-travel in Apple Watch

ClockKit provides a simple animation you can use to emphasise certain transitions when traveling through time. You can choose from three animation behaviours: 

1. None is the default value of no animation, which is your app’s current behaviour. 
2. Always animates the change every time. 
3. Grouped lets you use animation groups to specify which transitions to animate. Here, timeline entries are divided into groups, identified by a string. Animations will only occur when the displayed timeline entry changes between groups. 

The system manages this by allocating time budgets to each complication. Your complication can take time to update as long as it stays within its budget. Once time exceeds the budget, the system won’t let the complication update its data at all until the system replenishes your complication’s budget 

- Use CLKComplicationServer to invalidate / update data
- When the time comes for an update, the system will call either requestedUpdateDidBegin() or requestedUpdateBudgetExhausted() on the CLKComplicationDataSource to let you know that the update is beginning 
- iOS 9 introduced a new type of push notification — designed especially for complications 

Ways to update complication - from watch app, schedule, iPhone, own server (PushKit), background task.

Handoff functionality depends on few things: 

- An iCloud Account: You must be logged into the same iCloud account for each device on you wish to use Handoff.
- Bluetooth LE 4.0: Handoff broadcasts activities via Bluetooth LE signals, so both the broadcasting and receiving devices must have Bluetooth LE 4.0 support.
- iCloud paired: devices should have been already paired through iCloud.  
For Handoff to work, both the sending and receiving apps must be signed by the same Team ID. Handoff is based on the concept of user activities: stand-alone units of information that you can hand off without any dependencies on other information. In iOS, Handoff uses NSUserActivity objects to package information to transfer. When passing instances of NSURL, don’t pass local file URLs, as the receiver won’t be able to translate and map the URL properly. Instead, send a relative path and reconstruct the URL manually on the receiving side 

- `updateUserActivity` / `restoreUserActivity`
- You can broadcast only one activity at a time

## 3

- Accelerometer measures all axes in G’s 
- Altimeter - height according to sea level
- Gyroscope & Magnetometer
- We can use variable to unique bundle id for watch / iPhone / watch extension. Example in plist: `${W3T_BUNDLE_PREFIX}.$(PRODUCT_NAME)`

You can find in WK Book:

- How to ask for permissions to save and access HealthKit data from the Watch 
- How to create a workout session and get sensor and other health data while the session is running
- How to save a workout to the HealthKit data store and add your own metadata 

## 4

As in iOS, you need to ask for user authorisation to access a user’s location in the Watch app. You can ask for two types of authorisation: 

- When in use, where the location is only accessible while the app is in the foreground. 
- Always, where the location is accessible at any time, as long as the device is running. 

If you’re familiar with Core Location on iOS, you know it’s possible to subscribe to ongoing location updates from Core Location. In watchOS, you can only ask for a one-time location update via an API.

If the iPhone isn’t reachable and the Watch has to get a location fix on its own, the best accuracy level you can get from `CLLocationManager` is `kCLLocationAccuracyHundredMeters`.

When the Watch app isn’t running, Watch Connectivity caches any updates and will deliver the most recent one on the next launch.

Since iOS 9, you also have to set the value of the allowsBackgroundLocationUpdates property on your CLLocationManager instance to true. You must set this property for each CLLocationManager instance 

`allowDeferredLocationUpdatesUntilTraveled(_:timeout:)` is an old API that’s been around for a long time, but it probably hasn’t gotten as much attention as it deserves.

There are a number of things to keep in mind about `allowDeferredLocationUpdates(untilTraveled:timeout:)`.

The location manager allows deferred updates only when GPS hardware is available on the device and the desired accuracy is set to `kCLLocationAccuracyBest` or `kCLLocationAccuracyBestForNavigation`. Otherwise, you’ll get a `kCLErrorDeferredFailed` error. If you set the accuracy to an unsupported value, you’ll get a `kCLErrorDeferredAccuracyTooLow` error.

You must set the distance. Filter property of the location manager to `kCLDistanceFilterNone` or you’ll get a `kCLErrorDeferredDistanceFiltered` error.

Call `allowDeferredLocationUpdates(untilTraveled:timeout:)` after you’ve received your first batch of location updates. You call this once you’re happy with your current updates and want to defer future updates until the distance or time criteria are met.

Don’t call `allowDeferredLocationUpdates(untilTraveled:timeout:)` more often than necessary. Each subsequent call cancels the previous deferral. You should keep track of whether updates are currently deferred and call it again only when you want to change the deferral criteria.

The system delivers deferred updates only when it enters a low-power state. Deferred updates don’t occur during debugging, because Xcode prevents your app from sleeping and so prevents the system from entering that low-power state 


Alerts in watchOS come in three styles: 

- alert
- sideBySideButtonsAlert
- actionSheet 

 
You can implement the WKInterfaceController `pickerDidSettle(_:)` method that makes Watch pickers behave like iPhone pickers.

The Interactions section includes two recommendations to make your haptic feedback more effective:
 - Provide visual cues to correspond with haptics…[This] creates a deeper connection between the user’s action and the result.
 - Initiate the playback of haptics at the appropriate time…as the first step in performing the corresponding task, rather than as the last step.

### Internationalization
**Internationalization is the process of making strings from storyboard or code externally editable. It also involves using formatting classes for things like dates and numbers. It’s up to you, the app developer, to perform internationalization**

### Localization
**Localization is the process of translating those externalized strings into a given language. You’ll usually hire a localization company to do this work** 
- xliff (XML Localization Interchange File Format) 
- Apple has introduced new `Unit` classes to Foundation; while you didn’t need them for this app, they might be handy for your future projects. They work across languages and locales automatically, so if you can use them, you’ll save a ton of boilerplate code.

## 5

- **Request behaviours** is pattern that performs different actions according to injected extended protocol

## 8

**NSProcessInfoPowerStateDidChangeNotification** - for managing low power mode

## 9

**UIView.transition** - replace two states of view, using snapshot mechanism

## 10

- `UIView.removeFromSuperView()` will release it from memory and calling addSubview - will remove from old parent view

- debugger is simply attached to process, and each instruction from child process (except `SIGKILL`) send to parent, something like that
- **Статическая переменная**, как и глобальная переменная, объявляется за пределами какой-либо функции - но при этом она доступна только в коде того файла, в котором была объявлена
- Если переменной не было присвоено начальное значение, она автоматически инициализируется нулем. 

### Nullability

- `_Null_unspecified`, which bridges to a Swift implicitly unwrapped optional. This is the default
- `_Nonnull`, the value won’t be nil it bridges to a regular reference
- `_Nullable` the value can be nil, it bridges to an optional
- `_Null_resettable` the value can never be nil, when read but you can set it to know to reset it. This is only apply property.

## 16

- функция `sizeof()` возвращает значение типа `size_t`, для вывода которого следует использовать относительно редкий заполнитель `%zu`

## 17

`__auto_type` is very convenient thing for blocks

## 19

- Когда отправляется сообщение release у объекта в пуле? При сбросе текущего пула autorelease
- `NSМutаblеАrrау` содержит два метода: 
	- `(NSUInteger)indexOfObject:(id)anObject`
	- `(NSUInteger)indexOfObjectIdenticalTo:(id)anObject`
	
	Первый метод перебирает коллекцию, проверяя для каждого объекта условие `isEqual: anObject`. Второй метод перебирает коллекцию с проверкой условия `== anObject`. 

Директива `#import` гарантирует, что препроцессор включит файл только один раз. Директива `#include` позволяет многократно включить один файл. Программисты С чаще используют `#include`, а программисты Objective-C предпочитают `#import`.

Имя импортируемого файла может быть заключено в кавычки или угловые скобки.

*Кавычки означают, что заголовочный файл находится в каталоге проекта*. 

*Угловые скобки означают, что заголовочный файл находится в одном из стандартных каталогов, известных препроцессору.*

## 20

- атомик инструкция выполняет сохранение в отдельный файл
- `__unused` для сообщения компилятору
- Фактические определения IBOutlet и IBAction тривиальны: 
	- `#define IBAction void`
	- `#define IBOutlet`
- It’s better to expand path, rather that maintaining tilda. Or use fileURL’s instead of path, and later just ask for path
- Любопытный факт о компиляторе Objective-C: при компилировании приложения для iOS или 64-разрядной платформы Мас OS Х объявлять переменные экземпляров не нужно. Вызовов `@рrореrtу/@sуnthеsizе` достаточно для того, чтобы память для данных была зарезервирована 
- `NSZone` и зонирование памяти вообще - устаревшие, рудиментарные возможности программирования `Сосоа`, поэтому здесь они подробно не рассматриваются. Впрочем, метод `copyWithZone:` еще находит практическое применение и не считается полностью вытесненным 
- по умолчанию переменные, скопированные блоком, в блоке изменяться не могут, то есть фактически превращаются в константы. Например, переменные указателей на объекты сохраняют постоянное значение в пределах блока. (Хотя вы можете отправить объекту сообщение, изменяющее его содержимое, сам указатель изменить нельзя.) 

## 21

**NSDateDetector** поиск вхождений даты и ссылок в тексте

Функция malloc() выделяет буфер в куче, поэтому вы должны проследить за тем, чтобы он был освобожден после завершения работы. А разве не удобнее было бы объявить буфер как часть кадра (в стеке), чтобы он автоматически освобождался после завершения выполнения функции `float *values = float[3]`

- `UISearchController` hold new controller and search bar
- `UISearchContainerViewController` used for wrapped out search controller for direct present of it