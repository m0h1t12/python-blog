# Flask Blog Application

A modern, user-friendly blogging platform built with Flask. Users can create accounts, sign in, and share their thoughts with the community.

## 🚀 Features

- **User Authentication**: Secure sign-up and login system with password hashing
- **Create Posts**: Authenticated users can create and share blog posts
- **User Profiles**: Each user has a profile with their posts
- **Session Management**: Persistent login sessions with "Remember Me" functionality
- **Responsive Design**: Mobile-friendly interface
- **Database Support**: SQLite database with SQLAlchemy ORM

## 🛠️ Tech Stack

### Backend Framework
- **Flask** (3.1.3) - Lightweight Python web framework
- **Flask-SQLAlchemy** (3.1.1) - ORM for database operations
- **Flask-Login** (0.6.3) - User session and authentication management

### Database
- **SQLAlchemy** (2.0.49) - Python SQL toolkit and ORM
- **SQLite** - Lightweight database

### Security
- **Werkzeug** (3.1.8) - Utilities for WSGI applications (password hashing)
- **itsdangerous** (2.2.0) - Data signing and timestamp signing

### Frontend
- **Jinja2** (3.1.6) - Template engine for HTML rendering
- **MarkupSafe** (3.0.3) - Safe string handling in templates

### Additional Dependencies
- **click** (8.3.3) - Command-line interface creation kit
- **colorama** (0.4.6) - Colored terminal output
- **blinker** (1.9.0) - Signal support for Flask
- **greenlet** (3.5.0) - Lightweight concurrency primitives
- **typing-extensions** (4.15.0) - Python typing utilities

## 📋 Requirements

- Python 3.13.5 or higher
- pip (Python package installer)

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd Blog
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv .venv
   ```

3. **Activate the virtual environment**
   - **Windows**
     ```bash
     .\.venv\Scripts\activate
     ```
   - **macOS/Linux**
     ```bash
     source .venv/bin/activate
     ```

4. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```

   Or install packages individually:
   ```bash
   pip install Flask==3.1.3
   pip install Flask-SQLAlchemy==3.1.1
   pip install Flask-Login==0.6.3
   ```

## 🚀 Running the Application

1. **Activate the virtual environment** (if not already active)

2. **Run the Flask app**
   ```bash
   python app.py
   ```

3. **Open your browser** and navigate to
   ```
   http://127.0.0.1:5000
   ```

The application will start in debug mode with auto-reload enabled.

## 📁 Project Structure

```
Blog/
├── app.py                    # Main application entry point
├── website/
│   ├── __init__.py          # Flask app factory and database initialization
│   ├── auth.py              # User authentication routes (login, signup, logout)
│   ├── views.py             # Main application routes (home, create post)
│   ├── models.py            # Database models (User, Post)
│   └── templates/
│       ├── base.html        # Base template with navigation
│       ├── home.html        # Home page with posts
│       ├── login.html       # Login page
│       └── signup.html      # Sign-up page
├── instance/                # Instance folder (database files)
├── .venv/                   # Virtual environment directory
└── README.md               # Project documentation
```

## 👥 User Model

Each user has the following attributes:
- **ID**: Unique identifier
- **Email**: User's email address (unique)
- **Username**: User's display name (unique)
- **Password**: Hashed password for security
- **Date Created**: Account creation timestamp
- **Posts**: Relationship to user's posts

## 📝 Post Model

Each blog post contains:
- **ID**: Unique identifier
- **Text**: Post content
- **Date Created**: Post creation timestamp
- **Author**: Foreign key reference to the User

## 🔐 Security Features

- **Password Hashing**: Passwords are securely hashed using Werkzeug's `generate_password_hash()`
- **Login Required**: Protected routes require user authentication
- **CSRF Protection**: Flask handles cross-site request forgery protection
- **Session Management**: Secure session handling with Flask-Login

## 🌐 Available Routes

| Route | Method | Description |
|-------|--------|-------------|
| `/` | GET | Home page (requires login) |
| `/home` | GET | Home page (requires login) |
| `/create-post` | GET, POST | Create a new blog post |
| `/login` | GET, POST | User login |
| `/sign-up` | GET, POST | Create new account |
| `/logout` | GET | User logout (requires login) |

## 🎯 Usage

### Sign Up
1. Navigate to the sign-up page
2. Enter your email, username, and password
3. Confirm your password
4. Click "Sign Up"

### Log In
1. Click on the login link
2. Enter your email and password
3. Check "Remember Me" to stay logged in
4. Click "Log In"

### Create a Post
1. Log in to your account
2. Click "Create Post"
3. Write your blog post
4. Click "Post" to publish

## 🐛 Troubleshooting

### Database Issues
If you encounter database errors, delete the `database.db` file in the `instance/` folder and restart the app. A new database will be created automatically.

### Module Not Found
Ensure the virtual environment is activated and all packages are installed:
```bash
pip install -r requirements.txt
```

### Port Already in Use
If port 5000 is already in use, modify the port in `app.py`:
```python
app.run(debug=True, port=5001)
```

## 📦 Dependencies Summary

| Package | Version | Purpose |
|---------|---------|---------|
| Flask | 3.1.3 | Web framework |
| Flask-SQLAlchemy | 3.1.1 | Database ORM |
| Flask-Login | 0.6.3 | User authentication |
| SQLAlchemy | 2.0.49 | SQL toolkit |
| Werkzeug | 3.1.8 | Security utilities |
| Jinja2 | 3.1.6 | Template engine |

## 🚀 Future Enhancements

- Add post editing and deletion
- Implement user comments on posts
- Add post categories/tags
- User profile pages
- Search functionality
- Email notifications
- Like/favorite posts system

## 📄 License

This project is open source and available under the MIT License.

## 💡 Contributing

Contributions are welcome! Feel free to fork the repository and submit pull requests.

## 📧 Support

For issues or questions, please create an issue in the repository or contact the project maintainer.

---

**Happy Blogging! 🎉**
