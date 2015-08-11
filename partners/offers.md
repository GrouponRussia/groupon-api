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
        "mobile_title": "Кафе Medoc",
        "delivery_title": "Ужин в кафе европейской кухни. <b>Скидка&nbsp;до&nbsp;49%</b>",
        "age_restriction": 18,
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
        "merchant": {
          "name": "Интернет-магазин Best Nespresso"
        },
        "category": {
          "name": "Развлечения и спорт"
        },
        "multideal": true,
        "active_to": "2014-05-12",
        "sub_category": {
          "name": "NEW Концерт/Шоу"
        },
        "places": [
          {
            "title": "Гончарная улица",
            "address": "Ул. Гончарная, д. 38",
             "metro_station": {
               "name": "Таганская",
               "latitude": 55.7404243,
               "longitude": 37.6533613
             },
             "latitude": 55.740887,
             "longitude": 37.650621,
             "phone": "+7 926 153-90-65",
             "opening_hours": "пн. — пт. 10:00 — 20:00"
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
      "mobile_title": "Кафе Medoc",
      "delivery_title": "Ужин в кафе европейской кухни. <b>Скидка&nbsp;до&nbsp;49%</b>",
      "age_restriction": 18,
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
      "merchant": {
        "name": "Интернет-магазин Best Nespresso"
      },
      "category": {
        "name": "Развлечения и спорт"
      },
      "multideal": true,
      "active_to": "2014-05-12",
      "sub_category": {
        "name": "NEW Концерт/Шоу"
      },
      "places": [
        {
            "title": "Гончарная улица",
            "address": "Ул. Гончарная, д. 38",
             "metro_station": {
               "name": "Таганская",
               "latitude": 55.7404243,
               "longitude": 37.6533613
             },
             "latitude": 55.740887,
             "longitude": 37.650621,
             "phone": "+7 926 153-90-65",
             "opening_hours": "пн. — пт. 10:00 — 20:00"
        }
      ]
    },
    "id": 326056,
    "url": "http://groupon.ru/moscow/evdokimovshow"
  }
}
```


Описание полей из ответа сервера:
---------------------------------

- ``deal`` - описание акции
    - ``multideal`` - является ли акция мультидилом?
    - ``active_to`` - дата последнего размещения
    - ``options`` - варианты акции
        - ``id`` - ID варианта акции
        - ``title`` - название варианта акции
        - ``price`` - цена купона
        - ``bought`` - количество проданных купонов
        - ``usual_price`` - обычная цена
        - ``discount`` - скидка (в процентах)
        - ``max_limit`` - максимально возможное количество проданных купонов
        - ``unlimited`` - ограничено ли количество купонов?
        - ``valid_to`` - срок действия купона
    - ``category`` - категория
        - ``name`` - название категории
    - ``title`` - название акции
    - ``mobile_title`` -  заголовок для мобильной версии сайта
    - ``delivery_title`` - заголовок для рассылок
    - ``age_restriction`` - ограничение в возрасте
    - ``places`` - список мест проведения акции
        - ``title`` - название места
        - ``address`` - адрес места проведения
        - ``latitude`` - широта
        - ``longitude`` - долгота
        - ``phone`` - телефон
        - ``opening_hours`` - время работы
        - ``metro_station`` - станция метро
            - ``name`` - название станции метро
            - ``latitude`` - широта
            - ``longitude`` - долгота

    - ``images`` - список картинок к акции
        - ``promo`` - стандартный размер
        - ``large_promo`` - большой размер
        - ``small`` - маленький размер
    - ``sub_category`` - подкатегория
        - ``name`` - название подкатегории
    - ``merchant`` - мерчант
        - ``name`` - название мерчанта
- ``url`` - ссылка на акцию
- ``id`` - ID акции
