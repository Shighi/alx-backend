# Internationalization with Flask and Babel

## Project Overview

This project demonstrates internationalization (i18n) in a Flask web application using the Flask-Babel extension. It includes locale selection via request headers and URL parameters, user-specific locale and timezone handling, and dynamic rendering of content in English and French.

---

## Features

* Basic Flask app setup with templates
* Flask-Babel integration for language translation
* Locale selection from request headers and URL query parameters
* User mock authentication to apply personalized language and timezone
* Timezone validation and conversion using `pytz`
* Dynamic display of current time in the user's timezone
* HTML templates with translatable strings using gettext

---

## Technologies

* Python 3.7
* Flask
* Flask-Babel 2.0.0
* pytz

---

## Setup Instructions

### Requirements

* Ubuntu 18.04 LTS
* Python 3.7

### Installation

```bash
$ sudo apt update
$ sudo apt install python3-pip
$ pip3 install flask==1.1.2 flask_babel==2.0.0 pytz
```

### Run the App

Choose the version you want to run:

```bash
$ python3 0-app.py
# or
$ python3 1-app.py
# etc.
```

Access the app at `http://127.0.0.1:5000/`

### Language and Timezone Testing

* Test translation using URL parameters:

  * `http://127.0.0.1:5000/?locale=fr`
  * `http://127.0.0.1:5000/?locale=en`

* Test mock login:

  * `http://127.0.0.1:5000/?login_as=2`

* Test timezone:

  * `http://127.0.0.1:5000/?timezone=Europe/Paris`

---

## Project Structure

```
0x02-i18n/
├── templates/
│   ├── 0-index.html
│   ├── 1-index.html
│   ├── ...
├── translations/
│   ├── en/LC_MESSAGES/messages.po
│   ├── fr/LC_MESSAGES/messages.po
│   ├── en/LC_MESSAGES/messages.mo
│   └── fr/LC_MESSAGES/messages.mo
├── 0-app.py
├── 1-app.py
├── 2-app.py
├── ...
├── app.py
├── babel.cfg
└── README.md
```

---

## Coding Standards

* Files end with a new line
* All Python files begin with `#!/usr/bin/env python3`
* Python files are executable and follow `pycodestyle` (v2.5)
* All modules, classes, and functions have proper docstrings
* All functions and coroutines include type annotations

---

## License

This project is intended for educational purposes as part of the ALX Software Engineering Program.
