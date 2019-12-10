# Switch case

Оператор `Switch` в Dart сравнивают целочисленные, строковые или константы времени компиляции, используя `==`. Все сравниваемые объекты должны быть экземплярами одного и того же класса (а не каких-либо его подтипов), и класс не должен переопределять `==`.

Каждый `case` должне заканчиватся `break, continue, throw или return`

```dart
var command = 'OPEN';
switch (command) {
  case 'CLOSED':
    executeClosed();
    break;
  case 'PENDING':
    executePending();
    break;
  case 'APPROVED':
    executeApproved();
    break;
  case 'DENIED':
    executeDenied();
    break;
  case 'OPEN':
    executeOpen();
    break;
  default:
    executeUnknown();
}
```

В следующем примере в операторе `case` пропущен оператор `break`, что приводит к ошибке:

```dart
var command = 'OPEN';
switch (command) {
  case 'OPEN':
    executeOpen();
    // ERROR: Пропущен break

  case 'CLOSED':
    executeClosed();
    break;
}
```

Тем не менее, Dart поддерживает пустые предложения case:

```dart
var command = 'CLOSED';
switch (command) {
  case 'CLOSED':
  case 'NOW_CLOSED':
    executeNowClosed();
    break;
}
```
