# AgriAI 

A complete Django web application for AI-powered agriculture monitoring, pest detection, and crop health assessment.

## 🎯 Features

- **Home Page**: Hero section with platform introduction and navigation
- **Upload & Analysis**: Image upload with AI-powered pest detection and crop health analysis
- **About Page**: Detailed information about the platform and technology stack
- **Contact Page**: Contact form with database storage
- **Django Admin**: Admin panel to view uploaded images and contact messages
- **API Endpoint**: RESTful API for image analysis (`/api/analyze/`)
- **Report Download**: Generate and download analysis reports

## 🛠️ Technology Stack

- **Backend**: Django 5+
- **API**: Django REST Framework
- **Database**: SQLite (default)
- **Frontend**: Bootstrap 5
- **Image Processing**: Pillow

## 📦 Installation & Setup

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)

### Step 1: Create Virtual Environment (Recommended)

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/Mac
python3 -m venv venv
source venv/bin/activate
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3: Database Setup

```bash
# Create database migrations
python manage.py makemigrations

# Apply migrations
python manage.py migrate
```

### Step 4: Create Superuser (Optional - for Admin Panel)

```bash
python manage.py createsuperuser
```

Follow the prompts to create an admin user.

### Step 5: Run Development Server

```bash
python manage.py runserver
```

The application will be available at: `http://127.0.0.1:8000/`

## 📁 Project Structure

```
agriai1/
├── manage.py
├── requirements.txt
├── README.md
├── agri_ai_project/          # Django project settings
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
├── pest_detection/            # Main Django app
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   └── templates/
│       └── pest_detection/
│           ├── base.html
│           ├── home.html
│           ├── about.html
│           ├── upload.html
│           └── contact.html
├── media/                     # User uploaded files
│   └── uploads/
├── static/                    # Static files (CSS, JS)
└── db.sqlite3                 # SQLite database (created after migrations)
```

## 🚀 Usage

### Accessing the Application

1. **Home Page**: `http://127.0.0.1:8000/`
2. **About Page**: `http://127.0.0.1:8000/about/`
3. **Upload Page**: `http://127.0.0.1:8000/upload/`
4. **Contact Page**: `http://127.0.0.1:8000/contact/`
5. **Admin Panel**: `http://127.0.0.1:8000/admin/`

### Using the Upload Feature

1. Navigate to the Upload page
2. Click "Choose File" and select an image (JPG, PNG, or GIF)
3. Click "Analyze Image"
4. View the analysis results:
   - Pest detected
   - Pest type (Harmful/Beneficial)
   - Crop health status (Healthy/Stressed/Diseased)
   - Confidence score
5. Download the analysis report

### API Endpoint

**POST** `/api/analyze/`

Upload an image file for analysis:

```bash
curl -X POST http://127.0.0.1:8000/api/analyze/ \
  -F "image=@path/to/image.jpg" \
  -H "X-CSRFToken: YOUR_CSRF_TOKEN"
```

Response:
```json
{
  "success": true,
  "image_id": 1,
  "image_url": "/media/uploads/2025/01/15/image.jpg",
  "analysis": {
    "pest": "Aphid",
    "type": "Harmful",
    "health": "Stressed",
    "confidence": 0.92
  },
  "message": "Image analyzed successfully"
}
```

## 🗄️ Database Models

### UploadedImage
- Stores uploaded plant/leaf images
- Contains analysis results (pest name, type, health status)
- Tracks upload and analysis timestamps

### ContactMessage
- Stores contact form submissions
- Contains name, email, message, and timestamp
- Tracks read/unread status

## 🔧 Configuration

### Media Files
- Uploaded images are stored in `media/uploads/YYYY/MM/DD/`
- Media URL: `/media/`
- Configured in `settings.py`

### Static Files
- Static files (CSS, JS) are served from `static/`
- Static URL: `/static/`
- In production, use `python manage.py collectstatic`

## 📝 Notes

- **Mock Analysis**: Currently, the platform uses mock/random analysis results for demonstration. In production, integrate with actual AI/ML models.
- **MATLAB Integration**: The platform is designed to integrate with MATLAB's Hyperspectral Imaging Library, Image Processing Toolbox, and Deep Learning Toolbox (conceptually mentioned in About page).
- **Security**: Change `SECRET_KEY` in `settings.py` before deploying to production.
- **File Size**: Maximum upload size is set to 10MB (configurable in `settings.py`).

## 🐛 Troubleshooting

### Migration Issues
```bash
# If migrations fail, try:
python manage.py makemigrations pest_detection
python manage.py migrate
```

### Static Files Not Loading
```bash
# Collect static files
python manage.py collectstatic
```

### Media Files Not Accessible
- Ensure `MEDIA_ROOT` and `MEDIA_URL` are correctly configured in `settings.py`
- In development, the URLs are automatically served (see `urls.py`)

## 📄 License

This project is created for educational and demonstration purposes.

## 👥 Support

For questions or issues, please use the Contact page on the website or create an issue in the repository.

---

**Built with ❤️ using Django and Bootstrap**


