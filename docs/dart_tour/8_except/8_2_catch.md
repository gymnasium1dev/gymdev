# Catch

Catch или захват исключения останавливает распространение ошибки на другие модули. Пойманное исключение дает вам возможность обработать его:

```dart
try { // попытка выполнить, что-то
  breedMoreLlamas();
} on OutOfLlamasException {  //если во время исполнения произошла ошибка типа OutOfLlamasException
  buyMoreLlamas(); //предпринемаем действия для ее исправления
}
```

Для обработки кода, который может генерировать более одного типа исключений, вы можете указать несколько catch. Первое catch, соответствующее типу брошенного исключения, и обрабатывает его. Если ошибка отличается от явно указанных типов, ее можно обработат при помощи `catch `:

```dart
try {
  breedMoreLlamas();
} on OutOfLlamasException {
  // проверка на определенную ошибку
  buyMoreLlamas();
} on Exception catch (e) {
  // ошибка другого типа
  print('Unknown exception: $e');
} catch (e) {
  // Nдля всех остальных
  print('Something really unknown: $e');
}

```

Как показывает предыдущий код, вы можете использовать on или catch или оба. Используйте, когда вам нужно указать тип исключения. Используйте catch, когда вашему обработчику исключений нужен объект исключения.

Вы можете указать один или два параметра для catch (). Первое - это исключение, а второе - трассировка стека (объект StackTrace). Простыми словами это список методов после вызова которых произошло исключение.

```dart
try {
  // ···
} on Exception catch (e) {
  print('Exception details:\n $e');
} catch (e, s) {
  print('Exception details:\n $e');
  print('Stack trace:\n $s');
}
```

Чтобы частично обработать исключение и разрешить дальнейшее исполнение кода, используйте ключевое слово `rethrow`.

```dart
void misbehave() {
  try {
    dynamic foo = true;
    print(foo++); // Runtime error
  } catch (e) {
    print('misbehave() partially handled ${e.runtimeType}.');
    rethrow; // Allow callers to see the exception.
  }
}

void main() {
  try {
    misbehave();
  } catch (e) {
    print('main() finished handling ${e.runtimeType}.');
  }
}
```
