# Функция main()

Каждое приложение должно иметь функцию `main()`, которая служит точкой входа в приложение. Функция `main()` возвращает `void` и имеет необязательный параметр `List<String>` для аргументов.

```dart
void main() {
  querySelector('#sample_text_id')
    ..text = 'Click me!'
    ..onClick.listen(reverseText);
}
```

> Примечание. Синтаксис .. в предыдущем коде называется каскадом. С помощью каскадов вы можете выполнять несколько операций над элементами одного объекта.

Вот пример функции `main()` для приложения командной строки, которое принимает аргументы:

```dart
void main(List<String> arguments) {
  print(arguments);

  assert(arguments.length == 2);
  assert(int.parse(arguments[0]) == 1);
  assert(arguments[1] == 'test');
}
```
