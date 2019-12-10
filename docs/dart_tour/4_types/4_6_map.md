# Map

...словари
...карты

В общем, карта - это объект, который связывает ключи и значения. И ключи, и значения могут быть объектами любого типа. Каждый ключ встречается только один раз, но вы можете использовать одно и то же значение несколько раз.

```dart
var gifts = {
  // Key:    Value
  'first': 'partridge',
  'second': 'turtledoves',
  'fifth': 'golden rings'
};

var nobleGases = {
  2: 'helium',
  10: 'neon',
  18: 'argon',
};
```

> Примичание: Dart делает вывод, что gifts имеет тип Map<String, String>,
а nobleGases Map<int, String>. Если вы попытаетесь добавить значения другого типа,
это приведет к ошибке.

Вы можете создать те же объекты, используя конструктор Map:

```dart
var gifts = Map();
gifts['first'] = 'partridge';
gifts['second'] = 'turtledoves';
gifts['fifth'] = 'golden rings';

var nobleGases = Map();
nobleGases[2] = 'helium';
nobleGases[10] = 'neon';
nobleGases[18] = 'argon';
```

>Примечание: Возможно вы ожидаете увидеть `new Map()` вместо `Map()`, но начиная
с Dart2 ключевое слово `new` стало **не обязательным**.

Добавьте новую пару ключ-значение в существующую карту можно так же, как в JavaScript:

```dart
var gifts = {'first': 'partridge'};
gifts['fourth'] = 'calling birds'; // оба варианта правильны
```

Получение значений так же подобно JavaScript:

```dart
var gifts = {'first': 'partridge'};
assert(gifts['first'] == 'partridge');
```

Если вы запросите несуществующий ключ, получите `null`:

```dart
var gifts = {'first': 'partridge'};
assert(gifts['fifth'] == null);
```

Используйте .length, чтобы получить количество пар ключ-значение в карте:

```dart
var gifts = {'first': 'partridge'};
gifts['fourth'] = 'calling birds';
assert(gifts.length == 2);
```

Чтобы создать карту константой времени компиляции, добавьте `const` перед литералом карты:

```dart
final constantMap = const {
  2: 'helium',
  10: 'neon',
  18: 'argon',
};

// constantMap[2] = 'Helium'; // Изменение значения приведет к ошибке
```

Начиная с Dart 2.3, карты поддерживают операторы распространения (... и ...?) И коллекции, `if` и `for`, как списки.
