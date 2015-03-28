---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---
# Установка и запуск
Минимальные весии:

```shell


git clone repo
npm install
# build and watch changes
webpack -w -colors -progres
# run websocket server
php ./server/websocket.php
# Download ligtHttpd and set document root to polarOS/public/
```
- `PHP >= 5.4`
- `NodeJS >= 0.12`

- Клонировать репозиторий link.
- Установить пакеты для nodejs
- Запустить сборку если необходмо внести изменения
- Запустить wesocket сервер, работает только с внешнего ip, поэому необходимо открыть порт в настойках firewall и роутера, по умолчанию `8181`.


# Запуск тестов

```shell
cd PROJECT_ROOT
webpack-dev-server --config mocha.js 
open http://YOUR_IP:8080/test/test.html#
```

[http://localhost:8080/test/test.html](http://localhost:8080/test/test.html).
Внешний IP нужен для работы websocket.
Для авто замены измененев в файлах нужно добавить флаг `--hot`

# Apps API

## Идеология
```javascript
Config.get('windows.active');
```
Для указания вложености в настройках,правах пиложений и событиях используются точки.
Например что-бы получить активное окно:

```javascript
Helper.on('user.background', callback);
```

Что-бы подписатся на событие смены обоев.

```json
{
"permissions": [
  "apps",
  "user.background",
]
}
```

Для этого необходимо указать права.
apps дает доступ к событиям и данным apps*.

## HTTP Request

`GET http://example.com/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>
