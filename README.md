
# Django-Frame-Website

## Features

- Django project skeleton with a dedicated `core` module
- Example app: `social_book` (for social features such as profiles and feeds — extend as needed)
- Static and media directories wired into the repo (`static/`, `media/profile_images/`)
- Templates folder for site-wide HTML
- **Dockerfile** and **docker-compose.yml** for containerized development
- Python dependencies pinned in **requirements.txt**
- Example **.env** file included for reference (replace with your own secrets)

> **Note:** This scaffold is designed to be extended. Exact app capabilities depend on your added code.

---

## Quickstart (without Docker)

### 1. Clone and enter the project
```bash
git clone https://github.com/yangjiaxin121800-droid/Django-Frame-Website.git
cd Django-Frame-Website
```



### **2. Create a virtual environment & install dependencies**



```
python -m venv .venv
# macOS/Linux
source ./.venv/bin/activate
# Windows (PowerShell)
./.venv/Scripts/Activate.ps1

pip install --upgrade pip
pip install -r requirements.txt
```



### **3. Configure environment variables**





Create a .env file in the project root. At minimum:

```
DEBUG=True
SECRET_KEY=change-me
ALLOWED_HOSTS=127.0.0.1,localhost
# If you use a DB other than SQLite, also add its DSN here
```



### **4. Run migrations and start the server**



```
python manage.py migrate
python manage.py createsuperuser  # optional
python manage.py runserver
```

Open http://127.0.0.1:8000/ in your browser.



------





## **Quickstart (with Docker)**





> Requires Docker Desktop or Docker Engine.

```
# Build images and start services
docker compose up --build
```

**Common container commands:**

```
docker compose exec web python manage.py migrate
docker compose exec web python manage.py createsuperuser
```



------





## **Project Structure**



```
Django-Frame-Website/
├─ core/                     # Project-level settings & URLs
├─ social_book/              # Example app for social features
├─ templates/                # HTML templates
├─ static/                   # CSS/JS/images
├─ media/
│  └─ profile_images/        # User-uploaded images (dev)
├─ manage.py                 # Django management script
├─ requirements.txt          # Python dependencies
├─ Dockerfile                # App image
├─ docker-compose.yml        # Local dev stack
└─ .env                      # Environment variables
```



------





## **Settings & Environment**





Typical environment variables:



- DEBUG: True/False
- SECRET_KEY: A long random string
- ALLOWED_HOSTS: Comma-separated hostnames
- Database configuration (if not SQLite)
- Static/media configuration for production





> For production:



- > Set DEBUG=False

- > Use a secure SECRET_KEY

- > Configure persistent DB and storage





------





## **Common Tasks**





**Run tests**

```
python -m pytest   # or python manage.py test
```

**Create a new app**

```
python manage.py startapp myapp
```

**Collect static files (production)**

```
python manage.py collectstatic
```



------





## **Development Tips**





- Keep secrets out of version control — use .env or a secrets manager.
- For Docker, bind-mount code for live reload in dev; build slim images for production.
- Include a .env.example with safe defaults for collaborators.





------





## **Roadmap Ideas**





- Add authentication (login, signup, password reset)
- Flesh out social_book with models, views, and tests
- Add CI/CD pipeline (GitHub Actions)
- Production-ready config (Gunicorn + Nginx, HTTPS, caching)










## **Acknowledgments**





Built with [Django](https://www.djangoproject.com/) and open-source tools.

```
Do you want me to also **add a workflow diagram** in Markdown so it visually explains how this Django scaffold runs? That would make the README more complete.
```
