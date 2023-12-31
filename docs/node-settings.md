# Настройка узла

**Marzban Node** - это приложение на Python, предоставляющее сервис для управления экземпляром ядра Xray. Оно использует RPyC для удаленных вызовов процедур и Docker для контейнеризации. Приложение разработано с учетом требований безопасности и использует самоподписанные SSL-сертификаты для связи между сервисом и его клиентами. Приложение состоит из нескольких Python-скриптов и конфигурационных файлов:

С помощью этого руководства вы можете создать узел Marzban Node на дополнительном сервере и подключить его к панели.

Приложение состоит из нескольких Python-скриптов и конфигурационных файлов:

* `certificate.py`: Python-скрипт для генерации самоподписанного SSL-сертификата.
* `config.py`: Python-скрипт для загрузки переменных окружения и установки значений по умолчанию для некоторых параметров.
* `docker-compose.yml`: Файл Docker Compose для определения и управления сервисами приложения.
* `logger.py`: Python-скрипт для настройки логгера для приложения.
* `main.py`: Основная точка входа в приложение. Он устанавливает сервер RPyC с SSL-аутентификацией и запускает его.
* `service.py`: Python-скрипт, определяющий RPyC-сервис для управления экземпляром ядра Xray.
* `xray.py`: Python-скрипт, определяющий класс для управления экземпляром ядра Xray.

## Установка узла на сервер <a href="#install" id="install"></a>

### Автоматическая установка <a href="#auto-install" id="auto-install"></a>

Воспользуйтесь скриптом автоматической установки

```bash
sudo bash -c "$(curl -sL https://github.com/Iambabyninja/marzban-tools/raw/main/install_marzban_node.sh)" @ install
```

Скрипт автоматически установит все зависимости и выведет сертификат для подключения к узлу.

### Ручная установка <a href="#manual-install" id="manual-install"></a>

Обновляем сервер

```bash
sudo apt-get update && sudo apt-get upgrade
```

Устанавливаем нужный софт

```bash
apt install socat -y && apt install curl socat -y && apt install git -y
```

Клонируем репозиторий

```bash
git clone https://github.com/Gozargah/Marzban-node
```

Входим в рабочую папку узла

```bash
cd Marzban-node
```

Устанавливаем Docker

```bash
curl -fsSL https://get.docker.com | sh
```

Запускаем узел

```bash
docker compose up -d
```

Получаем сертификат для подключения к узлу

```bash
cat /var/lib/marzban-node/ssl_cert.pem
```

## Подключение узла к панели <a href="#connect" id="connect"></a>

Открываем настройки узлов

![](<../.gitbook/assets/image (8).png>)

Заполняем данные узла:

* Name - Имя узла.&#x20;
* Adress - IP адрес/домен/поддомен узла.
* Port - Оставляем по умолчанию, если не изменяли их.
* Certificate - сертификат узла, полученный ранее.

Оставляем галку, если хотим добавить узел в качестве нового хоста во все входящие

![](<../.gitbook/assets/image (11).png>)

Жмем `Add Node`

## Использование ноды на нескольких панелях <a href="#multi-panel-usage" id="multi-panel-usage"></a>

Иногда, может возникнуть потребность запуска нескольких экзепляров узла на одном сервере, для подключения к нескольким панелям.

Для этого нам необходимо отредактировать файл `docker-compose.yml`  следующим образом

```yaml
services:
  node-1:
    # build: .
    image: gozargah/marzban-node:latest
    restart: always
    network_mode: host

    volumes:
      - /var/lib/marzban-node:/var/lib/marzban-node
      - /var/lib/marzban:/var/lib/marzban

    environment:
      SERVICE_PORT: 2000
      XRAY_API_PORT: 2001


  node-2:
    # build: .
    image: gozargah/marzban-node:latest
    restart: always
    network_mode: host

    volumes:
      - /var/lib/marzban-node:/var/lib/marzban-node
      - /var/lib/marzban:/var/lib/marzban

    environment:
      SERVICE_PORT: 3000
      XRAY_API_PORT: 3001
```

После перезагрузки контейнера,мы будем иметь следующее:

|               | Node-1 | Node-2 |
| ------------- | ------ | ------ |
| SERVICE PORT  | 2000   | 3000   |
| XRAY API PORT | 2001   | 3001   |

Получаем сертификат для подключения к узлу

```bash
cat /var/lib/marzban-node/ssl_cert.pem
```

И добавляем наши узлы исходя из вышеперечисленных данных
