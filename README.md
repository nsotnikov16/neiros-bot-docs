# Блоки

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

**_Сюда написать про получение названий и вариантов виджетов + скрины_**

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

**_Сюда написать про получение списков тегов, последовательностей, групп, пользователей + скрины_**

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
| data.elements[].count | string | Количество секунд/минут/часов/суток                                     |
| data.elements[].type  | string | "seconds" - секунды, "minutes" - минуты, "hours" - часы, "days" - сутки |

Содержащий элемент всегда будет только один! Массив data.elements не должен быть пустым.

**_Сюда скрины_**
