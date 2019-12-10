# Проверка установки

Если в консоли CMD при вводе `flutter doctor` вы получаете состояние flutter sdk,
то вы все сделали правильно, и можете создать свой первый проект.

>В случае если `flutter doctor` отвечает ошибкой об отсутствии команды flutter - [установите](2_setup_flutter.md) ее.

- Меняем ветку sdk на мастер и обновляем исходный код
`flutter channel master && flutter upgrade`

- Включаем поддержку веб сборки
`flutter config enable-web`

- Переходим в каталог с рабочими проектами `cd Documents\src`

>Пути могут отличатся! при необходимости можете создать новый каталог командой `mkdir folder_name`

- Создаем новый проект `flutter create my_firs+project`
  
- Открываем его `cd my_firs+project`
  
- Запускаем `flutter run -d chrome`

>Должна быть установлена последняя версия chrome browser

- Для просмотра исходного кода введите в консоли `code .`
