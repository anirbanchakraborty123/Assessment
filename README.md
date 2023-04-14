## Installation

### Prerequisites

#### 1. Install Python
Install ```python-3.7.2``` and ```python-pip```. Follow the steps from the below reference document based on your Operating System.
Reference: [https://docs.python-guide.org/starting/installation/](https://docs.python-guide.org/starting/installation/)

#### 2. Setup virtual environment
```bash
# Install virtual environment
pip install virtualenv

# Create virtual environment
virtualenv env

# Activate virtual environment
source env/bin/activate
```

#### 3. Clone git repository


#### 4. Install requirements
```bash
pip install -r requirements.txt
```

#### 5. Load sample data into MySQL
```bash
# open mysql bash
mysql -u <mysql-user> -p

# Give the absolute path of the file
mysql> source ~/simple-django-project/world.sql
mysql> exit;

OR ELSE USE PHPMYADMIN MYSQL SERVER USING XAMPP
```
#### 6. Edit project settings
```bash
# open settings file
panorbit/settings.py

# Edit Database configurations with your MySQL configurations.
# Search for DATABASES section.
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'world',
        'USER': '<mysql-user>',
        'PASSWORD': '<mysql-password>',
        'HOST': '<mysql-host>',
        'PORT': '<mysql-port>',
    }
}

# Edit email configurations.
# Search for email configurations
EMAIL_USE_TLS = True
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_HOST_USER = '<your-email>'
EMAIL_HOST_PASSWORD = '<your-email-password>'
EMAIL_PORT = 587

# save the file


```
#### 7. Create admin/superuser for accessing admin panel
```bash
# Make migrations
python manage.py createsuperuser
```
#### 7. Run the server
```bash
# Make migrations
python manage.py makemigrations
python manage.py migrate

# For search feature we need to index certain tables to the haystack. For that run below command.
python manage.py rebuild_index

# Run the server
python manage.py runserver 

```

#### AUTOSEARCH/AUTOCOMPLETE 

![](https://i.ibb.co/7XdKLqt/ZPk-RXNh-Imgur.png)

# URLS
### 1. http://127.0.0.1:8000/signup   ===> for signup
### 2. http://127.0.0.1:8000/login    ===> for login
### 3. http://127.0.0.1:8000/         ===> Dashboard page
### 4. http://127.0.0.1:8000/country  ===> for getting country details
### 2. http://127.0.0.1:8000/logout   ===> for logout
### 2. http://127.0.0.1:8000/admin    ===> for accessing admin page

