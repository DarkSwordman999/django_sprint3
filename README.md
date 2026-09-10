<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20&height=180&section=header&text=Blogicum&fontSize=70&fontAlignY=35&desc=Django%20Blog%20Platform%20%7C%20Yandex%20Practicum&descAlignY=55&descSize=18" alt="Blogicum Banner" width="100%">

<img src="https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python">
<img src="https://img.shields.io/badge/Django-5.x-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django">
<img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite">
<img src="https://img.shields.io/badge/Bootstrap-5.0.1-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap">

<br>

<img src="https://img.shields.io/badge/Pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white" alt="Pytest">
<img src="https://img.shields.io/badge/pytest--django-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white" alt="pytest-django">
<img src="https://img.shields.io/badge/Flake8-yellow?style=for-the-badge&logo=python&logoColor=white" alt="Flake8">
<img src="https://img.shields.io/badge/Yandex-Practicum-red?style=for-the-badge&logo=yandex&logoColor=white" alt="Yandex Practicum">

<br><br>

<h2>📝 Blogicum — блог-платформа на Django</h2>

<p>
  <b>Учебный проект в рамках курса «Python-разработчик» от Яндекс Практикума</b>
</p>

</div>

---

## 📖 О проекте

**Blogicum** — веб-платформа для ведения блогов. Пользователи могут публиковать записи, привязывать их к категориям и локациям, а также просматривать публикации других авторов.

В рамках третьего спринта проект полностью переведён на Django:

* подключены модели и база данных;
* реализовано наследование шаблонов;
* настроена маршрутизация с `namespace`;
* добавлена работа с реальными данными;
* подключён дамп `db.json`;
* реализованы автоматические тесты и линтинг.

### 🔄 Текущий этап

```text
Статическая вёрстка
        ↓
Django Templates
        ↓
Модели и база данных
        ↓
Динамические страницы
        ↓
Аутентификация и профили
        ↓
Комментарии
        ↓
Полноценная блог-платформа
```

---

## ✅ Реализовано

### 🧩 Django и модели

* Django-проект с приложениями `blog` и `pages`.
* Модели:

  * `Category`
  * `Location`
  * `Post`
* Поля моделей:

  * `created_at`
  * `is_published`
  * `title`
  * `slug`
  * `description`
  * `text`
  * `pub_date`
  * `author`
  * `category`
  * `location`

### 🎨 Шаблоны

* Базовый шаблон `base.html`.
* Наследование шаблонов через блоки `title` и `content`.
* Переиспользуемые шаблонные включения:

  * `header.html`
  * `footer.html`
  * `post_card.html`
  * `category_link.html`

### 📄 Страницы

* Лента публикаций.
* Страница отдельного поста.
* Страница категории.
* Страница «О проекте».
* Страница «Наши правила».

### 🔗 Маршрутизация

Настроены именованные маршруты с использованием `namespace`:

```text
blog:index
blog:post_detail
blog:category_posts

pages:about
pages:rules
```

Активный пункт навигации определяется через:

```python
request.resolver_match.view_name
```

### 🗃️ Данные

Проект содержит дамп `db.json`:

| Сущность     | Количество |
| :----------- | ---------: |
| Категории    |          6 |
| Локации      |         12 |
| Посты        |         39 |
| Пользователи |          4 |

---

## 🚧 В разработке

* 👤 Регистрация и авторизация пользователей.
* 🪪 Профили пользователей.
* 💬 Комментарии к постам.
* 🖼️ Загрузка изображений к публикациям.
* ✏️ Создание и редактирование постов через пользовательский интерфейс.

---

## 🛠️ Технологии

| Технология          | Назначение                 |
| :------------------ | :------------------------- |
| **Python 3.10+**    | Язык разработки            |
| **Django 5.x**      | Веб-фреймворк              |
| **SQLite**          | База данных                |
| **Bootstrap 5.0.1** | CSS-фреймворк              |
| **Pytest**          | Тестирование               |
| **pytest-django**   | Интеграция Pytest с Django |
| **Flake8**          | Линтинг кода               |

---

## 📂 Структура проекта

