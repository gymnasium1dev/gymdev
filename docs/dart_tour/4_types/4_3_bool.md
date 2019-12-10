# bool

Для представления логических значений Dart имеет тип с именем `bool`. Только два объекта имеют тип `bool`: логические литералы `true` и `false`,
которые являются константами времени компиляции.

Безопасность типов Dart означает, что вы не можете использовать
код вроде `if (nonbooleanValue)` или `assert (nonbooleanValue)`.
Лучше явно проверять значения, например:

```dart
// проверка на пустую строку
var fullName = '';
assert(fullName.isEmpty);

// Проверка на ноль
var hitPoints = 0;
assert(hitPoints <= 0);

// Проверка null.
var unicorn;
assert(unicorn == null);

// Проверка NaN.
var iMeantToDoThis = 0 / 0;
assert(iMeantToDoThis.isNaN);
```