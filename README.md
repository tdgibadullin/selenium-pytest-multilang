# Multilingual UI Test for Online Store (Selenium + pytest)

![Python](https://img.shields.io/badge/python-3.10+-blue?logo=python)
![pytest](https://img.shields.io/badge/Pytest-tested-brightgreen?logo=pytest)
![Selenium](https://img.shields.io/badge/Selenium-green?logo=selenium)

Этот учебный проект реализует автотест, проверяющий наличие кнопки "Добавить в корзину" на странице товара в демонстрационном интернет-магазине.

Проект поддерживает запуск теста на разных языках интерфейса браузера с помощью параметра командной строки.

## Задание

Реализовать автотест, который можно запускать с различными языками интерфейса, передаваемыми через параметр `--language`.

## Описание проверки

Тест открывает страницу товара в интернет-магазине:

```
http://selenium1py.pythonanywhere.com/catalogue/coders-at-work_207/
```

и выполняет два шага:
- ищет кнопку добавления товара в корзину по уникальному CSS-селектору;
- с помощью `assert` проверяет, что элемент присутствует на странице.

## Стек технологий

- Python
- Selenium
- pytest
- Google Chrome

## Структура проекта

```text
selenium-pytest-multilang/
├── conftest.py             # Добавляет параметр --language и фикстуру browser для запуска Chrome
├── test_items.py           # Проверяет наличие кнопки добавления в корзину
├── requirements.txt        # Список зависимостей проекта (Selenium, pytest)
├── .gitignore              # Исключения для git
├── README.md               # Описание проекта
```

## Установка и запуск

### 1. Подготовка окружения: ChromeDriver

- Узнайте версию Chrome: Меню Chrome → О Google Chrome.

- Скачайте соответствующую версию ChromeDriver с официального сайта:
https://googlechromelabs.github.io/chrome-for-testing/

- Распакуйте драйвер и разместите его в любой папке, доступной из PATH, либо укажите путь к драйверу в настройках запуска теста.

- После распаковки убедитесь, что нужная версия ChromeDriver установлена:

```bash
  chromedriver --version
```

### 2. Клонирование репозитория

```bash
git clone https://github.com/tdgibadullin/selenium-pytest-multilang.git
cd selenium-pytest-multilang
```

### 3. Установка зависимостей

Рекомендуется использовать виртуальное окружение:

```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 4. Запуск теста

Укажите язык интерфейса браузера с помощью параметра `--language`, например:

```bash
pytest --language=es test_items.py
```

Проверьте работу на других языках:

```bash
pytest --language=ru test_items.py
pytest --language=fr test_items.py
```

Чтобы вручную убедиться в корректной локализации, можно временно добавить `time.sleep(30)` в `test_items.py` после `browser.get(link)`.
