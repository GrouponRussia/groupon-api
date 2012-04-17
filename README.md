Groupon API (v3)
================

Groupon API построен поверх протокола HTTP с использованием принципов REST. На данный момент мы поддерживаем два формата ответа сервера - XML и JSON.

В дальнейшем, в этой документации мы описываем все запросы и ответы сервера в формате JSON. Работа с XML полностью идентична и не должна вызвать затруднений.


Доступ к API
------------

Наш API подразделяет пользователей на несколько ролей. Каждая роль имеет строго определенный уровень функциональности и доступа к информации.

**Merchant** - пользователь, являющийся нашим поставщиком услуг. С помощью нашего API он имеет возможность получать инфорамцию о своих акциях, купонах и т.п. вне сайта [Groupon](http://groupon.ru).

Примером использования Merchant API может является интернет-магазин по продаже билетов, использующий для проверки введеных купонов наш API.

**Partner** - пользователь, являющийся нашим партнером. Имеет доступ к информации по текущим акциями в городах, регистрации пользователей и т.п.

Примером использования Partner API могут являться сайты-агрегаторы купонов.