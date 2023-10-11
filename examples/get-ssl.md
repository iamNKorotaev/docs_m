---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Получение SSL

## Получению сертификата SSL для использования в Marzban <a href="#intro" id="intro"></a>

{% hint style="info" %}
Файлы сертификатов должны быть доступны по адресу `/var/lib/marzban/certs`, чтобы Marzban мог получить к ним доступ.

Во всех примерах ниже файлы будут установлены по этому адресу.
{% endhint %}

{% hint style="info" %}
Прежде чем приступить к получению SSL-сертификата, вы должны настроить DNS-записи домена.
{% endhint %}

## Получение сертификата с acme.sh <a href="#acme.sh" id="acme.sh"></a>

Устанавливаем нужный софт

<pre class="language-bash"><code class="lang-bash"><strong>apt install cron &#x26;&#x26; apt install socat 
</strong></code></pre>

```sh
curl https://get.acme.sh | sh -s email=EMAIL
```

Создаем директорию для сертификатов

```sh
mkdir -p /var/lib/marzban/certs/
```

Получаем сертификат

Введите ваш домен или субдомен в поле `DOMAIN`

```shell
~/.acme.sh/acme.sh --set-default-ca --server letsencrypt  --issue --standalone -d DOMAIN \
--key-file /var/lib/marzban/certs/key.pem \
--fullchain-file /var/lib/marzban/certs/fullchain.pem
```

В случае, если вам необходимо получить сертификаты для ваших поддоменов, команда получения сертификата будет выглядеть так

```bash
~/.acme.sh/acme.sh --set-default-ca --server letsencrypt --issue --standalone \
-d DOMAIN \
-d SUBDOMAIN1.DOMAIN \
-d SUBDOMAIN2.DOMAIN \
--key-file /var/lib/marzban/certs/key.pem \
--fullchain-file /var/lib/marzban/certs/fullchain.pem
```

### Посмотреть список выпущенных сертификатов с их сроком <a href="#cert-list" id="cert-list"></a>

```bash
~/.acme.sh/acme.sh --list
```
