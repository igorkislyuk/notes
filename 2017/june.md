# June

## 1

- оценки никогда не делать нечетными, поскольку они не умещаются 
- отличие POST от GET в семантике запроса. Пост предназначен для передачи файлов, в то время как гет - нет
- для мобильных клиентов использование put & delete не рекомендуется

## 2

- Lhs
- `~=`

## 8

- слабая типизация - довольно мерзкая штука. Не хватает понимания, что тебе приходит

## 14

- Don't forget to use `...in` + `month or year`: In March, In 2003
- `on` + `date` (with the year or without it) or `day of the week`: On April 2, On March 3, 1999, On Saturday
- `at` + `clock time`, `midnight`, `noon`: At 3:30 p.m., At 4:01, At noon
- `in` + `season`: In the summer, In the winter
- `in` + `morning`, `afternoon`, `evening`: In the morning, In the evening
- `at` + `night`: At night

## 15

- концепция промежуточного по
- `middleware`

## 20 

- **Note that when you load a XIB into memory, all of its contents are loaded into memory, including any images. If you have a view you’re not using immediately, then you’re wasting precious memory. It’s worth noting that this won’t happen with storyboards, since a storyboard will only instantiate a view controller when it’s needed**
- Some objects are very slow to initialize — `NSDateFormatter` and `NSCalendar` are two examples
- color for pattern instead of image

## 21

- **http pipelining** - sending multiple requests without waiting for response. - order matters. requests should be idempotent.

## 23

- челночная дипломатия

## 26

- in case observeOn isn't explicitly specified, work will be performed on whichever thread/scheduler elements are generated.
- scheduler - can be any type from dispatch_queue till nsoperation queue
- serial is far better than concurrent one, due to optimisation
- RxTraits - **Single** (element or error), **Completable** (completed or error), **Maybe** (element, completed or error)
 
## 27
 
- bodyParser.urlencoded ({extended: VALUE})
- defaults to true, but using the default has been deprecated. 
- please research into the difference between qs and querystring and choose the appropriate setting.
- **Using qs - best option, querystring is not working**

## 28

- npm version system
- `~1.2` from `1.2.0` till `1.3.0`. It accepts minor changes
- `^0.2.0` - from `0.2.0` till `0.3.0`. It allows changes that do not modify the left-most non-zero digit