# codealpha_tasks-
NEXUS_STORE — Django E-Commerce Store


A premium Django-based e-commerce store project created for the CodeAlpha Full Stack Development Internship Task.

## Features

* Modern Django project structure
* Responsive e-commerce homepage
* Static files integration
* Template rendering system
* Organized app architecture
* Ready for product system integration
* Easy scalability for future development

---

# Technologies Used

* Python
* Django
* HTML5
* CSS3
* JavaScript

---

# Project Setup Guide

## Step 1 — Clone Repository

```bash
git clone https://github.com/your-username/NEXUS_STORE.git
cd NEXUS_STORE
```

---

## Step 2 — Create Virtual Environment

```bash
python -m venv venv
```

Activate virtual environment:

### Windows

```bash
venv\Scripts\activate
```

### Mac/Linux

```bash
source venv/bin/activate
```

---

## Step 3 — Install Django

```bash
pip install django
```

Check Django version:

```bash
django-admin --version
```

---

## Step 4 — Create Django Project

```bash
django-admin startproject core .
```

---

## Step 5 — Create Store App

```bash
python manage.py startapp store
```

---

# Project Structure

```bash
NEXUS_STORE/
│
├── venv/
├── manage.py
├── db.sqlite3
│
├── core/
│   ├── settings.py
│   ├── urls.py
│
├── store/
│   ├── migrations/
│   ├── templates/
│   │   └── store/
│   │       └── index.html
│   │
│   ├── static/
│   │   └── store/
│   │       ├── css/
│   │       ├── js/
│   │       └── images/
│   │
│   ├── models.py
│   ├── views.py
│   ├── urls.py
```

---

# Configure Django Settings

## Register App

Open:

```python
core/settings.py
```

Add:

```python
'store',
```

Inside:

```python
INSTALLED_APPS = [
```

Example:

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    'store',
]
```

---

# Configure Templates

Find:

```python
'DIRS': [],
```

Replace with:

```python
'DIRS': [BASE_DIR / 'templates'],
```

---

# Configure Static Files

Add at bottom of `settings.py`

```python
STATIC_URL = 'static/'

STATICFILES_DIRS = [
    BASE_DIR / "store/static",
]

MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'
```

---

# Create Store URLs

Create:

```python
store/urls.py
```

Add:

```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='home'),
]
```

---

# Configure Main URLs

Open:

```python
core/urls.py
```

Replace everything with:

```python
from django.contrib import admin
from django.urls import path, include
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('store.urls')),
]

if settings.DEBUG:
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

---

# Create View

Open:

```python
store/views.py
```

Add:

```python
from django.shortcuts import render

def home(request):
    return render(request, 'store/index.html')
```

---

# Add HTML File

Create:

```bash
store/templates/store/index.html
```

Paste your full HTML design inside the file.

---

# Run Server

```bash
python manage.py runserver
```

Open browser:

```bash
http://127.0.0.1:8000/
```

---

# Future Improvements

* Product database
* Shopping cart
* Checkout system
* User authentication
* Admin product management
* Payment gateway integration
* Order tracking system

---

# Author

Faizan Shabbir Abbasi

---

# License

This project is created for educational and internship purposes.
