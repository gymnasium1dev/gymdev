# Значение по умолчанию

Неинициализированные переменные в Dart равны `null`. **Даже переменные с числовым типом данных**, потому что числа как и все в Dart является объектом.

```dart
int lineCount;
assert(lineCount == null);
```

> Примечание: Вызов `assert()` игнорируется в production коде. Во время разработки `assert()` выдает исключение если условие не является истинным.
> 