# Quick Setup Guide

## 🚀 Quick Start

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Run Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### 3. Create Admin User (Optional)
```bash
python manage.py createsuperuser
```

### 4. Run Server
```bash
python manage.py runserver
```

### 5. Access the Application
- **Home**: http://127.0.0.1:8000/
- **About**: http://127.0.0.1:8000/about/
- **Upload**: http://127.0.0.1:8000/upload/
- **Contact**: http://127.0.0.1:8000/contact/
- **Admin**: http://127.0.0.1:8000/admin/

### 6. New Smart Farming Features
- **Irrigation Advisor**: http://127.0.0.1:8000/irrigation/
- **Profit Predictor**: http://127.0.0.1:8000/profit/
- **Soil & Season**: http://127.0.0.1:8000/soil/

## 📝 Notes

- The application uses SQLite database by default (db.sqlite3)
- Uploaded images are stored in `media/uploads/` directory
- Static files are served from `static/` directory
- Currently uses mock AI analysis (random results for demonstration)

## 🔧 Troubleshooting

### If migrations fail:
```bash
python manage.py makemigrations pest_detection
python manage.py migrate
```

### If static files don't load:
```bash
python manage.py collectstatic
```

### If media files don't work:
- Ensure `media/` directory exists
- Check `MEDIA_ROOT` and `MEDIA_URL` in `settings.py`

## ✅ Verification Checklist

- [ ] Dependencies installed (`pip install -r requirements.txt`)
- [ ] Migrations applied (`python manage.py migrate`)
- [ ] Server running (`python manage.py runserver`)
- [ ] Can access home page
- [ ] Can upload images
- [ ] Can view analysis results
- [ ] Can submit contact form
- [ ] Admin panel accessible (if superuser created)

