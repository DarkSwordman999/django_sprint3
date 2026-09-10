<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20&height=180&section=header&text=Blogicum&fontSize=70&fontAlignY=35&desc=Django%20Blog%20Platform%20%7C%20Yandex%20Practicum&descAlignY=55&descSize=18" alt="Banner" width="100%">

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

<h2>🐍 Blogicum — блог-платформа на Django</h2>

<p><b>Учебный проект в рамках курса «Python-разработчик» от Яндекс Практикума</b></p>

</div>

<hr>

<h2>📖 О проекте</h2>

<p><b>Blogicum</b> — площадка для ведения блогов. Пользователи могут публиковать посты, привязывать их к категориям и локациям, а также просматривать записи других авторов.</p>

<p>В третьем спринте полностью подключены Django-модели, шаблоны с наследованием, маршрутизация с namespace и работа с реальными данными из БД через дамп <code>db.json</code>.</p>

<hr>

<h2>✅ Что уже сделано</h2>

<ul>
  <li>Django-проект с приложениями <code>blog</code> и <code>pages</code>.</li>
  <li>Модели <code>Category</code>, <code>Location</code>, <code>Post</code> с полями <code>created_at</code>, <code>is_published</code>, <code>title</code>, <code>slug</code>, <code>description</code>, <code>text</code>, <code>pub_date</code>, <code>author</code>, <code>category</code>, <code>location</code>.</li>
  <li>Базовый шаблон <code>base.html</code> с блоками <code>title</code> и <code>content</code>.</li>
  <li>Инклюды: <code>header.html</code>, <code>footer.html</code>, <code>post_card.html</code>, <code>category_link.html</code>.</li>
  <li>Страницы: лента записей, пост, категория, «О проекте», «Наши правила».</li>
  <li>Маршрутизация с namespace: <code>blog:index</code>, <code>blog:post_detail</code>, <code>blog:category_posts</code>, <code>pages:about</code>, <code>pages:rules</code>.</li>
  <li>Подсветка активного пункта меню через <code>request.resolver_match.view_name</code>.</li>
  <li>Дамп данных <code>db.json</code>: 6 категорий, 12 локаций, 39 постов, 4 пользователя.</li>
  <li>Настроены линтеры и тесты.</li>
</ul>

<hr>

<h2>🚧 Что в разработке</h2>

<ul>
  <li>Регистрация, авторизация и профили пользователей.</li>
  <li>Комментарии к постам.</li>
  <li>Загрузка изображений к постам.</li>
  <li>Возможность создавать и редактировать посты через интерфейс.</li>
</ul>

<hr>

<h2>🛠️ Технологии</h2>

<div align="center">

<table>
  <thead>
    <tr>
      <th align="left">Технология</th>
      <th align="left">Назначение</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><b>Python</b></td><td>Язык разработки</td></tr>
    <tr><td><b>Django</b></td><td>Веб-фреймворк</td></tr>
    <tr><td><b>SQLite</b></td><td>База данных</td></tr>
    <tr><td><b>Bootstrap</b></td><td>CSS-фреймворк</td></tr>
    <tr><td><b>Pytest</b></td><td>Тестирование</td></tr>
    <tr><td><b>pytest-django</b></td><td>Интеграция pytest с Django</td></tr>
    <tr><td><b>Flake8</b></td><td>Линтинг кода</td></tr>
  </tbody>
</table>

</div>

<hr>

<h2>📂 Структура проекта</h2>

