# Телеграм-бот «Mirror Leech»

Эффективный и многофункциональный телеграм-бот для зеркалирования и скачивания файлов из Интернета в Google Drive, Telegram или любое облако, поддерживаемое rclone. Реализован на Python с использованием asyncio для высокой производительности.

---

## 🔹 Возможности

* **Торренты (qBittorrent, Aria2c, SABnzbd)**

  * Выбор файлов до и во время загрузки
  * Управление посевом (отношение сидирования и время)
  * Синхронизация и редактирование глобальных настроек через меню бота

* **Прямые и облачные загрузки**

  * HTTP/FTP ссылки с авторизацией
  * NZB и JDownloader (поддержка DLC)
  * Извлечение видео/аудио через yt-dlp и подобные

* **Загрузка и назначения**

  * Google Drive (Service Account или OAuth)
  * rclone (серверная копия, загрузка, клон)
  * Telegram (как медиа или документы, с разбиением и миниатюрами)

* **Управление и статус**

  * Интерактивные inline-меню для задач и настроек
  * Страницы статуса с пагинацией и фильтрами
  * Очередь задач с паузой, отменой и приоритетами

* **Дополнительные инструменты**

  * Мониторинг RSS-лент с фильтрами
  * Работа с архивами (zip/7z: разбивка/распаковка)
  * Выполнение shell-команд и FFmpeg-скриптов
  * Пользовательские пути загрузки, шаблоны переименования

* **Развёртывание**

  * Docker (amd64/arm64/armv7)
  * Локальное окружение Python
  * Автообновление из upstream-репозитория

---

## 🚀 Быстрый старт

### 1. Клонирование и настройка

```bash
git clone https://github.com/shaniberd/telegram_tor.git
cd mirror-leech-bot
cp config_sample.py config.py
# Отредактируйте config.py: BOT_TOKEN, OWNER_ID, настройки Drive/remote
```

### 2. Запуск локально

```bash
python3 -m venv venv
source venv/bin/activate  # на Windows: venv\Scripts\activate
pip install -r requirements.txt
python3 bot/run.py
```

### 3. Запуск в Docker

```bash
docker compose up -d  # или
# docker build . -t mltb && docker run --network host mltb
```

---

## ⚙️ Настройка

Основные параметры хранятся в `config.py` или в MongoDB (для динамических изменений). Важные поля:

* **BOT\_TOKEN**, **OWNER\_ID** — токен бота и ID владельца
* **GDRIVE\_ID**, **RCLONE\_PATH** — папки загрузки по умолчанию
* **BASE\_URL**, **RCLONE\_SERVE\_URL** — веб-интерфейсы для выбора торрентов
* **QUEUE\_DOWNLOAD**, **QUEUE\_UPLOAD**, **QUEUE\_ALL** — ограничения параллельных задач
* **RSS\_DELAY**, **RSS\_CHAT** — мониторинг RSS-лент

См. подробные комментарии в `config_sample.py` для всех доступных опций.

---

## 📖 Документация и поддержка

* Репозиторий проекта: [https://github.com/shaniberd/telegram\_tor](https://github.com/shaniberd/telegram_tor)
* * Обсуждения и issues: [https://github.com/shaniberd/telegram\_tor/issues](https://github.com/shaniberd/telegram_tor/issues)
