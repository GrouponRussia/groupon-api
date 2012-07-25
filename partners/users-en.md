Partner API
===========

Users
------------

### User search

#### GET /users/search.json

Returns detailed information about user if it was found.

**Parameters:**

- ``email`` - user email address

*Response:*

```json
{
  "user": {
    "email": "atipugin@darberry.ru",
    "id": 27256253
  }
}
```


### User registration

#### POST /users.json

Creates new user and returns detailed information about him.

**Параметры:**

- ``user[email]`` - user email address
- ``user[password]`` - password (will be generated automatically if empty)
- ``user[city_id]`` - user city ID

*Response:*

```json
{
  "user": {
    "email": "atipugin@darberry.ru",
    "password": "chifyproc",
    "id": 27256253,
    "autosignin_token": "fb1d033f22ea9becc81f94e79c38b85a7f0ca7ed"
  }
}
```


Response fields description:
---------------------------------

- ``email`` - user email address
- ``password`` - password
- ``id`` - ID
- ``autosignin_token`` - token for autosignin