<pre><code>django_sprint3/
├── templates/
│   ├── blog/
│   │   ├── category.html       # Страница категории
│   │   ├── detail.html         # Страница отдельного поста
│   │   └── index.html          # Лента записей
│   ├── includes/
│   │   ├── category_link.html  # Ссылка на категорию
│   │   ├── footer.html         # Подвал сайта
│   │   ├── header.html         # Навигация
│   │   └── post_card.html      # Карточка поста
│   ├── pages/
│   │   ├── about.html          # Страница «О проекте»
│   │   └── rules.html          # Страница «Наши правила»
│   └── base.html               # Базовый шаблон
├── tests/
│   ├── fixtures/               # Фикстуры для тестов
│   ├── conftest.py             # Общие настройки pytest
│   ├── test_admin_page.py      # Тесты админки
│   ├── test_category_model.py  # Тесты модели Category
│   ├── test_category_page_views.py
│   ├── test_localization.py    # Тесты локализации
│   ├── test_location_model.py  # Тесты модели Location
│   ├── test_pageapp_views.py   # Тесты статических страниц
│   ├── test_post_detail_views.py
│   ├── test_post_model.py      # Тесты модели Post
│   ├── test_posts_page_views.py
│   └── test_urls.py            # Тесты маршрутов
├── .flake8                     # Конфигурация flake8
├── .gitignore                  # Исключения Git
├── LICENSE                     # Лицензия проекта
├── README.md                   # Документация
├── db.json                     # Дамп данных для загрузки в БД
├── pytest.ini                  # Конфигурация pytest
├── requirements.txt            # Зависимости проекта
└── manage.py                   # Управляющий скрипт Django</code></pre>

<hr>

<h2>🚀 Запуск</h2>

<h3>Требования</h3>
<ul>
  <li><b>Python</b> 3.10 или выше.</li>
  <li><b>pip</b> для установки зависимостей.</li>
</ul>

<h3>Шаги</h3>
<ol>
  <li>
    <b>Клонируйте репозиторий:</b>
    <pre><code>git clone https://github.com/DarkSwordman999/django_sprint3.git
cd django_sprint3</code></pre>
  </li>
  <li>
    <b>Создайте и активируйте виртуальное окружение:</b>
    <pre><code>python -m venv venv

# Windows:
venv\Scripts\activate

# macOS / Linux:
source venv/bin/activate</code></pre>
  </li>
  <li>
    <b>Установите зависимости:</b>
    <pre><code>pip install -r requirements.txt</code></pre>
  </li>
  <li>
    <b>Примените миграции:</b>
    <pre><code>python manage.py migrate</code></pre>
  </li>
  <li>
    <b>Загрузите данные из дампа:</b>
    <pre><code>python manage.py loaddata db.json</code></pre>
  </li>
  <li>
    <b>Запустите сервер разработки:</b>
    <pre><code>python manage.py runserver</code></pre>
  </li>
</ol>

<p>После запуска проект доступен по адресу <code>http://127.0.0.1:8000/</code>, админ-панель — <code>http://127.0.0.1:8000/admin/</code>.</p>

<hr>

<h2>🧪 Тестирование</h2>

<p>Тесты запускаются через <b>pytest</b> с плагином <b>pytest-django</b>. Конфигурация — в <code>pytest.ini</code>.</p>

<pre><code>pytest</code></pre>

<p>Что проверяется:</p>
<ul>
  <li><b>Модели:</b> <code>test_category_model.py</code>, <code>test_location_model.py</code>, <code>test_post_model.py</code>.</li>
  <li><b>Вьюхи:</b> <code>test_category_page_views.py</code>, <code>test_post_detail_views.py</code>, <code>test_posts_page_views.py</code>, <code>test_pageapp_views.py</code>.</li>
  <li><b>Маршруты:</b> <code>test_urls.py</code>.</li>
  <li><b>Админка:</b> <code>test_admin_page.py</code>.</li>
  <li><b>Локализация:</b> <code>test_localization.py</code>.</li>
</ul>

<hr>

<h2>🧹 Линтинг</h2>

<p>Код проверяется линтером <b>flake8</b>. Настройки — в файле <code>.flake8</code>.</p>

<pre><code>flake8 .</code></pre>

<hr>

<h2>📄 Лицензия</h2>

<p>Проект распространяется под лицензией, указанной в файле <a href="./LICENSE">LICENSE</a>.</p>

<hr>

<h2>👤 Автор</h2>

<div align="center">

<p><b>DarkSwordman999</b></p>

<a href="https://github.com/DarkSwordman999">
  <img src="https://img.shields.io/badge/GitHub-DarkSwordman999-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
</a>

</div>

<hr>

<div align="center">

<h3>🎓 Проект создан в рамках курса «Python-разработчик» от <a href="https://practicum.yandex.ru/">Яндекс Практикума</a></h3>

<p><i>Учебный проект. Создан в образовательных целях.</i></p>

</div>
