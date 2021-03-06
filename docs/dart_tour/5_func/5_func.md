# Функции

Dart - это объектно-ориентированный язык, поэтому даже функции являются объектами(`Object`) и имеют тип `Function`.
Это означает, что функции могут быть присвоены переменным или переданы в качестве аргументов другим функциям. Вы также можете вызвать экземпляр класса Dart, как если бы это была функция.

Пример функции:

```dart
bool isNoble(int atomicNumber) {
  return _nobleGases[atomicNumber] != null;
}
```

В Dart рекомендуется явно указывать тип возвращаемого значения в функциях, но если вы это опустите, ошибкой это не будет:

```dart
isNoble(atomicNumber) {
  return _nobleGases[atomicNumber] != null;
}
```

Для функций, которые содержат только одно выражение, вы можете использовать сокращенный синтаксис:

```dart
bool isNoble(int atomicNumber) => _nobleGases[atomicNumber] != null;
```

Синтаксис `=> expr` является сокращением для `{return expr; }`. Обозначение `=>` иногда называют синтаксисом стрелки.

>Примечание. Между стрелкой (`=>`) и точкой с запятой (`;`) может появляться только выражение, но не утверждение. Например, вы не можете поместить туда оператор `if`, но вы можете использовать условное выражение.
