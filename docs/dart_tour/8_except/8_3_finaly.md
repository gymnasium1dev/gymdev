# Finally

Чтобы убедиться, что какой-то код выполняется независимо от того, было ли выброшено исключение, используйте предложение finally. 

```dart
try {
  breedMoreLlamas();
} finally {
  // выполнится в любом случае
  cleanLlamaStalls();
}
```

Предложение finally запускается после всех catch и повзоляет например восстановится после обработки исключений:

```dart
try {
  breedMoreLlamas();
} catch (e) {
  print('Error: $e');
} finally {
  cleanLlamaStalls(); // очищаем состояние
}
```
