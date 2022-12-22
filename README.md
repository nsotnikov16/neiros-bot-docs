# Конструктор чат-ботов

### Логика приложения

## Блоки

### Основной массив elementsApp

```json
"elementsApp": [
  {
    "x": 50,
    "y": 100,
    "component": "Start",
    "id": "1",
    "nextId": "2",
    "data": {
      "elements": []
    }
  },
  {
    "text": "Выбрать первый шаг",
    "x": 450,
    "y": 80,
    "id": "2",
    "component": "ChooseStep"
  },
  {
    "x": 750,
    "y": 80,
    "type": "actions",
    "id": "10",
    "nextId": "4",
    "component": "Step",
    "data": {
      "elements": []
    }
  },
  {
    "x": 750,
    "y": 300,
    "type": "delay",
    "id": "3",
    "component": "Step",
    "data": {
      "elements": [
        {
          "count": 1,
          "type": "seconds"
        }
      ]
    }
  },
  {
    "x": 750,
    "y": 500,
    "type": "conditions",
    "id": "4",
    "component": "Step",
    "data": {
      "elements": [
        {
          "type": "name",
          "name": "",
          "condition": "Совпадает",
          "group": "1"
        },
        {
          "type": "sex",
          "sex": "Мужской",
          "group": "2"
        },
        {
          "type": "tag",
          "tag": "",
          "group": "1"
        }
      ]
    }
  },
  {
    "x": 1150,
    "y": 80,
    "type": "random",
    "id": "5",
    "component": "Step",
    "data": {
      "elements": [
        {
          "name": "A",
          "value": 50,
          "nextId": "3"
        },
        {
          "name": "B",
          "value": 50,
          "nextId": "34"
        }
      ]
    }
  },
  {
    "x": 1150,
    "y": 300,
    "type": "message",
    "component": "Step",
    "id": "34",
    "data": {
      "elements": []
    }
  },
  {
    "x": 100,
    "y": 500,
    "type": "Comment",
    "id": "7",
    "component": "Comment",
    "text": "Какой-то текст"
  }
]
```

### Блок "Добавить триггер"

```json
{
  "x": 50,
  "y": 100,
  "component": "Start",
  "id": "1",
  "nextId": "2",
  "data": {
    "elements": [
      {
        "type": "keywords",
        "keywords": [
          {
            "condition": "Совпадает",
            "value": "123"
          }
        ]
      },
      {
        "type": "quiz",
        "name": "Виджет №1 Квиз",
        "variant": "Вариант Первый1"
      },
      {
        "type": "multibutton",
        "variant": "Мультикнопка №1"
      },
      {
        "type": "subscribers",
        "name": "Виджет №1 Подписчики",
        "variant": "Вариант Первый1"
      },
      {
        "type": "minilanding",
        "name": "Виджет №1 Мини-Лендинг",
        "variant": "Вариант Первый1"
      }
    ]
  }
}
```

| Свойство                             | Тип    | Описание                                          |
| ------------------------------------ | ------ | ------------------------------------------------- |
| x                                    | number | Координата X                                      |
| y                                    | number | Координата Y                                      |
| component                            | string | Название компонента. Для этого блока - "Start"    |
| id                                   | string | ID блока                                          |
| nextId                               | string | ID блока следующего шага                          |
| data.elements                        | array  | Массив содержащих элементов                       |
| data.elements[].type                 | string | Тип содержащего элемента                          |
| data.elements[].keywords             | array  | Массив ключевых слов (только для типа "keywords") |
| data.elements[].keywords[].condition | string | Условие для ключевого слова                       |
| data.elements[].keywords[].value     | string | Значение ключевого слова                          |
| data.elements[].name                 | string | Имя виджета                                       |
| data.elements[].variant              | string | Выбранный вариант виджета / мультикнопки          |

Типы содержащих элементов блока: keywords - По ключевым словам, quiz - виджет квиз, multibutton - мультикнопка, subscribers - виджет подписчики, minilanding - виджет мини-лендинг

