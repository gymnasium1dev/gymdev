# PATH

PATH - это переменная окружения, которая является набором каталогов содержащих исполняемые файлы.

Для установки добавления нового каталога в переменную на компьютерах под управлением OS Windows 10 необходимо открыть компьютер -> правый клик -> свойства ->
(с лева) дополнительные параметры системы ->
(внизу) параметры среды -> (верхний список) клик по PATH ->
изменить -> в значение переменной вставить путь

>**Windows 7** значения должны быть разделены ; без пробелов!!!

```path ПРИМЕР
С:\flutter\bin;С:\flutter\bin\cache\dart-sdk\bin;
```

>**Windows 7** если в системе несколько логических дисков (C,D,F...) после установки переменной окружения PATH
возможны проблемы с командой `flutter` (ошибка отсутствия команды). Для ее решения перенести папку flutter с диска C на другой раздел
и изменить переменную PATH.
