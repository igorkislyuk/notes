# June

## 1

- оценки никогда не делать нечетными, поскольку они не умещаются 
- отличие POST от GET в семантике запроса. Пост предназначен для передачи файлов, в то время как гет - нет
- для мобильных клиентов использование put & delete не рекомендуется
## 15

- концепция промежуточного по из node.js `middleware`

## 20 

- **Note that when you load a XIB into memory, all of its contents are loaded into memory, including any images. If you have a view you’re not using immediately, then you’re wasting precious memory. It’s worth noting that this won’t happen with storyboards, since a storyboard will only instantiate a view controller when it’s needed**
- Some objects are very slow to initialize — `NSDateFormatter` and `NSCalendar` are two examples

## 21

- **http pipelining** - sending multiple requests without waiting for response. Order matters. requests should be idempotent.

## 26

- in case observeOn isn't explicitly specified, work will be performed on whichever thread/scheduler elements are generated.
- scheduler - can be any type from `dispatch_queue` till `NSOperation` queue
- serial is far better than concurrent one, due to optimisation
- RxTraits
	- **Single** (element or error)
	- **Completable** (completed or error)
	- **Maybe** (element, completed or error)
 
## 27
 
- bodyParser.urlencoded ({extended: VALUE}) defaults to true, but using the default has been deprecated. 
- please research into the difference between qs and querystring and choose the appropriate setting.
- **Using qs - best option, querystring is not working**

## 28

- npm version system
- `~1.2` from `1.2.0` till `1.3.0`. It accepts minor changes
- `^0.2.0` - from `0.2.0` till `0.3.0`. It allows changes that do not modify the left-most non-zero digit