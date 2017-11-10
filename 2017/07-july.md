# July

## 6

- поле динамических данных **slug**. Например замена /blog/post/name-of-post на определенный идентификатор
- middleware - `cookies`, `bodyParsers`

## 15

- `__unsafe_unretained` for < iOS4
- `__autoreleasing` - for variables that will be used by reference. E. g.`NSError* error; &error`
- **любая операция с блоком, кроме выполнения выполняется в куче**

## 19

- цвет у окна не выставляется в случае обычного init без параметров. Существует метод `_resizeWindowToFullScreenIfNecessary`. Если его переписать - то все становится хорошо
- relative paths for remotes are interpreted relative to our main remote, no to our repo’s root directory

## 20

- `yyyy` is another calendar system instead of `YYYY` in date formatter.

## 29

- **numericCast** will throw an error if you are using overflowing only for debugging 
