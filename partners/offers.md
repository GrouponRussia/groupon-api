Partner API
===========

Акции
-----

### Список всех акций по городу

#### GET /cities/#{city_id}/offers.json

Возвращает список всех доступных акций по конкретному городу.

**Параметры:**

- ``city_id`` - ID города

*Ответ сервера:*

```json
{
  "offers": [
    {
      "deal": {
        "title": "Билет на концерт Evdokimov Show с программой «Я сделал всех!» в Государственном московском театре эстрады",
        "options": [
          {
            "title": "Билет на концерт Evdokimov Show «Я сделал всех!». Партер, 16 ряд, 16-30. 1000 рублей вместо 2000"
            "max_limit": 25,
            "valid_to": "2012-04-26",
            "unlimited": false,
            "bought": 0,
            "discount": 50,
            "usual_price": 2000,
            "price": 1000
          },
          {
            "title": "Билет на концерт Evdokimov Show «Я сделал всех!». Партер, 9 ряд, места 32-44. 1500 рублей вместо 3000"
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


### Подробная информация об акции

#### GET /offers/#{id}.json

Возвращает подробную информацию о конкретной акции.

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
          "title": "Билет на концерт Evdokimov Show «Я сделал всех!». Партер, 16 ряд, 16-30. 1000 рублей вместо 2000"
          "max_limit": 25,
          "valid_to": "2012-04-26",
          "unlimited": false,
          "bought": 0,
          "discount": 50,
          "usual_price": 2000,
          "price": 1000
        },
        {
          "title": "Билет на концерт Evdokimov Show «Я сделал всех!». Партер, 9 ряд, места 32-44. 1500 рублей вместо 3000"
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