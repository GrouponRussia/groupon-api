Common API
============

Cities
-------

### List of all available cities

#### GET /cities.json

Returns all available cities.

*Response:*

```json
{
  "cities": [
    {
      "name": "Москва",
      "id": 1,
    },
    {
      "name": "Санкт-Петербург",
      "id": 1,
    }
  ]
}
```


### Detailed information about city

#### GET /cities/#{id}.json

Returns detailed information about specific city.

**Parameters:**

- ``id`` - City ID

*Response:*

```json
{
  "city": {
    "name": "Москва",
    "id": 1,
    "country": {
      "name": "Россия"
    },
    "metro_stations": [
      {
        "name": "Преображенская пл."
      },
      {
        "name": "Планерная"
      }
    ]
  }
}
```


Response fields description:
-----------------------------------

- ``name`` - city name
- ``id`` - city ID
- ``country`` - country
    - ``name`` - country name
- ``metro_stations`` - list of metro stations
    - ``name`` - metro station name