Reseller API
============

Купоны
------

### Список всех купленных купонов

#### GET /resellers/coupons.json

Возвращает список всех купленных реселлером купонов.

*Ответ сервера:*

```json
{
  "orders": [
    {
      "description_permalink": "cultservmoscow3-1",
      "id": 5152036,
      "offer_id": 12345,
      "activated": false,
      "coupon": "1234567/12345"
    }
  ]
}
```


### Подробная информация о купленном купоне

#### GET /resellers/coupons/#{id}.json

Возвращает подробную информацию о конкретном купленным реселлером купоне.

**Параметры:**

- ``id`` - ID купона

*Ответ сервера:*

```json
{
  "order": {
    "description_permalink": "cultservmoscow3-1",
    "id": 5152036,
    "offer_id": 12345,
    "activated": false,
    "coupon": "1234567/12345"
  }
}
```


### Покупка купона

#### POST /resellers/coupons.json

Покупает купон и возвращает подробную информацию о нем.

**Параметры:**

- ``option_id`` - ID акции (или варианта акции, если акция - multideal)

*Ответ сервера:*

```json
{
  "order": {
    "description_permalink": "cultservmoscow3-1",
    "id": 5152036,
    "offer_id": 12345,
    "activated": false,
    "coupon": "1234567/12345"
  }
}
```