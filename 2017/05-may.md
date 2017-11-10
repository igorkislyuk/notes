# May

## 03

- all static variables are lazy be default

## 05

- 0.16 ms for cellForRow. Default system calls ~0.03ms
- Dequeue with indexPath always return cell. Simple dequeue could return nil

## 07

- addSubview is very rich operation. [TeamLead experience]

## 08

- API is very important part & dynamic type system is very hand to maintain
- module in node.js can return one instance
- custom navbar - simple view SIMULATING navigation bar underscore
- `#fileLiteral`

## 10

- forEach принимает closure, которую нужно вызывать каждый раз и которая может кидать exception. Такой вызов не самый дешёвый. Оптимизации вроде loop-unroll невозможно или крайне сложно применять в таких случаях.

## 11

- First function parameter is err, then data
- Error event always should be handled
- `parent`(property from viewController) is initialized between init and child `viewDidLoad`
- gcd 64 max threads. + main + background

## 23

- `NS_INLINE`
- разница между мютексом и семафором состоит в том, что блокировки (мютексы) могут сниматься только потоками, которые ими владеют, тогда как изменять значение семафора может любой поток, имеющий к нему доступ. Поэтому придется следить за тем, как работает с семафорами поток, что потребует дополнительных усилий при программировании.

## 30

- `If it isn’t a clear “yes”, then it’s a clear “no”`
- хорошей считается та оценка, которая обеспечивает достаточно ясное представления реального состояния проекта и позволяет руководителю проекта принимать хорошие решения относительно того, как управлять проектом для достижения целей.
- пагинация на лимит оффсет
- пагинация на страницах
- пагинация на курсорах
- разница между библиотекой и фреймворком

## 31

- заголовки до первой записи в ответ, т. е. до `res.write` / `res.end`

