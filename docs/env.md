# Подготовка рабочего пространства

Все манипуляции с переменной `PATH` выполняются **только один раз** для первого проекта, для последующих этот шаг **следует пропустить**

## Установка Flutter

- [Загрузить](https://flutter.dev/docs/development/tools/sdk/releases) первый архив в таблице `Stable channel (Windows)`

- распаковать архив и положить папку flutter в корень диска C:\
  *должно получится C:\flutter*

- [Добавить](#PATH) в PATH
  - *С:\flutter\bin*
  - *С:\flutter\bin\cache\dart-sdk\bin*

- Проверка установки
  - запустить cmd (win + r -> ввести cmd -> нажать Enter(или открыть)
  - ввести `flutter doctor`,
    нажать Enter

>В случае ошибки проверить переменную [PATH](#PATH)

### PATH

PATH - это переменная окружения, которая является набором каталогов содержащих исполняемые файлы.

Для установки добавления нового каталога в переменную на компьютерах под управлением OS Windows 10 необходимо открыть компьютер -> правый клик -> свойства ->
(с лева) дополнительные параметры системы ->
(внизу) параметры среды -> (верхний список) клик по PATH ->
изменить -> в значение переменной вставить путь

>**Windows 7** значения должны быть разделены ; без пробелов!!!

```path
С:\flutter\bin;С:\flutter\bin\cache\dart-sdk\bin;
```

## Установить AndroidStudio

- [Скачать](https://developer.android.com/studio) и установить все предлагаемые SDK.
- Запустить. На приветственном экране зайти в меню Configure -> AVD Manager
- Создать виртуальный девайс
  - выбрать устройство (предпочтительно Pixel)
  - скачать API 27 (Pie)
  - Далее все по умолчанию. Запустить виртуальное устройство для проверки

## Установить Visual Studio Code

- https://code.visualstudio.com/

### Установить плагины для Visual Studio Code (Flutter)

- открыть VS Code
- `ctrl+shift+x`
- в строке поиска `Flutter`
- первый в поиске плагин
- Install

### Create Project

- Проверить работоспособность созданием нового проекта `ctrl+shift+p -> Flutter: New Project`
- `F5` для запустить проекта в эмуляторе или физическом устройстве

### Запуск на устройстве

Для запуска на физическом устройстве необходимо активировать "Режим Разработчика". Для этого нужно открыть Настройки -> О телефоне -> 5 раз тапнуть на строку "номер сборки", должно появится всплывающее сообщение "Вы стали разработчиком". После чего вернуть назад, в меню настроек должна появится вкладка "Для разработчиков", там необходимо активировать пункт "Разрешить отладку по USB {ADB}"

# Flutter Desktop

## Flutter Channels
Для работы Flutter Web и Flutter Desktop должен находится в ветке `master`

Проверить ветку можно командой в CMD `flutter channel`

```Bash
Flutter channels:
 beta
 dev
*master
 stable
```

`*` означает выбранную ветку, она должна стоять рядом с мастер, в противном случае нужно изменить текущую ветку

`flutter channel master && flutter upgrade`

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

# Flutter WEB

- Создать [новый проект](#Create-Project) `Flutter: New Web Project`

- добавить в [PATH](#PATH)
*путь к flutter может отличаться!!* мой :
`c:\flutter\.pub-cache\bin`

- в терминале VS CODE выполнить
`webdev serve --auto refresh`

- открыть localhost:8080 в браузере (предпочтительно Google Chrome)

Для поддержки иконок необходимо добавить папку `assets` из [ForWeb](https://yadi.sk/d/PfTuqBQUOzeKBg) в папку `web` в проекте

>Изменения применяются автоматически после сохранения редактируемого файла
