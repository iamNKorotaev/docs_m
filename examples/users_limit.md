# Ограничение пользователей

Вы можете ограничить количество подключений с одного конфига несколькими реализациями.

Существует два скрипта для этой цели, и их способы функционирования полностью различаются.

## V2IpLimit

Этот скрипт,  для ограничения IP в Marzban, работает следующим образом: если количество подключенных IP-адресов для пользователя превышает установленный вами лимит, эта учетная запись будет отключена на указанный период времени, а затем снова активирована после истечения этого времени.

[https://github.com/houshmand-2005/V2IpLimit](https://github.com/houshmand-2005/V2IpLimit)

## luIP-marzban

Этот скрипт работает иначе. Например, если ограничение IP установлено на одно подключение, и два пользователя пытаются подключиться к одной учетной записи, второй IP будет заблокирован через таблицу IP на указанный период времени, но первый IP останется подключенным. Таким образом,  будет отключен только второй пользователь, а не будет отключена вся учетная запись

[https://github.com/mmdzov/luIP-marzban](https://github.com/mmdzov/luIP-marzban)