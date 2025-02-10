# Price Tracker Backend (Django Application)

## Overview

This directory contains the core backend of the Price Tracker project. The backend handles web scraping, data processing, and serves web pages using Django. It manages product data tracking from Amazon and Flipkart, storing information in a MySQL database.

---

## Key Features

- **Web Scraping:** Extracts product details, offers, and price history from Amazon and Flipkart.
- **Django Framework:** Provides backend logic and template rendering for the web application.
- **MySQL Integration:** Stores product data and manages historical price records.
- **Template-Based Rendering:** Uses Django templates for frontend generation.

---

## Project Structure

```plaintext
backend/
├── manage.py              # Django project management tool
├── backend/                # Django project settings
│   ├── settings.py         # Project settings, including database configurations
│   ├── urls.py             # URL routing for the application
│   └── wsgi.py             # WSGI entry point for the server
├── templates/              # Django HTML templates for the web interface
└── price_tracker_app/      # Main Django app for price tracking
    ├── models.py           # Database models
    ├── views.py            # Backend logic for handling requests
    ├── urls.py             # App-specific routes
    └── scraper.py          # Web scraping logic for Amazon and Flipkart
```

---

## Setup and Installation

### Prerequisites

- Python 3.7 or higher  
- MySQL 8.0 or higher  
- ChromeDriver for Selenium  

---

### Installation Steps

1. **Navigate to the Backend Directory:**

   ```bash
   cd backend
   ```

2. **Create and Activate Virtual Environment:**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Linux/macOS
   venv\Scripts\activate     # On Windows
   ```

3. **Install Dependencies:**

   ```bash
   pip install -r ../requirements.txt
   ```

4. **Configure Database Settings:**

   Open `backend/settings.py` and modify the `DATABASES` section to match your MySQL configuration:

   ```python
   DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.mysql',
           'NAME': 'price_tracker_db',  # Replace with your database name
           'USER': 'your_mysql_user',    # Replace with your username
           'PASSWORD': 'your_mysql_password', # Replace with your password
           'HOST': 'localhost',          # Database host
           'PORT': '3306',               # Default MySQL port
       }
   }
   ```

5. **Apply Database Migrations:**

   ```bash
   python manage.py migrate
   ```

6. **Run the Development Server:**

   ```bash
   python manage.py runserver
   ```

   Access the app at [http://localhost:8000](http://localhost:8000).

---

## Web Scraping Configuration

### Amazon Scraping

- Ensure you have Chrome and ChromeDriver installed.  
- Download the appropriate version from [ChromeDriver Download](https://chromedriver.chromium.org/downloads).  
- Place `chromedriver` in the `backend` directory or ensure it's in your system PATH.

---

## Usage

1. Start the development server using:

   ```bash
   cd backend
   python manage.py runserver
   ```

2. Open a browser and navigate to [http://localhost:8000](http://localhost:8000).

3. Use the application to track and monitor product prices.

---

## Contributing

1. Fork the repository.  
2. Create a new branch (`git checkout -b feature-branch`).  
3. Commit your changes (`git commit -m 'Add feature'`).  
4. Push to the branch (`git push origin feature-branch`).  
5. Create a pull request.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Disclaimer

Web scraping can violate the terms of service of websites. Use this project responsibly and ethically. Avoid excessive requests and always respect the target website's terms.
