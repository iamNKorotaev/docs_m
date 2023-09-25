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

# Установка

## Быстрая установка <a href="#quick-install" id="quick-install"></a>

{% hint style="info" %}
Данные Marzban будут доступны по пути`/var/lib/marzban`

Файлы Marzban ( docker-compose.yml и  .env) будут доступны по пути `/opt/marzban`
{% endhint %}

Выполните быструю установку с помощью следующей команды

```bash
sudo bash -c "$(curl -sL https://github.com/Gozargah/Marzban-scripts/raw/master/marzban.sh)" @ install
```

После установки вы можете остановить логи Marzban, нажав `Ctrl+C.`

Панель управления Marzban будет запущена на порту `8000`.

Вы можете войти в панель управления по адресу `http://YOUR_SERVER_IP:8000/dashboard/`

Чтобы создать супер-администратора, выполните следующую команду:

```bash
marzban cli admin create --sudo
```

Теперь вы можете войти в панель управления Marzban, используя созданное вами имя пользователя и пароль

Кроме того, вы можете запустить следующую команду, чтобы просмотреть руководство по сценарию Marzban.

```bash
marzban --help
```

Чтобы изменить настройки по умолчанию, вам необходимо отредактировать файл `/opt/marzban/.env`

[Список переменных](env.md) смотрите в разделе конфигурации

## Установка вручную (расширенная) <a href="#manual-install" id="manual-install"></a>

{% hint style="warning" %}
Ручная установка Marzban не рекомендуется непрофессионалам.&#x20;
{% endhint %}

Установите Xray, используя скрипт Xray-install, с помощью следующей команды

```bash
bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install
```

Клонируйте проект Marzban и установите зависимости, выполнив следующие команды

```bash
git clone https://github.com/Gozargah/Marzban.git
cd Marzban
python3 -m pip install -r requirements.txt
```

Запустите создание базы данных, выполнив следующую команду

```bash
alembic upgrade head
```

Создайте копию файла .env.example и настройте необходимые переменные

```bash
cp .env.example .env
```

Создайте символическую ссылку для marzban-cli и выполните автоматическую установку, используя следующие команды

```bash
sudo ln -s $(pwd)/marzban-cli.py /usr/bin/marzban-cli
sudo chmod +x /usr/bin/marzban-cli
marzban-cli completion install
```

Создайте супер администратора с помощью marzban-cli, выполнив следующую команду

```bash
marzban-cli admin create --sudo
```

Запустите Marzban, выполнив следующую команду:

```bash
python3 main.py
```
