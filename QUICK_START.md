# 🚀 Quick Start Guide - How to Run the Code

## Step-by-Step Instructions

### 1. Open Terminal/Command Prompt
Navigate to your project directory:
```bash
cd C:\Users\kinja\OneDrive\Desktop\agriai1
```

### 2. Create Virtual Environment (Recommended)
This keeps your project dependencies isolated:

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**Mac/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

You should see `(venv)` at the beginning of your command prompt.

### 3. Install Dependencies
Install all required Python packages:
```bash
pip install -r requirements.txt
```

This will install:
- Django 5+
- Django REST Framework
- Pillow (for image processing)
- requests (for weather API)

### 4. Set Up Database
Create and apply database migrations:
```bash
python manage.py makemigrations
python manage.py migrate
```

This creates the SQLite database file (`db.sqlite3`) with all necessary tables.

### 5. Create Admin User (Optional)
Create a superuser to access the admin panel:
```bash
python manage.py createsuperuser
```

Follow the prompts to enter:
- Username
- Email (optional)
- Password (twice)

### 6. Start the Development Server
Run the Django development server:
```bash
python manage.py runserver
```

You should see output like:
```
Starting development server at http://127.0.0.1:8000/
Quit the server with CTRL-BREAK.
```

### 7. Access the Application
Open your web browser and visit:

**Main Pages:**
- 🏠 **Home**: http://127.0.0.1:8000/
- ℹ️ **About**: http://127.0.0.1:8000/about/
- 📤 **Upload**: http://127.0.0.1:8000/upload/
- 📧 **Contact**: http://127.0.0.1:8000/contact/

**Smart Farming Features:**
- 🌦️ **Irrigation Advisor**: http://127.0.0.1:8000/irrigation/
- 💰 **Profit Predictor**: http://127.0.0.1:8000/profit/
- 🌱 **Soil & Season**: http://127.0.0.1:8000/soil/

**Admin Panel:**
- 🔐 **Admin**: http://127.0.0.1:8000/admin/

---

## 🎯 Testing the New Features

### Test Irrigation Advisor
1. Go to http://127.0.0.1:8000/irrigation/
2. Enter a city name (e.g., "Mumbai", "Delhi", "Bangalore")
3. Optionally enter a crop type
4. Click "Get Irrigation Advice"
5. View weather summary and irrigation recommendations

### Test Profit Predictor
1. Go to http://127.0.0.1:8000/profit/
2. Enter crop details:
   - Crop Name: "Wheat"
   - Yield: 45 (quintals per hectare)
   - Cost: 35000 (₹ per hectare)
   - MSP: 2015 (₹ per quintal)
3. Click "Add Another Crop" to compare multiple crops
4. Click "Calculate Profits"
5. View the comparison table and chart
6. Download the report

### Test Soil & Season
1. Go to http://127.0.0.1:8000/soil/
2. Browse through different soil types
3. Learn about recommended crops and seasons

---

## ⚠️ Troubleshooting

### Problem: "ModuleNotFoundError: No module named 'django'"
**Solution:** Make sure you've activated the virtual environment and installed dependencies:
```bash
venv\Scripts\activate  # Windows
pip install -r requirements.txt
```

### Problem: "No such table" or database errors
**Solution:** Run migrations:
```bash
python manage.py makemigrations
python manage.py migrate
```

### Problem: Port 8000 already in use
**Solution:** Use a different port:
```bash
python manage.py runserver 8080
```
Then access at http://127.0.0.1:8080/

### Problem: Static files not loading
**Solution:** Collect static files:
```bash
python manage.py collectstatic
```

### Problem: Weather API not working
**Solution:** The app uses mock data by default. To use real weather data:
1. Get a free API key from https://openweathermap.org/api
2. Edit `pest_detection/views.py` line 232
3. Replace `api_key = 'demo_key'` with your actual API key

---

## 📝 Notes

- The server runs in development mode (DEBUG=True)
- Database is SQLite (no separate database server needed)
- Uploaded images are stored in `media/uploads/` directory
- Weather API uses mock data by default (works without API key)
- All features are fully functional and ready to use!

---

## 🛑 Stopping the Server

Press `CTRL+C` (or `CTRL+BREAK` on Windows) in the terminal to stop the server.

---

## ✅ Quick Checklist

- [ ] Virtual environment created and activated
- [ ] Dependencies installed (`pip install -r requirements.txt`)
- [ ] Migrations applied (`python manage.py migrate`)
- [ ] Server running (`python manage.py runserver`)
- [ ] Can access home page at http://127.0.0.1:8000/
- [ ] Can access all three new smart farming features

---

**Happy Coding! 🌾**

