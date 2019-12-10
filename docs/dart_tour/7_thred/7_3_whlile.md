# While и do-while

Цикл `while` перед исполнением тела цикла, проверяет условие

```dart
while (!isDone()) {
  doSomething();
}
```

Цикл `do while` сначала исполняет тело цикла, а затем проверяет условие

```dart
do {
  printLine();
} while (!atEndOfPage());
```