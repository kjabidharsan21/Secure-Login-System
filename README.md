# 🔐 Secure Login System

## 📌 About the Project

The Secure Login System is a web application I developed to understand how user authentication works and how user accounts can be protected from common security threats.

The application allows users to create an account, log in using their credentials, access a protected dashboard, and log out when they finish. While building this project, I focused on implementing basic security practices rather than just creating a login page.

One of the main features is password hashing using **bcrypt**, which ensures that passwords are not stored as plain text in the database. I also used parameterized SQL queries to reduce the risk of SQL injection and session management to control access to protected pages.

This project helped me gain practical experience in Python web development and understand the importance of security when handling user information.

## ✨ Features

- **User Registration:** Users can create accounts with a username and password.
- **Secure Password Storage:** Uses bcrypt to hash passwords before saving them in the database.
- **User Login:** Verifies credentials and allows registered users to access their accounts.
- **Input Validation:** Checks usernames and passwords to prevent invalid data from being submitted.
- **SQL Injection Protection:** Uses parameterized SQL queries for safer database operations.
- **Session Management:** Maintains the user's authenticated session and limits its lifetime.
- **Protected Dashboard:** Restricts dashboard access to logged-in users.
- **Logout Functionality:** Clears the login session when the user logs out.
- **Security Headers:** Includes basic browser security headers to improve protection.
- **Responsive Interface:** Provides a clean and simple interface for registration, login, and dashboard pages.

## 🛠️ Technologies Used

- **Python** – Application logic
- **Flask** – Web application framework
- **SQLite** – Stores user account information
- **bcrypt** – Password hashing and verification
- **HTML5** – Creates the web pages
- **CSS3** – Styles the application
- **Jinja2** – Renders dynamic HTML templates

## ⚙️ How It Works

1. A new user creates an account by entering a username and password.
2. The application validates the submitted information.
3. The password is hashed using bcrypt before it is stored in the SQLite database.
4. When the user logs in, the application verifies the entered password against the stored hash.
5. If the credentials are correct, a session is created and the user is redirected to the dashboard.
6. Users who are not logged in cannot access the protected dashboard.
7. When the user logs out, the session is cleared.

## 📂 Project Structure

```text
secure-login-system/
│
├── app.py
├── requirements.txt
├── README.md
│
├── templates/
│   ├── base.html
│   ├── login.html
│   ├── register.html
│   └── dashboard.html
│
└── static/
    └── style.css
```

- `app.py` contains the main application logic, authentication routes, database operations, and session handling.
- `requirements.txt` contains the Python packages required to run the project.
- `templates/` contains the login, registration, dashboard, and shared HTML pages.
- `static/style.css` contains the styling for the user interface.
- `README.md` provides project documentation and setup instructions.

The SQLite database is created automatically when the application starts.

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/secure-login-system.git
cd secure-login-system
```

Replace `YOUR-USERNAME` with your GitHub username.

### 2. Create a virtual environment

```bash
py -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install the required packages

```bash
python -m pip install -r requirements.txt
```

### 4. Set the Flask secret key

Run this command in PowerShell:

```powershell
$env:SECRET_KEY = py -c "import secrets; print(secrets.token_hex(32))"
```

### 5. Start the application

```bash
python app.py
```

### 6. Open the application

Visit `http://127.0.0.1:5000` in your browser. You can then register a new account, log in, explore the dashboard, and test the logout feature.

## 🔒 Security Practices

Security was an important part of this project. I used bcrypt for password hashing, input validation to reject invalid information, and parameterized SQL queries to reduce SQL injection risks. I also implemented session handling and basic security headers.

This is a learning project, so additional security measures, such as CSRF protection, login rate limiting, email verification, and secure password recovery, would be needed before using it in a public production environment.

**Note:** Two-factor authentication (2FA) is not included in the current version.

## 🔮 Future Improvements

Some features I would like to add in future versions include:

- Two-factor authentication (2FA)
- Email verification
- Password reset functionality
- Protection against repeated failed login attempts
- User roles and permissions
- Automated security and functionality tests
- Deployment using HTTPS and a production-ready server

## 🎓 What I Learned

Working on this project helped me understand how a web application's authentication process works in practice. I gained experience with Flask, database integration, password hashing, form validation, SQL injection prevention, and session management.

It also helped me recognize that building a login system involves more than checking a username and password. User data must be handled carefully, and security should be considered throughout the development process.

## 🏁 Conclusion

The Secure Login System is a hands-on project that combines web development with basic cybersecurity concepts. It gave me an opportunity to apply what I learned in Python and build a functional application with registration, login, and protected dashboard features.

I plan to improve it further by adding more advanced security features and exploring how authentication systems are designed for real-world applications.

**Project Type:** Web Development | Authentication | Cybersecurity

**Current Status:** Basic authentication features implemented.
