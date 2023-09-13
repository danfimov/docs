# Устранение ошибок с HTTP 499 при работе облачной функции или serverless-контейнера


## Описание проблемы {#issue-description}

* В журнале работы облачной функции или serverless-контейнера отображаются сообщения вида `Error: Code 499 Message: request cancelled`

## Решение {#issue-resolution}

Такое поведение происходит когда функция разрывает соединение до того, как ей был отправлен ответ со стороны сервера. Например, по истечении таймаута на один запрос в функции, запрос отменяется (поэтому в логах отображается строка «Request cancelled»).

Выполните следующие действия для решения проблемы:

1. Добавьте логирование в код функции. Мы подготовиили пример настройки логирования работы облачных функций на Python [в документации](../../../functions/lang/python/logging.md);

2. Переработайте логику работы функции. Например, хорошей практикой является, когда разные методы API используются разными сервисными аккаунтами. В случае, если по каким-то причинам (система безопасности, устаревание токена, и т.д..) у аккаунта, от чьего имени происходит обращение к API, пропадёт доступ, то проблемы возникнут лишь с одним или несколькими методами функции, а не со всей функцией сразу. Кроме того, такой подход поможет упростить диагностику функции, если с ней возникнут в будущем и другие проблемы.

## Если проблема осталась {#if-issue-still-persists}

Если вышеописанные действия не помогли решить проблему, [создайте запрос в техническую поддержку](https://console.cloud.yandex.ru/support?section=contact).
При создании запроса укажите следующую информацию:

1. Идентификатор облачной функции или serverless-контейнера;
2. Содержимое журнала работы облачной функции иди serverless-контейнера (журналы работы функции доступны в разделе **Логи** на странице функции в Консоли управления).