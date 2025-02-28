![image](https://github.com/user-attachments/assets/c65ef755-4d97-4d48-b2c5-a8ab50e7c857)
# Bless Network Node Manager

[English](#english) | [Русский](#russian)

<a name="english"></a>
# Bless Network Node Manager [EN]

## System Requirements
- Windows OS
- Python 3.10
- Internet connection

## Installation

1. Run `install.bat` (Windows) or `install.sh` (Linux/Mac) to:
   - Create virtual environment
   - Install dependencies
   - Set up necessary files and directories

2. After installation, use `run.bat` (Windows) or `run.sh` (Linux/Mac) to start the program.

## Quick Start Guide

### 1. Configuration Files

#### auth.txt (Authorization accounts)
```
email:password
email:password
```

#### reg.txt (Registration Node accounts)
```
email:password
email:password
```

#### farm.txt (Farming accounts)
```
email:password
email:password
```

#### proxies.txt (Proxy list)
```
scheme://username:password@ip:port
```

### 2. Core Settings (config.py)

```python
# Threading
FARM_THREADS = 5  # Number of concurrent threads
REG_THREADS = 5  # Number of concurrent threads

AUTH_THREADS = 1  # Number of concurrent threads not more than 1

# Telegram Bot
TELEGRAM_BOT_TOKEN = "YOUR_BOT_TOKEN"
TELEGRAM_CHAT_ID = "YOUR_CHAT_ID"

# Node Settings
FARM_NODES = 3  # Nodes per account

```

### 3. Telegram Bot Setup Guide

#### Creating a Bot

1. Open Telegram and search for [@BotFather](https://t.me/BotFather)
2. Start a chat and send `/newbot`
3. Follow the instructions:
   - Enter bot name (e.g., "My Bless Manager")
   - Enter bot username (must end in 'bot', e.g., "my_bless_manager_bot")
4. Save the HTTP API token you receive (looks like `123456789:ABCdefGHIjklMNOpqrsTUVwxyz`)

#### Getting Your Chat ID

1. Open [@getmyid_bot](https://t.me/getmyid_bot)
2. Send any message to the bot
3. Copy your ID number from the response

#### Configuring the Bot

1. Open `config.py` and update these lines:
```python
TELEGRAM_BOT_TOKEN = "YOUR_BOT_TOKEN"  # Paste your bot token here
TELEGRAM_CHAT_ID = "YOUR_CHAT_ID"      # Paste your chat ID here
```

2. Start your bot:
   - Find your bot by username in Telegram
   - Click Start
   - Send `/start` command

3. Test the connection:
   - Run your script
   - You should receive notifications in Telegram

#### Troubleshooting

If notifications don't work:
1. Check if bot token is correct
2. Ensure you started the bot in Telegram
3. Verify your chat ID
4. Make sure you have internet connection

### 4. Usage

Authorization:
```
authorize accounts from auth.txt
```

Registration:
```
register accounts from reg.txt
```

Farming:
```
farm accounts from farm.txt
```

## Quick Usage Guide

### Step 1: Authorization 
```bash
python main.py use 1
```
- Uses Playwright for authorization
- Must be repeated when token expires
- Use only 1 thread for stability

### Step 2: Node Registration
```bash
python main.py use 2
```
- Register nodes for authorized accounts
- Can use multiple threads for speed

### Step 3: Farming
```bash
python main.py use 3
```
- Start farming with registered nodes
- Can use multiple threads

### Step 4: Statistics
```bash
python main.py use 4
```
- View current statistics
- Can be run separately at any time
- Statistics can be updated and requested via Telegram bot

## Support
TellBip - [Telegram](https://t.me/Tell_Bip)

## Disclaimer

By using this software, you acknowledge and agree that:

1. The author is not responsible for:
   - Any losses or damages caused by using this software
   - Account bans or restrictions
   - Loss of funds or assets
   - Problems with third-party services
   - Any other consequences of using this software

2. You use this software:
   - At your own risk
   - Understanding all potential consequences
   - Taking full responsibility for your actions

3. This software:
   - Is provided "as is" without any warranty
   - May contain bugs or errors
   - May stop working at any time
   - May be discontinued without notice

4. You are responsible for:
   - Compliance with local laws and regulations
   - Security of your accounts and data
   - Proper configuration and usage

---

<a name="russian"></a>
# Bless Network Node Manager [RU]

## Системные требования
- Операционная система Windows
- Python 3.10
- Подключение к интернету

## Установка

1. Запустите `install.bat` (Windows) или `install.sh` (Linux/Mac) для:
   - Создания виртуального окружения
   - Установки зависимостей
   - Настройки необходимых файлов и директорий

2. После установки используйте `run.bat` (Windows) или `run.sh` (Linux/Mac) для запуска программы.

## Краткое руководство

### 1. Файлы конфигурации

#### auth.txt (Аккаунты для авторизации)
```
email:password
email:password
```

#### reg.txt (Аккаунты для регистрации нод)
```
email:password
email:password
```

#### farm.txt (Аккаунты для фарминга)
```
email:password
email:password
```

#### proxies.txt (Список прокси)
```
scheme://username:password@ip:port
```

### 2. Основные настройки (config.py)

```python
# Потоки
FARM_THREADS = 5  # Количество одновременных потоков
REG_THREADS = 5  # Количество одновременных потоков

AUTH_THREADS = 1  # Количество одновременных потоков не более 1

# Telegram Bot
TELEGRAM_BOT_TOKEN = "ВАШ_ТОКЕН_БОТА"
TELEGRAM_CHAT_ID = "ВАШ_ЧАТ_ID"

# Настройки нод
FARM_NODES = 3  # Количество нод на аккаунт
```

### 3. Руководство по настройке Telegram бота

#### Создание бота

1. Откройте Telegram и найдите [@BotFather](https://t.me/BotFather)
2. Начните чат и отправьте `/newbot`
3. Следуйте инструкциям:
   - Введите имя бота (например, "My Bless Manager")
   - Введите username бота (должен заканчиваться на 'bot', например "my_bless_manager_bot")
4. Сохраните полученный HTTP API токен (выглядит как `123456789:ABCdefGHIjklMNOpqrsTUVwxyz`)

#### Получение Chat ID

1. Откройте [@getmyid_bot](https://t.me/getmyid_bot)
2. Отправьте любое сообщение боту
3. Скопируйте ваш ID из ответа

#### Настройка бота

1. Откройте `config.py` и обновите эти строки:
```python
TELEGRAM_BOT_TOKEN = "ВАШ_ТОКЕН_БОТА"  # Вставьте ваш токен бота
TELEGRAM_CHAT_ID = "ВАШ_ЧАТ_ID"        # Вставьте ваш chat ID
```

2. Запустите вашего бота:
   - Найдите бота по username в Telegram
   - Нажмите Start
   - Отправьте команду `/start`

3. Проверьте подключение:
   - Запустите ваш скрипт
   - Вы должны получить уведомления в Telegram

#### Устранение проблем

Если уведомления не работают:
1. Проверьте правильность токена бота
2. Убедитесь, что вы запустили бота в Telegram
3. Проверьте правильность chat ID
4. Убедитесь, что есть подключение к интернету

### 4. Использование

Авторизация:
```
authorize accounts from auth.txt
```

Регистрация:
```
register accounts from reg.txt
```

Фарминг:
```
farm accounts from farm.txt
```

## Краткое руководство по использованию

### Шаг 1: Авторизация 
```bash
python main.py выбрать пункт 1
```
- Использует Playwright для авторизации
- Необходимо повторять при истечении токена
- Использовать только 1 поток для стабильности

### Шаг 2: Регистрация нод
```bash
python main.py выбрать пункт 2
```
- Регистрация нод для авторизованных аккаунтов
- Можно использовать несколько потоков для скорости

### Шаг 3: Фарминг
```bash
python main.py выбрать пункт 3
```
- Запуск фарминга на зарегистрированных нодах
- Можно использовать несколько потоков

### Шаг 4: Статистика
```bash
python main.py выбрать пункт 4
```
- Просмотр текущей статистики
- Можно запускать отдельно в любое время
- Статистику можно обновить и запросить через Telegram бот

## Поддержка
TellBip - [Telegram](https://t.me/Tell_Bip)

## Отказ от ответственности

Используя данное программное обеспечение, вы признаете и соглашаетесь с тем, что:

1. Автор не несет ответственности за:
   - Любые убытки или ущерб, вызванные использованием данного ПО
   - Блокировку или ограничение аккаунтов
   - Потерю средств или активов
   - Проблемы со сторонними сервисами
   - Любые другие последствия использования ПО

2. Вы используете это ПО:
   - На свой страх и риск
   - Понимая все возможные последствия
   - Принимая полную ответственность за свои действия

3. Данное ПО:
   - Предоставляется "как есть" без каких-либо гарантий
   - Может содержать ошибки или баги
   - Может перестать работать в любой момент
   - Может быть прекращено без предупреждения

4. Вы несете ответственность за:
   - Соблюдение местных законов и правил
   - Безопасность ваших аккаунтов и данных
   - Правильную настройку и использование 
