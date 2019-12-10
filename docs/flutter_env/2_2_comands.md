# Основные команды

## flutter doctor

Данная команда выводит текущее состояни flutter sdk: ветка, версия, готовность сборки под платформы

```bash
flutter doctor

Doctor summary (to see all details, run flutter doctor -v):
[√] Flutter (Channel master, v1.13.1-pre.62, on Microsoft Windows [Version 10.0.18362.476], locale ru-RU)

[√] Android toolchain - develop for Android devices (Android SDK version 29.0.2)
[√] Chrome - develop for the web
[√] Visual Studio - develop for Windows (Visual Studio CommunityВ 2019 16.4.0)
[√] Android Studio (version 3.4)
[√] VS Code (version 1.40.2)
[√] Connected device (3 available)
```

## flutter channel

Данная команда выводит текущую ветку flutter sdk

```Bash
Flutter channels:
 beta
 dev
*master
 stable
```

`*` означает выбранную ветку, она должна стоять рядом с мастер, в противном случае нужно изменить текущую ветку

Для изменения ветки необходимо ввести `flutter channel {channel_name}` и [обновить](#flutter-upgrade) исходный код flutter.

```Bash
flutter channel master && flutter upgrade
```

## flutter upgrade

Обновляет исходный код текущей ветки до актуального состояния.

```Bash
flutter upgrade
```

Так же даная команда позволяет перейти на необходимую версию flutter

```Bash
flutter upgrade 1.13.1
```

Обновит/откатит текущую версию flutter до 1.13.1

## flutter config

Данная команда служит для конфигурации эксперементальных возможностей flutter sdk

Для включения поддержки веб сборки необходимо ввести:

```Bash
flutter config enable-web
```

Для включения поддержки сборки под ОС Windows необходимо ввести:

```Bash
flutter config enable-desctop-windows
```

## flutter devices

Команда `flutter devices` отображает список доступных для сборки девайсов

```Bash
flutter devices
3 connected devices:

Windows    • Windows    • windows-x64    • Microsoft Windows [Version 10.0.18362.476]
Chrome     • chrome     • web-javascript • Google Chrome 78.0.3904.108
Web Server • web-server • web-javascript • Flutter Tools
```

## flutter create

Для создания нового проекта используется команда `flutter create {project_name}`

>Имена проект должны быть в стиле snake_case

`flutter create my_awesome_project`

## flutter run

Команда для запуска отладочной версии проекта `flutter run -d {device_id}`

`flutter run -d chrome` запустит ваш проект в браузере chrome.

Для остановки работающего приложения необходимо ввести `q` в терминал.

Для пересборки работающего приложения необходимо ввести `R` в терминал.

Для обновления интерфейся без потери данных работающего приложения необходимо ввести `r` в терминал. (на данный момент не работает для web)

При зависании вашего приложения небоходимо нажать `ctrl + c` в терминале.

>Если при вводе команд в терминал ни чего не происходит убедитесь, что язык ввода английский или перезапустите приложение.

Флаг `--release` запустит ваше приложение в релизной версии.
`flutter run -d chrome`

## flutter build

Команда `flutter build {platform}` соберет релизную версию вашего проекта в папку `./build`

## flutter clean

Команда `flutter clean` удаляет временный файлы сборки.
