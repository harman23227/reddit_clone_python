# Django Reddit

[![Django CI](https://github.com/madhvi-n/django-reddit/actions/workflows/django.yml/badge.svg)](https://github.com/madhvi-n/django-reddit/actions/workflows/django.yml)
[![CodeQL](https://github.com/madhvi-n/django-reddit/actions/workflows/github-code-scanning/codeql/badge.svg)](https://github.com/madhvi-n/django-reddit/actions/workflows/github-code-scanning/codeql)
[![Python](https://img.shields.io/badge/Python-3.12-blue?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-3.1-brightgreen?style=flat&logo=django&logoColor=white)](https://www.djangoproject.com/)
[![Django Rest Framework](https://img.shields.io/badge/Django_Rest_Framework-3.11-red?style=flat&logo=django&logoColor=white)](https://www.django-rest-framework.org/)
[![Angular](https://img.shields.io/badge/Angular-10-blueviolet?style=flat&logo=angular&logoColor=white)](https://angular.io/)

A **full-featured Reddit clone** using **Django** (backend) and **Angular** (frontend). Users can engage in communities, discussions, and post sharing.

## 🚀 Features

- **Authentication**: Register, login, and manage accounts securely.
- **Posting System**: Create posts and comments, support for groups and threads.
- **Communities (Groups)**: Public, private, and restricted groups support.
- **Voting**: Upvote and downvote posts/comments.
- **Follow System**: Follow users and stay updated with their posts.
- **Moderation Tools**: Report inappropriate content.
- **Bookmarking**: Save favorite posts.
- **Invites and Membership Requests**: Controlled access to groups.

## 📸 Screenshots

![Sign In](screenshots/image01.png?raw=true "Sign In")
![Feed](screenshots/image02.png?raw=true "Feed")
![Group](screenshots/image03.png?raw=true "Group")
![User Feed](screenshots/image04.png?raw=true "User Feed")

## 🔧 Requirements

### Backend
- Python 3.8 or newer
- virtualenv
- WSL (for Windows users)

### Frontend
- Angular 10.2.4 or 10.2.5
- Node.js v10.13+

## ⚙️ Installation Guide

### Backend Setup
```bash
git clone https://github.com/madhvi-n/django-reddit.git
cd django-reddit
virtualenv venv
source venv/bin/activate  # macOS/Linux
venv\Scripts\activate     # Windows
pip install -r requirements.txt
```

Set your secret key:
- Edit `reddit_clone/settings.py`
- Or, use environment variable `SECRET_KEY`

```bash
python manage.py migrate
python manage.py runserver
```

Visit `http://127.0.0.1:8000/`

### Frontend Setup
```bash
cd static/frontend/reddit-app
npm install
ng serve
```

Visit `http://127.0.0.1:4200/`

## 📝 API Docs
- Swagger: `http://127.0.0.1:8000/api/swagger/`
- Redoc: `http://127.0.0.1:8000/api/redoc/`

## 🔐 Environment Variables

Create `.env` file:
```ini
SECRET_KEY=your_secret_key
DEBUG=True
DATABASE_NAME=my_db
DATABASE_USER=my_username
DATABASE_PASSWORD=my_db_password
DATABASE_HOST=localhost
DATABASE_PORT=5432
```

## 🛠️ Management Commands

### Django Shell Example
```python
from django.contrib.auth.models import User
from posts.models import Post
from groups.models import Group

user = User.objects.get(id=1)
post = Post.objects.create(title="Sample Post", content="Post content here", author=user)
group = Group.objects.create(name="Django", description="Official Django community")
```

### Populate Dummy Data
```bash
python manage.py populate_users
python manage.py populate_posts
python manage.py populate_tags
python manage.py populate_groups
```

## 💡 Notes
- Backend runs in WSL (Windows)
- Frontend runs natively on Windows

## 📚 References
- [Install Python 3.8 on Ubuntu](https://linuxize.com/post/how-to-install-python-3-8-on-ubuntu-18-04/)
- [Node.js on Windows](https://www.guru99.com/download-install-node-js.html)
- [Angular 10 Setup](https://v10.angular.io/guide/setup-local)
- [Install Specific Angular CLI](https://stackoverflow.com/questions/44759621/install-specific-version-of-ng-cli)
- [Angular/Node Compatibility](https://stackoverflow.com/questions/60248452/is-there-a-compatibility-list-for-angular-angular-cli-and-node-js)

---

### 🎉 Happy Coding!
