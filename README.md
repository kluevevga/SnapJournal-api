# SnapJournal(api) 📡

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue?style=for-the-badge&labelColor=333333&logo=python&logoColor=white)](https://www.python.org/)
[![flake8](https://img.shields.io/badge/code%20style-flake8-blue?style=for-the-badge&labelColor=333333)](https://flake8.pycqa.org/)
[![Django](https://img.shields.io/badge/Django-3.2.16-blue?style=for-the-badge&labelColor=333333&logo=django&logoColor=white&color=black)](https://www.djangoproject.com/)
[![Pillow](https://img.shields.io/badge/Pillow-9.3.0-blue?style=for-the-badge&labelColor=333333&logo=pillow&logoColor=white&color=black)](https://pillow.readthedocs.io/en/stable/)
[![DRF](https://img.shields.io/badge/django--rest--framework-3.12.4-blue?style=for-the-badge&labelColor=008B76&logo=django&logoColor=white&color=black)](https://www.django-rest-framework.org/)
[![SimpleJWT](https://img.shields.io/badge/simplejwt-4.7.2-blue?style=for-the-badge&labelColor=008B76&logo=django&logoColor=white&color=black)](https://github.com/davesque/django-rest-framework-simplejwt)
[![PyJWT](https://img.shields.io/badge/PyJWT-2.1.0-blue?style=for-the-badge&labelColor=00A7D0&logo=python&logoColor=white&color=black)](https://github.com/jpadilla/pyjwt)
[![Djoser](https://img.shields.io/badge/djoser-2.1.0-blue?style=for-the-badge&labelColor=3498DB&logo=django&logoColor=white&color=black)](https://github.com/sunscrapers/djoser)
[![Лицензия](https://img.shields.io/github/license/kluevevga/SnapJournal-api?color=blue&style=for-the-badge&labelColor=black&logo=github)](https://github.com/kluevevga/SnapJournal-api/blob/master/LICENSE)
[![Размер кода](https://img.shields.io/github/languages/code-size/kluevevga/SnapJournal-api?style=for-the-badge&labelColor=black&logo=github)](https://github.com/kluevevga/SnapJournal-api)

## О проекте "SnapJournal" 📖

Проект "SnapJournal" - это уникальная платформа для ведения личных микроблогов и журналов. Основанный на мощном
фреймворке Django-rest-framework, "SnapJournal" предоставляет REST API backend сервис, который позволяет пользователям
создавать и управлять своими текстовыми и визуальными записями. "SnapJournal" разработан с акцентом на интуитивном
интерфейсе и легкости в использовании, а также предоставляет возможность добавлять как текстовые, так и мультимедийные
записи. Это идеальное решение для тех, кто ищет место, где можно свободно и креативно делиться своими мыслями и идеями.

# SnapJournal(api) 🔌

SnapJournal(api) - это REST API сервис, который расширяет функциональность платформы SnapJournal, позволяя пользователям
создавать и управлять своим контентом, отправляя CRUD запросы в формате JSON и таким образом взаимодействуя с базой
данных "SnapJournal." Это предоставляет пользователям мощный инструмент для управления их контентом в системе.

### 🔑 Ключевые особенности

- **🔐 Авторизация и безопасность**: В проекте реализована надежная система аутентификации на основе JWT токенов,
  обеспечивая безопасное взаимодействие пользователей с платформой.

- **📖 Документация**: API проекта снабжен документацией в формате OpenAPI, что делает его легким в использовании и
  понимании.

- **🔒 Защита данных**: Для обеспечения целостности и безопасности данных, проект использует сериализаторы, которые
  фильтруют и проверяют информацию, предотвращая внесение некорректных данных в систему. Для хранения данных
  используется SQLite база данных, а использование Django ORM обеспечивает дополнительную безопасность от SQL инъекций.

- **🛠️ Функциональность API**: Аутентифицированным пользователям разрешено добавление постов и комментариев, а также
  изменение и удаление своего контента; в остальных случаях доступ предоставляется только для чтения.
  Эндпоинт `/follow/` доступен только для аутентифицированных пользователей.

Этот проект, "SnapJournal(api)," обеспечивает мощное и безопасное API для управления данными и взаимодействия с
контентом пользователей и является важной частью платформы "SnapJournal."

## 👷‍♂️ Установка 🏗️

### Клонирование проекта

Для начала, клонируйте проект "SnapJournal-api" с помощью следующей команды:

```shell
git clone https://github.com/kluevevga/SnapJournal-api.git
```

### Установка виртуальной среды 🧟‍♂️

Далее создайте виртуальное окружение:

```shell
python3 -m venv venv
```

### Активация виртуальной среды

Активируйте виртуальное окружение в зависимости от вашей операционной системы:

**🪟 Windows (PowerShell):**

```shell
venv\Scripts\Activate
```

**🪟 Windows (Git Bash):**

```shell
source venv/Scripts/activate
```

**🐧 Linux (Bash):**

```shell
source venv/bin/activate
```

### Установка зависимостей 📦 

Установите необходимые зависимости из файла `requirements.txt`:

```shell
pip3 install -r requirements.txt
```

## Запуск сервера 🤖

Перейдите в папку с проектом:

```shell
cd SnapJournal-api/
```

Выполните миграции:

```shell
python3 manage.py migrate
```

Запустите сервер:

```shell
py manage.py runserver
```

## Диаграммы эндпоинтов 📊

Здесь представлены диаграммы эндпоинтов для API проекта "SnapJournal-api":

> **Общий вид**

```mermaid
graph TD;
api/v1/ --> posts/;
api/v1/ --> groups/;
api/v1/ --> follow/;
```

> **Эндпоинт posts/**

```mermaid
graph TD;
posts/ --> GET-POST;
posts/ -->id/;
id/ --> GET-PUT-PATCH-DELETE;
```

> **Эндпоинт post -> comments/**

```mermaid
graph TD;
api/v1/posts/ --> post_id/;
post_id/ --> comments/;
comments/ --> GET-POST
comments/ --> id/
id/ --> GET-PUT-PATCH-DELETE;
```

> **Эндпоинт groups/**

```mermaid
graph TD;
groups/ --> GET;
groups/ --> id/;
id/ --> /(GET);
```

> **Эндпоинт follow/**

```mermaid
graph TD;
follow/ --> GET;
follow/ --> POST;
```

## Лицензия 📜

Этот проект распространяется под лицензией `MIT`. Дополнительную информацию можно найти
в [LICENSE](https://github.com/kluevevga/SnapJournal-api/blob/master/LICENSE).