```text
django_sprint3/
├── templates/
│   ├── blog/
│   │   ├── category.html          # Страница категории
│   │   ├── detail.html            # Страница отдельного поста
│   │   └── index.html             # Лента записей
│   │
│   ├── includes/
│   │   ├── category_link.html     # Ссылка на категорию
│   │   ├── footer.html             # Подвал сайта
│   │   ├── header.html             # Навигация
│   │   └── post_card.html          # Карточка поста
│   │
│   ├── pages/
│   │   ├── about.html              # Страница «О проекте»
│   │   └── rules.html              # Страница «Наши правила»
│   │
│   └── base.html                   # Базовый шаблон
│
├── tests/
│   ├── fixtures/                    # Фикстуры для тестов
│   ├── conftest.py                  # Общие настройки pytest
│   ├── test_admin_page.py           # Тесты админки
│   ├── test_category_model.py       # Тесты модели Category
│   ├── test_category_page_views.py  # Тесты страницы категории
│   ├── test_localization.py         # Тесты локализации
│   ├── test_location_model.py       # Тесты модели Location
│   ├── test_pageapp_views.py        # Тесты статических страниц
│   ├── test_post_detail_views.py    # Тесты страницы поста
│   ├── test_post_model.py           # Тесты модели Post
│   ├── test_posts_page_views.py     # Тесты ленты постов
│   └── test_urls.py                 # Тесты маршрутов
│
├── .flake8                          # Конфигурация Flake8
├── .gitignore                       # Исключения Git
├── LICENSE                          # Лицензия проекта
├── README.md                        # Документация
├── db.json                          # Дамп данных
├── pytest.ini                       # Конфигурация pytest
├── requirements.txt                 # Зависимости проекта
└── manage.py                        # Управляющий скрипт Django
```

---

## 🚀 Запуск проекта

### 📋 Требования

* **Python** 3.10 или выше
* **pip** для установки зависимостей

<details>
<summary><b>1. Клонирование репозитория</b></summary>

```bash
git clone https://github.com/DarkSwordman999/django_sprint3.git
cd django_sprint3
```

</details>

<details>
<summary><b>2. Виртуальное окружение</b></summary>

```bash
python -m venv venv
```

**Windows:**

```bash
venv\Scripts\activate
```

**macOS / Linux:**

```bash
source venv/bin/activate
```

</details>

<details>
<summary><b>3. Установка зависимостей</b></summary>

```bash
pip install -r requirements.txt
```

</details>

<details>
<summary><b>4. Применение миграций</b></summary>

```bash
python manage.py migrate
```

</details>

<details>
<summary><b>5. Загрузка тестовых данных</b></summary>

Данные из подготовленного дампа загружаются командой:

```bash
python manage.py loaddata db.json
```

</details>

<details>
<summary><b>6. Запуск сервера</b></summary>

```bash
python manage.py runserver
```

После запуска проект будет доступен по адресу:

```text
http://127.0.0.1:8000/
```

Админ-панель:

```text
http://127.0.0.1:8000/admin/
```

</details>

---

## 🧪 Тестирование

Для тестирования используется **Pytest** совместно с **pytest-django**.

Конфигурация тестового окружения находится в:

```text
pytest.ini
```

Запуск всех тестов:

```bash
pytest
```

### 🔍 Что проверяется

| Область         | Тесты                                                                                                           |
| :-------------- | :-------------------------------------------------------------------------------------------------------------- |
| **Модели**      | `test_category_model.py`, `test_location_model.py`, `test_post_model.py`                                        |
| **Вьюхи**       | `test_category_page_views.py`, `test_post_detail_views.py`, `test_posts_page_views.py`, `test_pageapp_views.py` |
| **Маршруты**    | `test_urls.py`                                                                                                  |
| **Админка**     | `test_admin_page.py`                                                                                            |
| **Локализация** | `test_localization.py`                                                                                          |

---

## 🧹 Линтинг

Для проверки качества и соответствия кода стандартам используется **Flake8**.

Конфигурация находится в:

```text
.flake8
```

Запуск проверки:

```bash
flake8 .
```

---

## 📄 Лицензия

Проект распространяется под лицензией, указанной в файле [`LICENSE`](./LICENSE).

---

## 👤 Автор

<div align="center">

### DarkSwordman999

<a href="https://github.com/DarkSwordman999">
  <img src="https://img.shields.io/badge/GitHub-DarkSwordman999-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</a>

</div>

---

<div align="center">

### 🎓 Yandex Practicum

**Проект создан в рамках курса «Python-разработчик» от Яндекс Практикума.**

*Учебный проект. Создан в образовательных целях.*

</div>
