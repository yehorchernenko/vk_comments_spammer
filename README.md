# VK-comments-spammer

## 1. Качаем VPN
Например: https://clearvpn.com, по промокоду SAVEUKRAINE год бесплатно.


## 2. Регистрируемся и создаем приложения в VK
Зайдите на https://vk.com/editapp?act=create
Создайте standalone-приложение
Из настроек созданного приложения сохраните "ID приложения" и "Защищенный ключ"

## 3. Получение access token
Вставляем "ID приложения" в параметр client_id в ссылке https://oauth.vk.com/authorize?client_id=5618632&display=popup&response_type=code&redirect_uri=https://oauth.vk.com/blank.html&scope=groups,wall,offline
Переходим по ней и нажимаем разрешить.
Ссылка адресной строке браузера изменилась на ссылку вида https://oauth.vk.com/blank.html#code=465de75dbc97d61ec3. Запоминаем параметр code.
Вставляем
"ID приложения" в параметр client_id
"Защищенный ключ" в параметр client_secret
code в параметр code
в ссылке https://oauth.vk.com/access_token?client_id=5618632&client_secret=lmx9YRAjH6jrJ2FJBCwh&redirect_uri=https://oauth.vk.com/blank.html&code=465de75dbc97d61ec3

Переходим по получившийся ссылке и получаем access_token (может быть в адрессной строке)

## 4. Устанавливаем менеджер пакетов Conda
1. [Installation link for Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html)
2. Устанавливаем VK Api `pip install vk_api`.
3. Открываем `vk_comments.ipynb` через Jupyter notebook `jupyter notebook vk_comments.ipynb` (Юпитер оч удобная штука, позволяет запускать код отдельными блоками, это особенно полезно когда меняем контент или пулл групп)


## 5. Готовим контент и вбой
0. Подставьте номер телефона и пароль во второй ячейке и access_token в третьей.
1. В ячейке номер четыре добавляйте айдишники групп (`wall_ids`) (должны начинаться с -) или короткие имена из ссылки (`short_names`), например https://vk.com/svegienov
2. Добавляем тело комментария `messages`: `('тут текст', 'тут ссылка на фото, оставляем пустой если ее нет')`
3. Optiona: как добавить фото? Загружаем себе на страницу, из ссылки копируем параметр `z` https://vk.com/id7123416428?z=photo711016428_457239034%2Falbum711016428_00%2Frev, в этом случае `photo711016428_457239034`, вставляем во второй параметр, как описано в пункте 2.
