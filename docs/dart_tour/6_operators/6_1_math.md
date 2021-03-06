# Арифметические операторы

Dart поддерживает обычные арифметические операторы, как показано в следующей таблице

| Оператор | Описание                            |
| -------- | ----------------------------------- |
| +        | Сложение                            |
| -        | Вычитание                           |
| -expr    | Отрицательное число                 |
| *        | Умножение                           |
| /        | Деление                             |
| ~/       | Деление без остатка                 |
| %        | Остаток от деления                  |

Пример:

```dart
assert(2 + 3 == 5);
assert(2 - 3 == -1);
assert(2 * 3 == 6);
assert(5 / 2 == 2.5); // Результат число с плавающей точкой
assert(5 ~/ 2 == 2); // Результат целое число
assert(5 % 2 == 1); // Остаток от деления

assert('5/2 = ${5 ~/ 2} r ${5 % 2}' == '5/2 = 2 r 1');
```

Dart также поддерживает префиксные и постфиксные операторы увеличения и уменьшения

| Оператор | Описание                            |
| -------- | ----------------------------------- |
| ++var    | var = var + 1                       |
| var++    | var = var + 1                       |
| var--    | var = var – 1                       |
| --var    | var = var – 1                       |

Пример:

```dart
var a, b;

a = 0;
b = ++a; // Увеличит a, прежде чем b получит свое значение.
assert(a == b); // 1 == 1

a = 0;
b = a++; // Увеличит a, ПОСЛЕ того, как b получит свое значение.
assert(a != b); // 1 != 0

a = 0;
b = --a; // Уменьшит a, прежде чем b получит свое значение..
assert(a == b); // -1 == -1

a = 0;
b = a--; // Уменьшит a, ПОСЛЕ того, как b получит свое значение.
assert(a != b); // -1 != 0
```
