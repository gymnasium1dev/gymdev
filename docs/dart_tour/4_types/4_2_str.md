# String

Строка Dart представляет собой последовательность кодовых единиц UTF-16.
Вы можете использовать одинарные или двойные кавычки для создания строки:

```dart
var s1 = 'Single quotes work well for string literals.';
var s2 = "Double quotes work just as well.";
var s3 = 'It\'s easy to escape the string delimiter.';
var s4 = "It's even easier to use the other delimiter.";
```

Вы можете поместить значение выражения в строку, используя `${expression}`.
Если выражение является идентификатором, вы можете пропустить `{}`.
Чтобы получить строку, соответствующую объекту, Dart вызывает метод объекта toString ().

```dart
var s = 'string interpolation';

assert('Dart has $s, which is very handy.' ==
    'Dart has string interpolation, ' +
        'which is very handy.');
assert('That deserves all caps. ' +
        '${s.toUpperCase()} is very handy!' ==
    'That deserves all caps. ' +
        'STRING INTERPOLATION is very handy!');
```

> Примечание: Оператор == проверяет, эквивалентны ли два объекта.
Две строки эквивалентны, если они содержат одинаковую последовательность единиц кода.

Вы можете объединять строки, отступами или используя оператор `+`:

```dart
var s1 = 'String '
    'concatenation'
    " works even over line breaks.";
assert(s1 ==
    'String concatenation works even over '
        'line breaks.');

var s2 = 'The + operator ' + 'works, as well.';
assert(s2 == 'The + operator works, as well.');
```

Другой способ создания многострочной строки:
Использование трех `'` или `"""`:

```dart
var s1 = '''
You can create
multi-line strings like this one.
''';

var s2 = """This is also a
multi-line string.""";
```

Вы можете создать «raw» строку, добавив к ней префикс r:

```dart
var s = r'In a raw string, not even \n gets special treatment.';
```
