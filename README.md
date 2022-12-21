# Конструктор чат-ботов Neiros
Логика приложения чат-ботов

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
