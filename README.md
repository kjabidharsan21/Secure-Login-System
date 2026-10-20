# Secure Login System

A beginner-friendly Flask web app demonstrating registration, bcrypt password hashing, parameterized SQLite queries, input validation, server-side session data, logout, and basic security headers.

## Features

- Register and log in with bcrypt password hashes (cost factor 12).
- Validate usernames and password length.
- Parameterized SQL queries to reduce SQL injection risk.
- Session-based login state, session reset after login, and logout.
- 30-minute session lifetime and HttpOnly / SameSite cookie settings.
- Basic browser security headers.

## Requirements

- Python 3.10+
- pip

## Run on Windows

Open PowerShell in this project folder:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
$env:SECRET_KEY = python -c "import secrets; print(secrets.token_hex(32))"
python app.py
```

If PowerShell blocks activation, you can run the environment's Python directly:

```powershell
py -m pip install -r requirements.txt
py app.py
```

Then open http://127.0.0.1:5000 in your browser. The SQLite database (`users.db`) is created automatically when you start `app.py`.

## Run on macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
export SECRET_KEY="$(python -c 'import secrets; print(secrets.token_hex(32))')"
python app.py
```

Then visit http://127.0.0.1:5000.

## Project structure

```text
secure_login_system/
├── app.py
├── requirements.txt
├── README.md
├── templates/
│   ├── base.html
│   ├── login.html
│   ├── register.html
│   └── dashboard.html
└── static/
    └── style.css
```

## Important security notes

This is a learning/demo project, not a production-ready authentication service. Before deploying publicly, add CSRF protection to every state-changing form (for example, Flask-WTF), rate limiting and login throttling, HTTPS, secure secret management, password reset and email verification flows, audit logging, and automated security tests. Enable `FLASK_HTTPS=1` only when serving over HTTPS. Do not use the development secret in production. Consider a maintained authentication framework for production systems.

Two-factor authentication (2FA) is not included in this starter version.
