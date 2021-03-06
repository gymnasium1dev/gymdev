# List

Возможно, самая распространенная коллекция почти в каждом языке программирования - это массив или упорядоченная группа объектов.
В Dart массивы являются объектами List, поэтому их часто называют списками.

```dart
var list = [1, 2, 3];
```

> Dart делает вывод, что список имеет тип List<int>.
Если вы попытаетесь добавить нецелые объекты в этот список,
анализатор или среда выполнения выдаст ошибку.

Списки используют индексацию с нуля, где 0 - это индекс первого элемента,
а list.length - 1 - это индекс последнего элемента.
Вы можете получить длину списка и ссылаться на элементы списка так же, как в JavaScript:

```dart
var list = [1, 2, 3];
assert(list.length == 3);
assert(list[1] == 2);

list[1] = 1;
assert(list[1] == 1);
```

Чтобы создать список, который является константой времени компиляции, добавьте const перед литералом списка:

```dart
var constantList = const [1, 2, 3];
// constantList[1] = 1; // переопределение приведет к ошибке
```

В Dart 2.3 появился оператор распространения (`...`) и оператор распространения с нулевым значением
(`...?`), Которые обеспечивают краткий способ вставки нескольких элементов в коллекцию.

```dart
var list = [1, 2, 3];
var list2 = [0, ...list];
assert(list2.length == 4);
```

Если выражение справа от оператора распространения может быть `null`, вы можете избежать исключений, используя оператор распространения с `null` значением (...?):

```dart
var list;
var list2 = [0, ...?list];
assert(list2.length == 1);
```

В Dart 2.3 также была представлена `collection if` и `collection for`, которую можно использовать для построения коллекций с использованием условий (`if`) и повторения (`for`).

```dart
var nav = [
  'Home',
  'Furniture',
  'Plants',
  if (promoActive) 'Outlet'
];
```

Вот пример использования коллекции for для управления элементами списка перед их добавлением в другой список:

```dart
var listOfInts = [1, 2, 3];
var listOfStrings = [
  '#0',
  for (var i in listOfInts) '#$i'
];
assert(listOfStrings[1] == '#1');
```
