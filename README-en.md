Groupon API
===========

Groupon API built upon the protocol HTTP in connection with ground rules of REST. We can provide response in 2 formats: XML and JSON.
In this documentation we will describe requests and responses  for JSON. Work with XML is totally identical.


Accessing API
------------------

Our API divides users into several roles. Each role has strictly defined functionality and information access.
 
**Merchant** is  a role for our vendors. With help of Merchant API vendor can get an information about his deals, coupons etc  out of Groupon site.
 Usage example: online ticket-shop where API is used for verification of  coupons.  

**Partner** is a role for our partner. Partner has an access to information about active deals in all cities, user registration etc.
Usage example: coupon aggregators.

**Reseller** is a role for resellers of coupons and vouchers. Reseller has an access to information about active deals in all cities and coupon  buying.
Usage example:  online-shops which resell coupons and vouchers.

Also we have **Common API**. It is open to all users regardless of their roles and access right.

At the moment we make a decision about API access  in a personal order. 


Authorization
------------------

Before start using the API you have to log in system and get ``api_id`` and ``api_token``.

For authorization you need to make a POST-request to:

    http://api.groupon.ru/v3/sign_in.json

In request parameteres you should specify your [Groupon](http://groupon.ru) account data:

- ``user[email]`` - your email address
- ``user[password]`` - your password

*Example using [Curl](http://ru.wikipedia.org/wiki/CURL):*

```shell
curl -d "user[email]=ivan_ivanov@gmail.com&user[password]=secret" http://api.groupon.ru/v3/sign_in.json
```

If you point out correct data, authorization will be successful. As a result you will receive this response:

```json
{
  "user": {
    "id": 13579,
    "api_id": 24680,
    "api_token": "fc5e038d38a57032085441e7fe7010b0"
  }
}
```

If you point out incorrect data, you will receive this response:

```json
{
  "error": "Invalid credentials."
}
```

It is strongly recommended to save ``api_id`` and ``api_token`` received during the authorization.  This information is necessary for  the next requests to API.


Making requests
---------------------

All requests should be perform to the address: **http://api.groupon.ru/v3**

Maximum amount of requests per minute is **600**.

Each request to the API should meet the following options:In the matter of what information you are applying, the parameters are changed.These three parameters should always be present in the created request:

- ``api_id`` - your api-account ID in the system
- ``signature`` - unique signature of your request
- ``timestamp`` - current time on your server or device inUnix Timestamp [Unix Timestamp](http://ru.wikipedia.org/wiki/UNIX-%D0%B2%D1%80%D0%B5%D0%BC%D1%8F) format

We have parameter ``api_id`` to identify you in the system. You will get it after successful authorization. 

Parameter ``signature`` is required for us to safe request we do at the moment. You can get more information about signing the request in chapter **"Creating a signature."**

The parameter ``timestamp`` shows the exact time of the request was made. You should set it by yourself everytime you making the request.

*Example of properly formatted request:*

    http://api.groupon.ru/v3/cities.json?api_id=24680&signature=b159366cb50f17bab55013837c92d73a&timestamp=1332792966


Creating the signature
----------------------------

Every request you make to our API should be signed with special parameter called ``signature``.

Signature is a mix of three values. First two, ``api_id`` and ``api_token``, you receive right after successful authorization. Last one, ``timestamp``, you set by yourself with value of current [timestamp](http://ru.wikipedia.org/wiki/UNIX-%D0%B2%D1%80%D0%B5%D0%BC%D1%8F) on server, which making requests.

Next, you should concatenate these values in alphabetical order into string, separating each one with ``_`` symbol (underscore). Like this:

    {api_id}_{api_token}_{timestamp}

*For example, if your ``api_id`` - 24680, ``api_token`` - fc5e038d38a57032085441e7fe7010b0, а ``timestamp`` - 1332792966, then your string should look like this:*

    24680_fc5e038d38a57032085441e7fe7010b0_1332792966

Last step is to encrypt this string with MD5. So, hash that you get, should be correct signature for your request.

*So, the correct signature in case of our example above, will be::*

    b159366cb50f17bab55013837c92d73a

In case you passed wrong request signature, you will get following error message:

```json
{
  "error": "Incorrect signature."
}
```

Common API
------------------

- [Cities](https://github.com/GrouponRussia/groupon-api/blob/master/common/cities-en.md)


Merchant API
-------------------

- [Deals](https://github.com/GrouponRussia/groupon-api/blob/master/merchants/offers-en.md)
- [Orders](https://github.com/GrouponRussia/groupon-api/blob/master/merchants/coupons-en.md)


Partner API
---------------

- [Deals](https://github.com/GrouponRussia/groupon-api/blob/master/partners/offers-en.md)
- [Users](https://github.com/GrouponRussia/groupon-api/blob/master/partners/users-en.md)


Reseller API
----------------

- [Users](https://github.com/GrouponRussia/groupon-api/blob/master/resellers/users-en.md)
- [Orders](https://github.com/GrouponRussia/groupon-api/blob/master/resellers/coupons-en.md)
- [Deals](https://github.com/GrouponRussia/groupon-api/blob/master/resellers/offers-en.md)
- [Payments](https://github.com/GrouponRussia/groupon-api/blob/master/resellers/payments-en.md)


Possible errors
------------------

Here goes the list of common errors you can receive while dealing with our API.

- ``Invalid credentials.`` - You have provided incorrect account data.
- ``Access denied.`` - You don't have access for this request.
- ``Unable to load API user.`` - Unable to load API user with ID you provided in ``api_id_`` param.
- ``Incorrect signature.`` - The signature you provided is incorrect or already used.
- ``Not found.`` - Resource not found.