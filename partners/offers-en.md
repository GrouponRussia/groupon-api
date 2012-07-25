Partner API
===========

Deals
-----

### List of all deals in specific city

#### GET /cities/#{city_id}/offers.json

Returns list of all deals in specific city.

**Parameters:**

- ``city_id`` - city ID

*Response:*

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


### Detailed information about specific deal.

#### GET /offers/#{id}.json

Returns detailed information about specific deal.

**Parameters:**

- ``id`` - deal ID

*Response:*

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


Response fields description:
---------------------------------

- ``deal`` - deal information
    - ``multideal`` - is it a "multi-deal"?
    - ``options`` - deal options
        - ``id`` - deal option ID
        - ``title`` - deal option title
        - ``price`` - coupon price
        - ``bought`` - amount of sold coupons
        - ``usual_price`` - usual price (without discount)
        - ``discount`` - discount (in percentage)
        - ``max_limit`` - maximum possible amount of coupons to be sold
        - ``unlimited`` - is amount of coupons limited?
        - ``valid_to`` - coupon expiration date
    - ``category`` - category
        - ``name`` - category name
    - ``title`` - deal title
    - ``places`` - deal venues
        - ``address`` - venue address
        - ``latitude`` - latitude coordinate
        - ``longitude`` - longitude coordinate
        - ``metro_station`` - closest metro station
            - ``name`` - metro station name
            - ``latitude`` - latitude coordinate
            - ``longitude`` - longitude coordinate
    - ``images`` - deal images
        - ``promo`` - normal size
        - ``large_promo`` - large size
        - ``small`` - small size
    - ``sub_category`` - subcategory
        - ``name`` - subcategory name
    - ``merchant`` - merchant
        - ``name`` - merchant name
- ``url`` - deal url
- ``id`` - deal ID