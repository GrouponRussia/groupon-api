Merchant API
============

Акции мерчанта
--------------

### Список всех акций мерчанта

#### GET /merchants/offers.json

Возвращает список всех акций мерчанта.

*Ответ сервера:*

```json
{
  "offers": [
    {
      "deal": {
        "title": "Билет на концерт Evdokimov Show с программой «Я сделал всех!» в Государственном московском театре эстрады",
        "options": [
          {
            "title": "Билет на концерт Evdokimov Show «Я сделал всех!». Партер, 16 ряд, 16-30. 1000 рублей вместо 2000",
            "max_limit": 25,
            "valid_to": "2012-04-26",
            "unlimited": false,
            "bought": 0,
            "discount": 50,
            "usual_price": 2000,
            "price": 1000
          },
          {
            "title": "Билет на концерт Evdokimov Show «Я сделал всех!». Партер, 9 ряд, места 32-44. 1500 рублей вместо 3000",
            "max_limit": 12,
            "valid_to": "2012-04-26",
            "unlimited": false,
            "bought": 0,
            "discount": 50,
            "usual_price": 3000,
            "price": 1500
          }
        ],
        "images": [
          {
            "large_promo": "http://i3.grouponcdn.ru/system/offers/000/077/336/179511/large_promo_jpg.jpg?1334590278",
            "promo": "http://i1.grouponcdn.ru/system/offers/000/077/336/179511/promo_jpg.jpg?1334590278",
            "small": "http://i1.grouponcdn.ru/system/offers/000/077/336/179511/small_jpg.jpg?1334590278"
          }
        ],
        "category": {
          "name": "Развлечения и спорт"
        },
        "multideal": true,
        "sub_category": {
          "name": "NEW Концерт/Шоу"
        },
        "places": [
          {
            "metro_station": null,
            "address": "Берсеневская наб., д. 20/2",
            "longitude": 37.6101855933667,
            "latitude": 55.744220459861
          }
        ]
        },
        "id": 326056,
        "url": "http://groupon.ru/moscow/evdokimovshow"
    },
    # ...
  ]
}
```


### Подробная информация об акции мерчанта

#### GET /merchants/offers/#{id}.json

Возвращает подробную информацию о конкретной акции мерчанта.

**Параметры:**

- ``id`` - ID акции

*Ответ сервера:*

```json
{
  "offer": {
    "deal": {
      "title": "Билет на концерт Evdokimov Show с программой «Я сделал всех!» в Государственном московском театре эстрады",
      "options": [
        {
          "title": "Билет на концерт Evdokimov Show «Я сделал всех!». Партер, 16 ряд, 16-30. 1000 рублей вместо 2000",
          "max_limit": 25,
          "valid_to": "2012-04-26",
          "unlimited": false,
          "bought": 0,
          "discount": 50,
          "usual_price": 2000,
          "price": 1000
        },
        {
          "title": "Билет на концерт Evdokimov Show «Я сделал всех!». Партер, 9 ряд, места 32-44. 1500 рублей вместо 3000",
          "max_limit": 12,
          "valid_to": "2012-04-26",
          "unlimited": false,
          "bought": 0,
          "discount": 50,
          "usual_price": 3000,
          "price": 1500
        }
      ],
      "images": [
        {
          "large_promo": "http://i3.grouponcdn.ru/system/offers/000/077/336/179511/large_promo_jpg.jpg?1334590278",
          "promo": "http://i1.grouponcdn.ru/system/offers/000/077/336/179511/promo_jpg.jpg?1334590278",
          "small": "http://i1.grouponcdn.ru/system/offers/000/077/336/179511/small_jpg.jpg?1334590278"
        }
      ],
      "category": {
        "name": "Развлечения и спорт"
      },
      "multideal": true,
      "sub_category": {
        "name": "NEW Концерт/Шоу"
      },
      "places": [
        {
          "metro_station": null,
          "address": "Берсеневская наб., д. 20/2",
          "longitude": 37.6101855933667,
          "latitude": 55.744220459861
        }
      ]
    },
    "id": 326056,
    "url": "http://groupon.ru/moscow/evdokimovshow"
  }
}
```


### Увеличение лимита купонов по акции

#### PUT /merchants/offers/#{id}/increase_limit.json

Увеличивает лимит купонов конкретной акции на указанное количество.

**Параметры:**

- ``id`` - ID акции
- ``amount`` - количество

*Ответ сервера:*

Сервер вернет статус **200 OK** в случае успешного выполнения. В противном случае вернется сообщение об ошибке.


### Уменьшение лимита купонов по акции

#### PUT /merchants/offers/#{id}/decrease_limit.json

Уменьшает лимит купонов конкретной акции на указанное количество.

**Параметры:**

- ``id`` - ID акции
- ``amount`` - количество

*Ответ сервера:*

Сервер вернет статус **200 OK** в случае успешного выполнения. В противном случае вернется сообщение об ошибке.