# Функции как объекты

Вы можете передать функцию в качестве параметра другой функции. Например:

```dart
void printElement(int element) {
  print(element);
}

var list = [1, 2, 3];

list.forEach(printElement);
```

Вы также можете назначить функцию переменной, например:

```dart
var loudify = (msg) => '!!! ${msg.toUpperCase()} !!!';
assert(loudify('hello') == '!!! HELLO !!!');
```
