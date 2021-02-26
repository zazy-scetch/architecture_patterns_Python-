# architecture_patterns
Набор домашних заданий к курсу GeekBrains "Архитектура и шаблоны проектирования на Python"

## Урок 1. Паттерны web-представления
`uwsgi --http :8000 --wsgi-file fwsgi.py`
0. Создать репозиторий для нового проекта (gitlab, github, ...)
1. С помощью `uwsgi` или `gunicorn` запустить пример `simple_wsgi.py`, проверить что он работает (Эти библиотеки работают на linux системах, документацию по ним можно найти в дополнительных материалах)
2. Написать свой wsgi фреймворк использую паттерны `page controller` и `front controller`.  
    Описание работы фреймворка:  
    * возможность отвечать на get запросы пользователя (код ответа + html страница)  
    * для разных url - адресов отвечать разными страницами  
    * page controller - возможность без изменения фреймворка добавить view для обработки нового адреса  
    * front controller - возможность без изменения фреймворка вносить изменения в обработку всех запросов  
3. Реализовать рендеринг страниц с помощью шаблонизатора `jinja2`. Документацию по этой библиотеке можно найти в дополнительных материалах
4. Добавить любый полезный функционал в фреймворк, например обработку наличия (отсутствия) слеша в конце адреса, ...
5. Добавить для демонстрации 2 любые разные страницы (например главная и about или любые другие)
6. Сдать дз в виде ссылки на репозиторий
7. В readme указать пример как запустить фреймворк с помощью uwsgi и/или gunicorn

## Урок 2. Архитектура python-приложений
1. Добавить в свой wsgi-фреймворк возможность обработки post-запроса
2. Добавить в свой wsgi-фреймворк возможность получения данных из post запроса
3. Дополнительно можно добавить возможность получения данных из get запроса
4. В проект добавить страницу контактов на которой пользователь может отправить нам сообщение (пользователь вводит тему сообщения, его текст, свой email)
5. После отправки реализовать сохранение сообщения в файл, либо вывести сообщение в терминал (базу данных пока не используем)

## Урок 3. Принципы проектирования
1. Внести изменения в wsgi-фреймворк, которые позволят использовать механизм наследования и включения шаблонов
2. Создать базовый шаблон для всех страниц сайта
3. Если нужно создать один или несколько включенных шаблонов
4. Добавить на сайт меню, которое будет отображаться на всех страницах
5. Улучшить имеющиеся страницы с использованием базовых и включенных шаблонов
6. Проверить что фреймворк готов для дальнейшего использования при желании добавить какой либо полезный функционал

## Урок 4. Порождающие паттерны

1. Добавить следующий функционал:
    * Создание категории курсов
    * Вывод списка категорий
    * Создание курса
    * Вывод списка курсов
2. Далее можно сделать всё или одно на выбор, применив при этом один из порождающих паттернов, либо аргументировать почему данные паттерны не были использованы:
    * На сайте могут быть курсы разных видов: офлайн (в живую) курсы (для них указывается адрес проведения) и онлайн курсы (вебинары), для них указывается вебинарная система. Также известно что в будущем могут добавиться новые виды курсов
    * Реализовать простой логгер (не используя сторонние библиотеки). У логгера есть имя. Логгер с одним и тем же именем пишет данные в один и тот же файл, а с другим именем в другой
    * Реализовать страницу для копирования уже существующего курса (Для того чтобы снова с нуля не создавать курс, а скопировать существующий и немного отредактировать)
