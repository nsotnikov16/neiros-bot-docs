# Конструктор чат-ботов Neiros
Логика приложения чат-ботов

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
| id                                   | string | ID                                                |
| data.elements                        | array  | Массив содержащих элементов                       |
| data.elements[].type                 | string | Тип содержащего элемента                          |
| data.elements[].keywords             | array  | Массив ключевых слов (только для типа "keywords") |
| data.elements[].keywords[].condition | string | Условие для ключевого слова                       |
| data.elements[].keywords[].value     | string | Значение ключевого слова                          |
| data.elements[].name                 | string | Имя виджета                                       |
| data.elements[].variant              | string | Выбранный вариант виджета / мультикнопки          |

Типы содержащих элементов блока: keywords - По ключевым словам, quiz - виджет квиз, multibutton - мультикнопка, subscribers - виджет подписчики, minilanding - виджет мини-лендинг

___Сюда написать про получение названий и вариантов виджетов + скрины___
