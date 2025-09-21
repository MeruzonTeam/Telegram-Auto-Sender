# 🚀 Инструкция по запуску Telegram Auto Sender

Этот скрипт нужен для автоматической рассылки сообщений или пересылки поста в группы Телеграма.

---

## 1. Установка

1. Установите Python 3.9 или новее: https://www.python.org/downloads/  
   При установке поставьте галочку **Add to PATH**.

2. В папке со скриптом установите библиотеку:
```bash
pip install telethon
```

---

## 2. Настройка аккаунтов

1. При первом запуске появится файл **accounts.ini**.  
   Если его нет – создайте сами.

2. Пример для двух аккаунтов:
```ini
[account1]
api_id = 1234567
api_hash = abcdef1234567890abcdef1234567890
session_name = session1

[account2]
api_id = 7654321
api_hash = 0987654321fedcba0987654321fedcba
session_name = session2
```

🔑 Где взять api_id и api_hash:
- Зайдите на https://my.telegram.org  
- Авторизуйтесь по номеру телефона  
- Нажмите **API development tools**  
- Создайте приложение → получите `api_id` и `api_hash`.

⚠️ `session_name` — любое название. При первом запуске скрипт спросит номер телефона и код из Telegram.

---

## 3. Настройки рассылки

Файл **config.ini** создаётся сам.  

Главные параметры:
```ini
[SENDING]
loop_enabled = true
loop_delay_seconds = 300
min_delay_between_groups = 2
max_delay_between_groups = 5
extra_text = none
message_link = none
```

👉 Пример: пересылка поста с текстом:
```ini
extra_text = 🔥 Новый пост!
message_link = https://t.me/kanal/123
```

---

## 4. Запуск

В папке со скриптом:
```bash
python main.py
```

- Введите номер телефона и код (при первом запуске).  
- Скрипт начнёт рассылку.

---

## 5. Логи

Результаты сохраняются в **stats.log**.  
Ошибки и паузы (FloodWait) обрабатываются автоматически.
