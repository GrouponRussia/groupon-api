Merchant API
============

Merchant coupons
------------------------

### List of all merchant coupons

#### GET /merchants/coupons.json

Returns list of all merchant coupons.

*Response:*

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


### List of all merchant coupons by specific deal

#### GET /merchants/offers/#{offer_id}/coupons.json

Returns list of all merchant coupons by specific deal.

**Parameters:**

- ``offer_id`` - deal ID

*Response:*

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


### Detailed information about specific coupon

#### GET /merchants/coupons/#{id}.json

Returns detailed information about specific merchant coupon.

**Parameters:**

- ``id`` - coupon ID

*Response:*

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


### Merchant coupon search

#### GET /merchants/coupons/search.json

Returns detailed information about merchant coupon if it was found.

**Parameters:**

- ``coupon`` - coupon code

*Response:*

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


### Coupon activation

#### PUT /merchants/coupons/#{id}.json/activate

Activates specific coupon by its ID.

**Parameters:**

- ``id`` - coupon ID
- ``security`` - coupon security code

*Response:*

Server will respond with **200 OK** status on success. Otherwise it will response with error message.


### Coupon activation by code

#### POST /merchants/coupons/activate_by_coupon.json

Activates specific coupon by its code.

**Parameters:**

- ``coupon`` - coupon code
- ``security`` - coupon security code

*Response:*

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


### Coupon activation by QR-code

#### POST /merchants/coupons/activate_by_qr.json

Activates specific coupon by its QR-code.

**Parameters:**

- ``qr`` - coupon QR-code

*Response:*

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


Response fields description:
--------------------------------

- ``description_permalink`` - deal permalink
- ``id`` - coupon ID
- ``offer_id`` - deal ID
- ``activated`` - is coupon used?
- ``coupon`` - coupon code