[Нужен апи для получения названий и вариантов виджетов, а также мультикнопок?](https://skr.sh/sHWoCZtDkEi)

### Блок "Выбрать шаг"

```json
{
    "x": 450,
    "y": 80,
    "component": "ChooseStep",
    "id": "2",
    "text": "Выбрать первый шаг",
},
```

| Свойство  | Тип    | Описание                                            |
| --------- | ------ | --------------------------------------------------- |
| x         | number | Координата X                                        |
| y         | number | Координата Y                                        |
| component | string | Название компонента. Для этого блока - "ChooseStep" |
| id        | string | ID блока                                            |
| text      | string | Заголовок блока (только при выборе первого шага)    |

### Блок "Действия"

```json
{
  "x": 750,
  "y": 80,
  "type": "actions",
  "id": "10",
  "nextId": "4",
  "component": "Step",
  "data": {
    "elements": [
      {
        "type": "tag",
        "tag": "Какой-то тег"
      },
      {
        "type": "chain",
        "chain": "Какая-то последовательность"
      },
      {
        "type": "talk",
        "talk": "Какой-то пользователь или группа"
      }
    ]
  }
}
```

| Свойство              | Тип    | Описание                                         |
| --------------------- | ------ | ------------------------------------------------ |
| x                     | number | Координата X                                     |
| y                     | number | Координата Y                                     |
| component             | string | Название компонента. Для этого блока - "Step"    |
| id                    | string | ID блока                                         |
| nextId                | string | ID блока следующего шага                         |
| type                  | string | Тип шага. Для этого блока - "actions"            |
| data.elements[].type  | string | Тип действия                                     |
| data.elements[].tag   | string | Значение для типа "tag" (Добавить тег)           |
| data.elements[].chain | string | Значение для типа "chain" (Подписать на цепочку) |
| data.elements[].talk  | string | Значение для типа "talk" (Назначить разговор)    |

[Аналогично апи для получения списка тегов, последовательностей, групп, пользователей](https://skr.sh/sHW4EA7r8cP)

### Блок "Умная задержка"

```json
{
  "x": 750,
  "y": 300,
  "type": "delay",
  "id": "3",
  "component": "Step",
  "nextId": "123",
  "data": {
    "elements": [
      {
        "count": 1,
        "type": "seconds"
      }
    ]
  }
}
```

| Свойство              | Тип    | Описание                                                                |
| --------------------- | ------ | ----------------------------------------------------------------------- |
| x                     | number | Координата X                                                            |
| y                     | number | Координата Y                                                            |
| component             | string | Название компонента. Для этого блока - "Step"                           |
| id                    | string | ID блока                                                                |
| nextId                | string | ID блока следующего шага                                                |
| type                  | string | Тип шага. Для этого блока - "delay"                                     |
| data.elements[].count | number | Количество секунд/минут/часов/суток                                     |
| data.elements[].type  | string | "seconds" - секунды, "minutes" - минуты, "hours" - часы, "days" - сутки |

Содержащий элемент всегда будет только один! Массив data.elements не должен быть пустым. [скрин](https://skr.sh/sHWngpa50la)

### Блок "Условие"

```json
{
  "x": 750,
  "y": 500,
  "type": "conditions",
  "id": "4",
  "component": "Step",
  "nextId": "123",
  "data": {
    "elements": [
      {
        "type": "name",
        "name": "Какое-то имя",
        "condition": "Совпадает",
        "group": "1"
      },
      {
        "type": "sex",
        "sex": "Мужской",
        "group": "2"
      },
      {
        "type": "tag",
        "tag": "Какой-то тег",
        "group": "1"
      }
    ]
  }
}
```

| Свойство                  | Тип    | Описание                                                                                                                    |
| ------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------- |
| x                         | number | Координата X                                                                                                                |
| y                         | number | Координата Y                                                                                                                |
| component                 | string | Название компонента. Для этого блока - "Step"                                                                               |
| id                        | string | ID блока                                                                                                                    |
| nextId                    | string | ID блока следующего шага, ДЛЯ КОНТАКТОВ БЕЗ УСЛОВИЙ                                                                         |
| type                      | string | Тип шага. Для этого блока - "conditions"                                                                                    |
| data.elements[].type      | string | Тип условия ("name" - имя, "sex" - пол, "tag" - тег)                                                                        |
| data.elements[].name      | string | Значение имени. Для типа "name"                                                                                             |
| data.elements[].condition | string | Условие имени. Для типа "name"                                                                                              |
| data.elements[].sex       | string | Выбранный пол. Для типа "sex"                                                                                               |
| data.elements[].tag       | string | Выбранный тег. Для типа "tag"                                                                                               |
| data.elements[].group     | string | Группа, к которой относится условие (должно быть у каждого условия) (по возрастанию 1, 2, 3 ...)                            |
| data.elements[].nextId    | string | ID блока следующего шага для одной группы условий. Должно быть прописано в каждом условии, если в группе есть следующий шаг |

[Получение тегов](https://skr.sh/sHWDMPXUQsv)

### Блок "Случайный выбор"

```json
{
  "x": 1150,
  "y": 80,
  "type": "random",
  "id": "5",
  "component": "Step",
  "data": {
    "elements": [
      {
        "name": "A",
        "value": 50,
        "nextId": "3"
      },
      {
        "name": "B",
        "value": 50,
        "nextId": "34"
      }
    ]
  }
}
```

| Свойство               | Тип    | Описание                                            |
| ---------------------- | ------ | --------------------------------------------------- |
| x                      | number | Координата X                                        |
| y                      | number | Координата Y                                        |
| component              | string | Название компонента. Для этого блока - "Step"       |
| id                     | string | ID блока                                            |
| type                   | string | Тип шага. Для этого блока - "random"                |
| data.elements[].name   | string | Имя вариации тестирования                           |
| data.elements[].value  | number | Процент вероятности                                 |
| data.elements[].nextId | string | ID блока следующего шага для определенного варианта |

Минимальное количество элементов data.elements - 2. Максимальное - 5.

Полное процент вероятности - 100. Соответственно для каждой вариации будет приходить процент 100 / n, где n - количество вариаций

### Блок "Отправить сообщение"

```json
{
  "x": 1150,
  "y": 300,
  "type": "message",
  "component": "Step",
  "id": "34",
  "nextId": "315",
  "data": {
    "elements": [
      {
        "type": "text",
        "text": "Какой-то текст",
        "buttons": [
          {
            "id": "1234",
            "title": "Кнопка №1",
            "type": "url",
            "url": "https://test.ru"
          },
          {
            "id": "123",
            "title": "Кнопка №2",
            "type": "message",
            "nextId": "124124"
          }
        ]
      },
      {
        "type": "img",
        "src": ""
      },
      {
        "type": "download",
        "src": "",
        "name": ""
      },
      {
        "type": "delay",
        "sec": 3
      },
      {
        "type": "link",
        "url": ""
      },
      {
        "type": "video",
        "src": "",
        "name": ""
      }
    ]
  }
}
```

| Свойство                         | Тип    | Описание                                                                 |
| -------------------------------- | ------ | ------------------------------------------------------------------------ |
| x                                | number | Координата X                                                             |
| y                                | number | Координата Y                                                             |
| component                        | string | Название компонента. Для этого блока - "Step"                            |
| id                               | string | ID блока                                                                 |
| type                             | string | Тип шага. Для этого блока - "message"                                    |
| nextId                           | string | ID блока следующего шага                                                 |
| data.elements[].type             | string | Тип содержащего элемента                                                 |
| data.elements[].buttons          | array  | Массив кнопок для типа "text"                                            |
| data.elements[].buttons[].id     | string | ID кнопки                                                                |
| data.elements[].buttons[].title  | string | Заголовок кнопки                                                         |
| data.elements[].buttons[].type   | string | Тип кнопки (url - ссылка, message - сообщение)                           |
| data.elements[].buttons[].url    | string | URL кнопки для типа кнопки "url"                                         |
| data.elements[].buttons[].nextId | string | ID блока следующего шага для кнопки! [скрин](https://skr.sh/sHWEk9n3HkR) |
| data.elements[].text             | string | Текст сообщения для элемента type == "text"                              |
| data.elements[].src              | string | Путь к файлу/картинке для элементов типа img, download, video            |
| data.elements[].name             | string | Имя файла для элементов типа                                             |
| data.elements[].url              | string | URL для элемента типа "link"                                             |
| data.elements[].sec              | number | Количество секунд для типа "delay"                                       |

data.elements[].type : text - текст, img - изображение, download - файл, delay - задержка, link - ссылка, video - видео

С добавленными файлами надо будет обсудить загрузку на сервер

### Блок "Комментарий"

```json
{
  "x": 100,
  "y": 500,
  "type": "comment",
  "id": "7",
  "component": "Comment",
  "text": "Какой-то текст"
}
```

| Свойство  | Тип    | Описание                                         |
| --------- | ------ | ------------------------------------------------ |
| x         | number | Координата X                                     |
| y         | number | Координата Y                                     |
| component | string | Название компонента. Для этого блока - "Comment" |
| id        | string | ID блока                                         |
| type      | string | Для этого блока - "comment"                      |
| text      | string | Текст комментария                                |
