# Break и continue

Используйте `break` для прирывания цикла

```dart
while (true) {
  if (shutDownRequested()) break;
  processIncomingRequests();
}
```

Для пропуска текущей итерации используйте `continue`:

```dart
for (int i = 0; i < candidates.length; i++) {
  var candidate = candidates[i];
  if (candidate.yearsExperience < 5) {
    continue;
  }
  candidate.interview();
}
```

Даный пример можно написать по-другому, если вы используете Iterable, такой как `List` или `Set`:

```dart
candidates
    .where((c) => c.yearsExperience >= 5)
    .forEach((c) => c.interview());
```
