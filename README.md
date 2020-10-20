# «Дела в Порядке»

**Используемые технологии:** PHP 7.0+ / MySQL 5.7+.

«Дела в порядке» — это веб приложение для удобного ведения списка дел. Сервис помогает пользователям не забывать о предстоящих важных событиях и задачах.

После создания аккаунта пользователь может начать вносить свои задачи, деля их по проектам и указывая сроки.

Основные сценарии использования сайта:

* создание проектов;
* добавление новых задач с привязкой к проекту и дате;
* просмотр дел на ближайшие дни;
* получение уведомлений о предстоящих задачах.


## Быстрый старт

Данные для доступа к БД MySQL: `root / root`.

Для полноценной работы с MySQL может потребоваться включить расширение mysqli в php.ini и доставить необходимые драйвера.

Готовая схема БД находится в корне проекта (`schema.sql`).

Чтобы создать трех тестовых пользователей со списком задач для одного из них (Игнат), необходимо выполнить строки с 1-й по 28-ю в файле `queries.sql`.

**Данные для авторизации на сайте:**

<table><thead><tr><th>Email</th><th>Пароль</th></tr></thead><tbody><tr><td>ignat.v@gmail.com</td><td>ug0GdVMi</td></tr><tr><td>kitty_93@li.ru</td><td>daecNazD</td></tr><tr><td>warrior07@mail.ru</td><td>oixb3aL8</td></tr></tbody></table>


## Реализованные возможности

* Регистрация новых пользователей.
* Авторизация зарегистрированных пользователей.
* Создание новых задач, их привязка к проекту и сопутствующие действия: пометка задачи как выполненной, удаление.
* Сортировка и фильтрация задач по следующим критериям: все, выполненные/невыполненные, задачи на сегодня, задачи на завтра, просроченные задачи.
* Поиск задач по фрагменту названия.
* Создание новых проектов.
* Серверная валидация всех форм обратной связи с выведением информации о допущенных пользователем ошибках.
* Email-уведомления о предстоящих задачах за час до истечения срока их выполнения.


## Список экранов

* Главная страница (боковое меню и список задач).
* Приветственная страница (экран по умолчанию, который видят незарегистрированные/неавторизованные пользователи).
* Регистрация аккаунта.
* Авторизация на сайте (модальное окно).
* Добавление проекта (модальное окно).
* Добавление задачи (модальное окно).


## Основные сущности

### Проект

Состоит только из названия. Каждая задача может быть привязана к одному из проектов. Проект имеет связь с пользователем, который его создал.

### Задача

Центральная сущность всего сайта. 

**Поля:**

* дата создания;
* дата выполнения;
* название;
* вложение;
* срок выполнения.

**Связи:**

* автор — пользователь, создавший задачу;
* проект — проект, к которому принадлежит задача.

### Пользователь

Представляет зарегистрированного пользователя.

**Поля:**

* дата регистрации;
* email;
* имя;
* пароль (обязательно в захэшированном виде);
* контактная информация.

**Связи:**

* созданные задачи;
* созданные проекты.


## Роли пользователей

Сайт могут использовать только зарегистрированные пользователи.

Анонимный пользователь всегда видит только страницу входа на сайт.

---

<a href="https://htmlacademy.ru/intensive/adaptive"><img align="left" width="50" height="50" alt="HTML Academy" src="https://up.htmlacademy.ru/static/img/intensive/adaptive/logo-for-github.svg"></a>

Репозиторий создан для обучения на интенсивном онлайн‑курсе «[Базовый PHP](https://htmlacademy.ru/intensive/php)» от [HTML Academy](https://htmlacademy.ru).
