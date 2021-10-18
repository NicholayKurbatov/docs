# Получить все записи по задаче

Запрос позволяет получить данные о времени, затраченном на выполнение задачи.

## Формат запроса {#section_ssn_dyb_ffb}

Чтобы получить записи о затраченном на задачу времени, используйте HTTP-запрос с методом `GET`:

```json
GET /{{ ver }}/issues/<issue-id>/worklog
Host: {{ host }}
Authorization: OAuth <токен>
{{ org-id }}
```

{% include [headings](../../../_includes/tracker/api/headings.md) %}

{% cut "Ресурс" %}

Параметр | Описание | Тип данных
--- | --- | ---
\<issues-id\> | Идентификатор или ключ задачи. | Строка

{% endcut %}

## Формат ответа {#section_egr_qcc_ffb}

{% list tabs %}

- Запрос выполнен успешно

    {% include [answer-200](../../../_includes/tracker/api/answer-200.md) %} 

     Тело ответа содержит JSON-массив с записями о времени, затраченном на выполнение задачи.

    ```json
    [
      {
      "self": "{{ host }}/v2/issues/TEST-324/worklog/1",
      "id": 1,
      "version": 1402121720882,
      "issue": {
        "self": "{{ host }}/v2/issues/TEST-324",
        "id": "515ec9eae4b09cfa984e2047",
        "key": "TEST-324",
        "display": "важная задача"
        },
      "comment": "важный комментарий",
      "createdBy": {
        "self": "{{ host }}/v2/users/1120000000014909",
        "id": "veikus",
        "display": "Artem Veikus"
        },
      "updatedBy": {
        "self": "{{ host }}/v2/users/1120000000014909",
        "id": "veikus",
        "display": "Artem Veikus"
        },
      "createdAt": "2021-09-28T08:42:06.258+0000",
      "updatedAt": "2021-09-28T08:42:06.258+0000",
      "start": "2021-09-21T10:30:00.000+0000",
      "duration": "P3W"
      },
      ...
    ]
    ```

    {% cut "Параметры ответа" %}

    Параметр | Описание | Тип данных
    -------- | -------- | ----------
    self | Адрес ресурса API, который содержит запись о затраченном времени. | Строка
    id | Идентификатор записи о затраченном времени. | Строка
    version | Версия записи. Каждое изменение записи увеличивает номер версии. | Строка
    [issue](#issue) | Блок с информацией о задаче. | Объект
    comment | Текст комментария к записи. Комментарий сохранится в Отчёте по затратам времени. | Строка
    [createdBy](#createdBy) | Объект с информацией о создателе записи. | Объект
    [updatedBy](#updatedBy) | Объект с информацией о пользователе, внесшем изменение в запись. | Объект
    createdAt | Дата и время создания записи в формате: ```YYYY-MM-DDThh:mm:ss.sss±hhmm``` | Строка
    updatedAt | Дата и время обновления записи в формате: ```YYYY-MM-DDThh:mm:ss.sss±hhmm``` | Строка
    start | Дата и время начала работы над задачей в формате: ```YYYY-MM-DDThh:mm:ss.sss±hhmm``` | Строка
    duration | Затраченное время в формате ```PnYnMnDTnHnMnS, PnW``` в соответствии с [ISO 8601]({{ link-iso-8601 }}). | Строка

    **Поля объекта** `issue` {#issue}

    Параметр | Описание | Тип данных
    -------- | -------- | ----------
    self | Адрес ресурса API, который содержит информацию о задаче. | Строка
    id | Идентификатор задачи. | Строка
    key | Ключ задачи. | Строка
    display | Отображаемое название задачи. | Строка

    **Поля объекта** `createdBy` {#createdBy}

    Параметр | Описание | Тип данных
    -------- | -------- | ----------
    self | Адрес ресурса API, который содержит информацию о пользователе. | Строка
    id | Идентификатор пользователя. | Строка
    display | Отображаемое имя пользователя. | Строка

    **Поля объекта** `updatedBy` {#updatedBy}

    Параметр | Описание | Тип данных
    -------- | -------- | ----------
    self | Адрес ресурса API, который содержит информацию о пользователе. | Строка
    id | Идентификатор пользователя. | Строка
    display | Отображаемое имя пользователя. | Строка

    {% endcut %}

- Запрос выполнен с ошибкой

    Если запрос не был успешно обработан, ответное сообщение содержит информацию о возникших ошибках:

    {% include [error](../../../_includes/tracker/api/answer-error-400.md) %}

    {% include [error](../../../_includes/tracker/api/answer-error-403.md) %}

    {% include [error](../../../_includes/tracker/api/answer-error-404.md) %}

    {% include [error](../../../_includes/tracker/api/answer-error-500.md) %}

    {% include [error](../../../_includes/tracker/api/answer-error-503.md) %}

{% endlist %}