# Flutter Desktop

## Установить Microsoft Visual Studio 20{ГОД} (=< 17)

- [Скачать](https://visualstudio.microsoft.com/ru/downloads/) Visual Studio 20{год} Community
- запустится компоновщик
- поставить галочку в разделе "Desktop Development C++"
- установить

## Подготовка проекта

- Добавить в PATH путь к sdk с++
    у меня он `C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build`
- Создать новое приложение flutter в VS CODE ([Создание проекта](#Create-Project))
- Добавить импорты в main.dart

```dart
import 'dart:io' show Platform;
import 'package:flutter/foundation.dart' show debugDefaultTargetPlatformOverride;
```

- изменить функцую `main()` в lib/main.dart

c

```dart
void main => runApp(MyApp());
```

на

```dart
void main() {
  debugDefaultTargetPlatformOverride = TargetPlatform.fuchsia;
  runApp(MyApp());
}
```

- Из папки [ForDesktop](https://yadi.sk/d/PfTuqBQUOzeKBg) `windows, macos, linux` копировать в корень проекта, должно получится

```DIR
 project
    android
    ios
    lib
    linux
    macos
    windows
    pubspec.yaml
```

- В терминале VSCode(ctrl+shift+~) последовательно ввести
`flutter packages get`

- Проверить что Flutter SDK готов для сборки под windows командой
`flutter devices`

предполагаемый ответ

```bash
1 connected device:

Windows • Windows • windows-x64 • Microsoft Windows [Version 6.1.7601]
```

значит все хорошо и можно запустить приложение командой

`flutter run`

***В случае когда подключенное несколько устройств или эмулятор можно получить подобное сообщение***

```bash
More than one device connected; please specify a device with the '-d <deviceId>' flag, or use '-d all' to act on all devices.

Android SDK built for x86 • emulator-5554 • android-x86 • Android 9 (API 28) (emulator)
Windows                   • Windows       • windows-x64 • Microsoft Windows [Version 6.1.7601]
```

в этом случае для запуска вводим команду

`flutter run -d DEVICE`

в случае для Windows

```Bash
flutter run -d windows
```

или для запуска на эмуляторе

```Bash
flutter run -d emulator-5554
```

***ID могут отличаться, смотреть свои, они указанны во втором столбике***

**Для применения изменений ввести в терминал**
**r** хот релоад
**shift+r** хот рестарт
