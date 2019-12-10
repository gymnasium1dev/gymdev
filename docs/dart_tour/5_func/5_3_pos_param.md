# Необязательные позиционные параметры

Обертывание набора параметров функции в [] помечает их как необязательные позиционные параметры:

```dart
String say(String from, String msg, [String device]) {
  var result = '$from says $msg';
  if (device != null) {
    result = '$result with a $device';
  }
  return result;
}
```

Вот пример вызова этой функции без необязательного параметра:

```dart
assert(say('Bob', 'Howdy') == 'Bob says Howdy');
```

И вот пример вызова этой функции с третьим параметром:

```dart
assert(say('Bob', 'Howdy', 'smoke signal') ==
    'Bob says Howdy with a smoke signal');
```
