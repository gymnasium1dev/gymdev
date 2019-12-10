# Наборы

Набор (Sets) в Dart - это неупорядоченная коллекция уникальных элементов.

```dart
var halogens = {'fluorine', 'chlorine', 'bromine', 'iodine', 'astatine'};
```

>Примечание: Dart делает вывод, что элементы имеют тип `Set<String>`. Если вы попытаетесь добавить неправильный
тип значения в набор, анализатор или среда выполнения выдаст ошибку.

Чтобы создать пустой набор, используйте {} с предшествующим аргументом типа или присвойте {} переменной типа `Set`:

```dart
var names = <String>{};
// Set<String> names = {}; // это тоже сработает
// var names = {}; // !!создает карту(map), а не набор
```

Добавление элементов в существующий набор, происходит с помощью методов `add()` или `addAll()`:

```dart
var elements = <String>{};
elements.add('fluorine');
elements.addAll(halogens);
```

Используйте метод .length, чтобы получить количество предметов в наборе:

```dart
var elements = <String>{};
elements.add('fluorine');
elements.addAll(halogens);
assert(elements.length == 5);
```

Чтобы создать набор, который является константой времени компиляции, добавьте const перед литералом набора:

```dart
final constantSet = const {
  'fluorine',
  'chlorine',
  'bromine',
  'iodine',
  'astatine',
};
// constantSet.add('helium'); // добавление нового элемента вызовет ошибку
```

> Примечание: Начиная с Dart 2.3, наборы поддерживают операторы распространения (... и ...?) И наборы if и for, как это делают списки.
