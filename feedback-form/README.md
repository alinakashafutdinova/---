# Feedback form — Московский Политех

Сайт из двух страниц по заданию для самостоятельной работы.

## Структура

```
feedback-form/
├── index.php          # Страница 1: форма обратной связи
├── result.php         # Страница 2: результат функции get_headers
├── assets/
│   ├── style.css      # Стили
│   └── logo.png       # Логотип МосПолитеха
└── README.md
```

## Описание

**Страница 1 (`index.php`)** — форма обратной связи с полями:
- Имя пользователя
- E-mail
- Тип обращения (жалоба / предложение / благодарность)
- Текст обращения
- Вариант ответа (СМС / E-mail) — checkbox
- Кнопка «Отправить» (отправка на `https://httpbin.org/post`)
- Ссылка на 2 страницу

**Страница 2 (`result.php`)** — выводит в `<textarea>` результат работы функции
`get_headers()`. По умолчанию запрашиваются заголовки `https://mospolytech.ru`,
но URL можно изменить через форму на странице.

## Локальный запуск

Для работы нужен PHP (страница `result.php` использует функцию `get_headers`).
В корне проекта выполните:

```bash
php -S localhost:8000
```

Откройте `http://localhost:8000` в браузере.

## Загрузка в репозиторий

```bash
git init
git add .
git commit -m "Feedback form: initial commit"
git branch -M main
git remote add origin <URL вашего репозитория>
git push -u origin main
```

## Деплой на хостинг

Подойдёт любой хостинг с поддержкой PHP (например, Beget, Timeweb, REG.RU,
000webhost). Загрузите все файлы в корень публичной папки (`public_html`
или `www`) через FTP/SFTP или панель управления.

Убедитесь, что в настройках PHP включена директива `allow_url_fopen=On` —
она нужна для работы `get_headers()` с внешними URL.
