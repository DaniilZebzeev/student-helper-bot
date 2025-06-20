# 🎓 HSE Student Helper Bot

Telegram-бот для студентов с функционалом управления дедлайнами, расчета среднего балла и социальными возможностями.

## 🚀 Возможности

### 📅 Управление дедлайнами
- Добавление личных и общих дедлайнов
- Автоматические напоминания (за 5, 3, 1 день и в день дедлайна)
- Просмотр актуальных и просроченных дедлайнов
- Удаление дедлайнов с уведомлениями

### 📊 Академические функции
- Расчет среднего балла диплома (10-балльная система)
- Расчет среднего балла по предмету
- Конвертация оценок в словесную форму

### 🎉 Социальные функции
- Приглашения на пиво, кино, прогулки, настолки
- Поздравления с днями рождения
- Ограничение частоты приглашений (1 раз в неделю)

### 📞 Информационные функции
- Контакты администрации
- Ссылка на оплату обучения
- Подробная справка по командам

## 📦 Установка

### Требования
- Python 3.8+
- Telegram Bot Token от [@BotFather](https://t.me/botfather)

### Шаги установки

1. **Клонируйте репозиторий:**
```bash
git clone https://github.com/your-username/student-helper-bot.git
cd student-helper-bot
```

2. **Установите зависимости:**
```bash
pip install -r requirements.txt
```

3. **Настройте переменные окружения:**
```bash
cp .env.example .env
```

Отредактируйте `.env` файл:
```env
BOT_TOKEN=your_bot_token_here
CHAT_ID=your_chat_id
ALLOWED_GROUP_ID=your_chat_id
LOG_LEVEL=INFO
```

4. **Создайте папку для данных:**
```bash
mkdir data
```

5. **Настройте персональные данные:**
```bash
# Следуйте инструкциям в файле CUSTOMIZATION.md
```

6. **Запустите бота:**
```bash
python Open_Source.py
```

## 🔧 Конфигурация

> ⚠️ **Важно**: Перед запуском обязательно настройте персональные данные согласно [CUSTOMIZATION.md](CUSTOMIZATION.md)

### Получение необходимых ID

1. **BOT_TOKEN**: Получите у [@BotFather](https://t.me/botfather)
2. **CHAT_ID**: Добавьте [@userinfobot](https://t.me/userinfobot) в группу
3. **ALLOWED_GROUP_ID**: ID группы, где будет работать бот

### Настройка дней рождения

Создайте файл `data/happy.json` со структурой:
```json
[
  {
    "имя": "Иван",
    "фамилия": "Иванов",
    "дата рождения": "27 октября"
  }
]
```

## 🎮 Использование

### Основные команды
- `/start` - Запуск бота
- `/menu` - Главное меню с кнопками
- `/help` - Справка по командам
- `/add_deadline` - Добавить дедлайн через команду
- `/list_deadlines` - Показать актуальные дедлайны
- `/set_group` - Установить группу для уведомлений

### Добавление дедлайна через команду
```
/add_deadline false Математика "Лабораторная работа 1" 2024-12-25 23:59 "Решить 10 задач"
```

Параметры:
- `false/true` - общий/личный дедлайн
- `Предмет` - название предмета
- `"Название"` - название задания (в кавычках если содержит пробелы)
- `YYYY-MM-DD HH:MM` - дата и время дедлайна
- `"Описание"` - подробное описание

### Интерактивное меню

Используйте кнопки меню для удобного доступа ко всем функциям:
- 🎓 Средний балл диплома
- 📚 Балл по предмету  
- 📞 Контакты администрации
- 🗓 Дедлайны
- 🍺 Социальные приглашения

## 🐳 Docker (опционально)

```yaml
# docker-compose.yml
version: '3.8'

services:
  student-bot:
    build: .
    environment:
      - BOT_TOKEN=${BOT_TOKEN}
      - CHAT_ID=${CHAT_ID}
      - ALLOWED_GROUP_ID=${ALLOWED_GROUP_ID}
      - LOG_LEVEL=${LOG_LEVEL}
    volumes:
      - ./data:/app/data
    restart: unless-stopped
```

## 📁 Структура проекта

```
student-helper-bot/
├── Open_Source.py          # Основной файл бота
├── requirements.txt        # Зависимости Python
├── .env.example           # Пример переменных окружения
├── .gitignore            # Исключения для Git
├── README.md             # Документация
├── LICENSE               # Лицензия MIT
├── CONTRIBUTING.md       # Руководство для участников
├── CHANGELOG.md          # История изменений
├── CUSTOMIZATION.md      # Настройка персональных данных
├── DEPLOY.md             # Инструкции по публикации
├── Dockerfile            # Docker конфигурация
├── docker-compose.yml    # Docker Compose
├── start.sh              # Скрипт запуска (Linux/macOS)
├── start.bat             # Скрипт запуска (Windows)
├── data/                 # Папка для данных
│   ├── users.json        # Список пользователей
│   ├── user_actions.json # История действий
│   ├── happy.json        # Дни рождения
│   └── happy.json.example # Пример файла дней рождения
└── deadlines_data.json   # Данные дедлайнов
```

## 🤝 Вклад в проект

1. Сделайте форк проекта
2. Создайте ветку для новой функции: `git checkout -b feature/amazing-feature`
3. Зафиксируйте изменения: `git commit -m 'Add amazing feature'`
4. Отправьте в ветку: `git push origin feature/amazing-feature`
5. Откройте Pull Request

## 📝 Лицензия

Этот проект распространяется под лицензией MIT. Подробности в файле [LICENSE](LICENSE).

## 🐛 Сообщить об ошибке

Если вы нашли ошибку, создайте [Issue](https://github.com/your-username/student-helper-bot/issues) с подробным описанием.

## ⭐ Поддержать проект

Если проект оказался полезным, поставьте звезду ⭐ на GitHub!

---

**Автор:** [Daniil Zebzeev](https://github.com/your-username)
**Версия:** 1.0.0 
