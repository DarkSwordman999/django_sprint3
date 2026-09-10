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

**Blogicum** — учебная блог-платформа, разработанная на Django.

Пользователи могут просматривать публикации, находить записи по категориям и локациям, а также переходить на страницы отдельных постов.

В рамках третьего спринта проект перешёл от статической HTML-вёрстки к полноценной работе с Django:

* созданы модели и связи между ними;
* подключена база данных SQLite;
* реализовано наследование Django-шаблонов;
* настроена маршрутизация с `namespace`;
* добавлены переиспользуемые шаблонные компоненты;
* подключены реальные данные из `db.json`;
* настроены автоматические тесты;
* добавлена проверка кода через Flake8.

---

## ✨ Основные возможности

### 📝 Работа с публикациями

* Просмотр ленты постов.
* Просмотр отдельной публикации.
* Фильтрация публикаций по категориям.
* Отображение автора, даты публикации и локации.
* Работа только с актуальными и опубликованными записями.

### 🗂️ Категории и локации

Посты связаны с соответствующими категориями и локациями через Django ORM.

В проекте используются отдельные модели:

```text
Category
Location
Post
```

### 🎨 Система шаблонов

Для устранения дублирования используется наследование шаблонов:

```text
base.html
    ├── index.html
    ├── category.html
    ├── detail.html
    ├── about.html
    └── rules.html
```

Дополнительно используются переиспользуемые `include`:

```text
header.html
footer.html
post_card.html
category_link.html
```

### 🔗 Namespace-маршрутизация

Для удобной работы с URL используются именованные маршруты:

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

---

## 🗃️ Данные проекта

Для демонстрации работы приложения подготовлен дамп `db.json`.

| Сущность        | Количество |
| :-------------- | ---------: |
| 📂 Категории    |          6 |
| 📍 Локации      |         12 |
| 📝 Посты        |         39 |
| 👤 Пользователи |          4 |

Загрузка данных выполняется стандартной Django-командой:

```bash
python manage.py loaddata db.json
```

---

## 🚧 В разработке

Следующие возможности планируется реализовать на следующих этапах проекта:

* 👤 Регистрация и авторизация пользователей.
* 🪪 Профили пользователей.
* 💬 Комментарии к публикациям.
* 🖼️ Загрузка изображений к постам.
* ✏️ Создание новых публикаций через интерфейс.
* 📝 Редактирование собственных публикаций.

---

## 🛠️ Технологический стек

| Технология          | Назначение                  |
| :------------------ | :-------------------------- |
| **Python 3.10+**    | Основной язык разработки    |
| **Django 5.x**      | Веб-фреймворк               |
| **SQLite**          | База данных                 |
| **Bootstrap 5.0.1** | Стилизация интерфейса       |
| **Pytest**          | Автоматическое тестирование |
| **pytest-django**   | Интеграция Pytest с Django  |
| **Flake8**          | Проверка качества кода      |

---

## 📂 Структура проекта

```text
django_sprint3/
├── templates/
│   ├── blog/
│   │   ├── category.html          # Страница категории
│   │   ├── detail.html            # Страница отдельного поста
│   │   └── index.html             # Лента публикаций
│   │
│   ├── includes/
│   │   ├── category_link.html     # Ссылка на категорию
│   │   ├── footer.html             # Подвал сайта
│   │   ├── header.html             # Навигация
│   │   └── post_card.html          # Карточка публикации
│   │
│   ├── pages/
│   │   ├── about.html              # Страница «О проекте»
│   │   └── rules.html              # Страница «Наши правила»
│   │
│   └── base.html                   # Базовый шаблон
│
├── tests/
│   ├── fixtures/                   # Фикстуры
│   ├── conftest.py                 # Конфигурация pytest
│   ├── test_admin_page.py          # Тесты админки
│   ├── test_category_model.py      # Тесты Category
│   ├── test_category_page_views.py # Тесты страницы категории
│   ├── test_localization.py        # Тесты локализации
│   ├── test_location_model.py      # Тесты Location
│   ├── test_pageapp_views.py       # Тесты статических страниц
│   ├── test_post_detail_views.py   # Тесты страницы поста
│   ├── test_post_model.py           # Тесты Post
│   ├── test_posts_page_views.py     # Тесты ленты
│   └── test_urls.py                 # Тесты маршрутов
│
├── .flake8                         # Конфигурация Flake8
├── .gitignore                      # Исключения Git
├── LICENSE                         # Лицензия
├── README.md                       # Документация проекта
├── db.json                         # Дамп базы данных
├── pytest.ini                      # Конфигурация pytest
├── requirements.txt                # Зависимости
└── manage.py                       # Управляющий скрипт Django
```

---

## 🚀 Запуск проекта

### 📋 Требования

Перед началом работы убедитесь, что установлены:

* **Python 3.10+**
* **pip**
* **Git**

<details>
<summary><b>1. Клонирование репозитория</b></summary>

```bash
git clone https://github.com/DarkSwordman999/django_sprint3.git
cd django_sprint3
```

</details>

<details>
<summary><b>2. Создание виртуального окружения</b></summary>

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
<summary><b>5. Загрузка данных</b></summary>

```bash
python manage.py loaddata db.json
```

</details>

<details>
<summary><b>6. Запуск сервера разработки</b></summary>

```bash
python manage.py runserver
```

После запуска приложение будет доступно по адресу:

```text
http://127.0.0.1:8000/
```

Административная панель:

```text
http://127.0.0.1:8000/admin/
```

</details>

---

## 🧪 Тестирование

В проекте используется связка **Pytest + pytest-django**.

Конфигурация тестов находится в:

```text
pytest.ini
```

Запуск полного набора тестов:

```bash
pytest
```

### 🔍 Что покрывают тесты

| Раздел            | Тесты                                                                                                           |
| :---------------- | :-------------------------------------------------------------------------------------------------------------- |
| **Модели**        | `test_category_model.py`, `test_location_model.py`, `test_post_model.py`                                        |
| **Представления** | `test_category_page_views.py`, `test_post_detail_views.py`, `test_posts_page_views.py`, `test_pageapp_views.py` |
| **Маршруты**      | `test_urls.py`                                                                                                  |
| **Админ-панель**  | `test_admin_page.py`                                                                                            |
| **Локализация**   | `test_localization.py`                                                                                          |

---

## 🧹 Линтинг

Для проверки качества и стиля Python-кода используется **Flake8**.

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

Проект распространяется в соответствии с лицензией, указанной в файле [`LICENSE`](./LICENSE).

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

### ⭐ Понравился проект?

Если **Blogicum** оказался полезным или интересным,
**поставьте ⭐ репозиторию на GitHub** — это лучшая поддержка проекта!

<a href="https://github.com/DarkSwordman999/django_sprint3">
  <img src="https://img.shields.io/github/stars/DarkSwordman999/django_sprint3?style=for-the-badge&logo=github&label=Star%20repository" alt="Star repository">
</a>

<br><br>

<i>Спасибо за интерес к проекту! 🚀</i>

</div>

---

<div align="center">

### 🎓 Yandex Practicum

**Проект создан в рамках курса «Python-разработчик» от Яндекс Практикума.**

<i>Учебный проект. Создан в образовательных целях.</i>

</div>
