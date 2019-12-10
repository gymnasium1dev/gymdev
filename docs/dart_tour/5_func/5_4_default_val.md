# Значения параметров по-умолчанию

Ваша функция может использовать `=` для определения значений по умолчанию для именованных и позиционных параметров. Значения по умолчанию должны быть константами времени компиляции.
Если значение по-умолчанию не указано, значением по умолчанию является `null`.

```dart
void enableFlags({bool bold = false, bool hidden = false}) {...}
// bold будет true; hidden - false.
enableFlags(bold: true);
```

> Примечание об устаревании: Старый код может использовать двоеточие (`:`) вместо `=` для установки значений по-умолчанию именованных параметров. Причина в том, что изначально только `:` поддерживали именованные параметры. Это уже устарело, поэтому мы рекомендуем использовать `=`, чтобы указать значения по-умолчанию.

В следующем примере показано, как установить значения по-умолчанию для позиционных параметров:

```dart
String say(String from, String msg,
    [String device = 'carrier pigeon', String mood]) {
  var result = '$from says $msg';
  if (device != null) {
    result = '$result with a $device';
  }
  if (mood != null) {
    result = '$result (in a $mood mood)';
  }
  return result;
}

assert(say('Bob', 'Howdy') ==
    'Bob says Howdy with a carrier pigeon');
```

Вы также можете передать списки или карты в качестве значений по умолчанию. В следующем примере определяется функция doStuff (), которая задает список по-умолчанию для параметра list и карту по-умолчанию для параметра gifts.

```dart
void doStuff(
    {List<int> list = const [1, 2, 3],
    Map<String, String> gifts = const {
      'first': 'paper',
      'second': 'cotton',
      'third': 'leather'
    }}) {
  print('list:  $list');
  print('gifts: $gifts');
}
```