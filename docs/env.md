> *!!!!* 
> ВСЕ МАНИПУЛЯЦИИ С ПЕРЕМЕННОЙ PATH ВЫПОЛНЯЮТСЯ ТОЛЬКО ПЕРВЫЙ РАЗ ДЛЯ ПЕРВОГО ПРОЕКТА, ДЛЯ ПОСЛДУЮЩИХ ЭТОТ ШАГ ПРОПУСТИТЬ

# 1 Подготовка рабочего пространства.

## 1.1 установка Flutter

- https://flutter.dev/docs/development/tools/sdk/releases
- скачать первый архив в таблице Stable channel (Windows)

- распокавать архив и положить папку flutter в корень диска C:\
    должно получится C:\flutter

- Добавить в PATH

    - С:\flutter\bin
    - С:\flutter\bin\cache\dart-sdk\bin 

>PATH: компьютер -> правый клик -> свойства -> 
(с лева) дополнительные параметры системы -> 
(внизу) параметры среды -> (верхний список) клик по PATH -> 
изменить -> в значение переменной вставить путь 


>**WINDOW 7** значения должны быть разделены ; без пробелов!!!

```BASH
С:\flutter\bin;С:\flutter\bin\cache\dart-sdk\bin;
```

- Проверить установку 
    запустить cmd (win + r -> ввести cmd -> нажать Enter(или открыть),
    ввести `flutter doctor`,
    нажать Enter

>В случае ошибки проведить переменную PATH из предыдущего шага

- Для работы Flutter Web и Flutter Desktop в cmd ввести `flutter channel master && flutter upgrade`

## 1.2 Установить AndroidStudio
- https://developer.android.com/studio скачать и установить все предлогаемые сдк.
- Запустить. На приветственном экране зайти в меню Configure -> AVD Manager
- Создать виртуальный девайс
  - выбрать устройство (предпачтительно Pixel) 
  - скачать API 27 (Pie)
  - Далее все поумолчанию. Запустить виртуальное устройство для проверки

## 1.3 Установить Visual Studio Code
- https://code.visualstudio.com/

### Установить плагины для Visual Studio Code (Flutter)

- открыть VS Code
- ctrl+shift+x
- в строке поиска `Flutter`
- первый в поиске плагин
- Install
- Проверить работоспособность созданием нового проекта (ctrl+shift+p -> Flutter: New Project)
- F5 для запустить проекта в эмуляторе или физическом устройстве

# 2 Flutter Desktop

## Установить Microsoft Visual Studio 20{ГОД} (=< 17)
https://visualstudio.microsoft.com/ru/downloads/

- Visual Studio 20{год} Community
- запустится компановщик
- поставить галочку в разделе "Desktop Development C++"
- *установить*

перевести в вветку master
*для запуска десктоп приложений необходимо:*

- **2.1 Добавить в PATH путь к сдк с++**
    у меня он 
    *C:\Program Files (x86)\Microsoft Visual Studio\2019\BuildTools\VC\Auxiliary\Build*
    **!!!МОЖЕТ ОТЛИЧАТЬСЯ ГОД!!!**
- **2.2 Создать новое приложение flutter в Intellij**
- **2.3 в main.dart добавить импорты** 

```dart
import 'dart:io' show Platform;
import 'package:flutter/foundation.dart' show debugDefaultTargetPlatformOverride;
```
- **2.3 изменить функцую main в main.dart**
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
- **2.4 Из папки ForDesktop windows, macos, linux копировать в корень проекта**
    должно получится
```
 project
    android
    ios
    lib
    linux
    macos
    windows
    pubspec.yaml
```
    
- **2.5 в терминале Intellij последовательно ввести 2 команды**
`flutter packages get`

`flutter precache --windows`

- **2.6 установить переменную среды (*в том же терминале*)**

`set ENABLE_FLUTTER_DESKTOP=true`

**ВНИМАНИЕ переменную необходимо устанавливать каждый раз при открытии терминала!!!**

- **2.7 проверить что все хорошо командой**
`flutter devices`

*должен быть ответ вроде*

```bash
1 connected device:

Windows • Windows • windows-x64 • Microsoft Windows [Version 6.1.7601]
```
 
**значит все хорошо и можно запустить приложение командой**

`flutter run`

***В случае когда подключенное несколько устройст или эмулятор можно получить подобное сообщение***

```bash
More than one device connected; please specify a device with the '-d <deviceId>' flag, or use '-d all' to act on all devices.

Android SDK built for x86 • emulator-5554 • android-x86 • Android 9 (API 28) (emulator)
Windows                   • Windows       • windows-x64 • Microsoft Windows [Version 6.1.7601]
```

в этом случае для замуска для Десктопа вводим команду

`flutter run -d DEVICE`

в данном случае для виндовс

```
flutter run -d windows
```

или для запуска на эмуляторе

```
flutter run -d emulator-5554
```

***ID могут отличаться, смотреть свои, они указанны во втором столбике***

**Для применения изменений ввести в терминал**
**r** хот релоад
**shift+r** хот рестарт


# 3 Flutter WEB

- *3.1 создать новый проект в качестве языка выбрать Dart*
    ( если в Dart SDK path: *not found*)
    выбрать его руками он расположен в папке flutter
 ```
 C:\flutter\bin\cache\dart-sdk
 ```
    мой путь такой

- **3.2 Выбрать шаблон** *Flutter Web App*

- **3.3 в терминале Intellij выполнить**
`flutter pub global activate webdev`

- **3.4 добавить в PATH см 1.1**
*путь к flutter может отличаться!!* мой такой:
`c\flutter\.pub-cache\bin`

- **3.5 в терминале Intellij выполнить**
`flutter pub upgrade`

- **3.6 в терминале Intellij выполнить**
`webdev serve --auto refresh`

- **3.7 открыть localhost:8080** в браузере

**Для поддержки иконок не обходимо допавить папку assets из ForWeb в папку web в проекте**

**Для изменения применяются автоматически, необходимо просто кликнуть по браузеру**


# Минимальная версия флаттера 1.5!
проверить свою версию можнов в cmd
``flutter doctor``

если версия ниже
выполнить в cmd

```
flutter upgrade
```







