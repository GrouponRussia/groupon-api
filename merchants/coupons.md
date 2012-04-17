Merchant API
============

Купоны мерчанта
---------------

### Список всех купонов мерчанта

#### GET /merchants/coupons.json

Возвращает список всех купонов мерчанта.

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


### Список всех купонов мерчанта по акции

#### GET /merchants/offers/#{offer_id}/coupons.json

Возвращает список всех купонов мерчанта по конкретной акции.

**Параметры:**

- ``offer_id`` - ID акции

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


### Подробная информация о купоне мерчанта

#### GET /merchants/coupons/#{id}.json

Возвращает подробную информацию о конкретном купоне мерчанта.

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


### Поиск купона мерчанта

#### GET /merchants/coupons/search.json

Возвращает подробную информацию о купоне мерчанта, если таковой был найден.

**Параметры:**

- ``coupon`` - код купона

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


### Активация купона мерчанта

#### PUT /merchants/coupons/#{id}.json/activate

Активирует конкретный купон.

**Параметры:**

- ``id`` - ID купона
- ``security`` - код безопастности купона

*Ответ сервера:*

Сервер вернет статус **200 OK** в случае успешного выполнения. В противном случае вернется сообщение об ошибке.


### Активация купона мерчанта по коду

#### POST /merchants/coupons/activate_by_coupon.json

Активирует купон по его коду и возвращает подробную информацию о нем.

**Параметры:**

- ``coupon`` - код купона
- ``security`` - код безопастности купона

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


### Активация купона мерчанта по QR-коду

#### POST /merchants/coupons/activate_by_qr.json

Активирует купон по его QR-коду и возвращает подробную информацию о нем.

**Параметры:**

- ``qr`` - QR-код купона

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


Описание полей из ответа сервера
--------------------------------

- ``description_permalink`` - пермалинк акции
- ``id`` - ID купона
- ``offer_id`` - ID акции
- ``activated`` - активирован ли купон?
- ``coupon`` - код купона