# Цикл For

Вы можете выполнять итерации со стандартным циклом `for`. Например:

```dart
var message = StringBuffer('Dart is fun');
for (var i = 0; i < 5; i++) {
  message.write('!');
}
```

Замыкания внутри циклов `for` в Dart фиксируют значение индекса, избегая распространенной ошибки, обнаруженной в JavaScript.

```dart
var callbacks = [];
for (var i = 0; i < 2; i++) {
  callbacks.add(() => print(i));
}
callbacks.forEach((c) => c());
```

Если объект, который вы используете, является Iterable, вы можете использовать метод `forEach()`. Использование `forEach()` является хорошим вариантом, если вам не нужно знать текущий счетчик итераций:

```dart
candidates.forEach((candidate) => candidate.interview());
```

Итерируемые объекты, такие как `List` и `Set`, также поддерживают форму итерации `for-in`:

```dart
var collection = [0, 1, 2];
for (var x in collection) {
  print(x); // 0 1 2
}
```
