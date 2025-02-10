## Architecture

This project is structured as a Django web application. While the code might contain separate "frontend" and "backend" folders, for running the project as a single application with Django templates, you should focus on the **"backend"** directory which contains the core Django project settings and `manage.py` file used to run the development server.

The architecture is essentially monolithic for a template-driven Django application:

1.  **Django Application (within the "backend" folder):**
    *   Handles both backend logic (web scraping, data processing, database interaction) and frontend rendering (using Django templates).
    *   Web scraping tasks for Amazon and Flipkart are managed within Django.
    *   Scraped data is stored in a MySQL database.
    *   Django views and templates within this project are used to create and render the user interface.

## Setup and Installation

**Project Setup:**

1.  **Clone the repository:**

    ```bash
    git clone [https://github.com/franciscse/Price-Tracker.git](https://github.com/franciscse/Price-Tracker.git)
    cd Price-Tracker
    ```

2.  **Create a virtual environment (recommended):**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Linux/macOS
    venv\Scripts\activate  # On Windows
    ```

3.  **Install Python Dependencies:**

    Install all required Python packages from the `requirements.txt` file (located in the main `Price-Tracker` directory):

    ```bash
    pip install -r requirements.txt
    ```

4.  **Set up MySQL Database:**

      * **Install MySQL Server:** If you don't have MySQL installed, follow the instructions for your operating system to install MySQL Server.

      * **Create a Database:** Create a MySQL database for your project (e.g., `price_tracker_db`).

      * **Configure Database Settings:**  Modify the `DATABASES` setting in your **`backend/settings.py`** file.  This is important, make sure you are editing the `settings.py` file located within the **`backend`** directory.  Configure the settings to connect to your MySQL database.  You'll need to provide your database name, user, password, host, and port.

        ```python
        DATABASES = {
            'default': {
                'ENGINE': 'django.db.backends.mysql',
                'NAME': 'price_tracker_db',  # Your database name
                'USER': 'your_mysql_user',    # Your MySQL username
                'PASSWORD': 'your_mysql_password', # Your MySQL password
                'HOST': 'localhost',          # Database host (usually localhost)
                'PORT': '3306',              # MySQL default port
            }
        }
        ```

5.  **Run Database Migrations:**

    Navigate to the **`backend`** directory:

    ```bash
    cd backend
    ```

    Then run migrations:

    ```bash
    python manage.py migrate
    ```

6.  **Download ChromeDriver:**

    For Amazon scraping (using Selenium), you need to download ChromeDriver that is compatible with your Chrome browser version.

      * Download it from: [https://chromedriver.chromium.org/downloads](https://www.google.com/url?sa=E&source=gmail&q=https://chromedriver.chromium.org/downloads)
      * Place the `chromedriver` executable in a directory that is in your system's `PATH` environment variable or in the **`backend`** directory.

7.  **Run the Django development server:**

    From the **`backend`** directory, run:

    ```bash
    python manage.py runserver
    ```

    The web application will be accessible at `http://localhost:8000`.

**Note on Project Structure:**

While the repository contains both "frontend" and "backend" folders and `manage.py` in each, for a basic Django application using templates, you primarily need to focus on running the Django project located in the **`backend`** folder.  The "frontend" folder might be an artifact from a different project setup or an attempt to separate concerns that is not fully implemented in this template-based project.

## How to Run this Project - Video Guide

For a visual guide on setting up and running this project, please refer to this YouTube video:

[![How to Run Price Tracker Project](about:sanitized)](https://www.youtube.com/watch?v=OsZDwMpFR0Y)

[Link to YouTube Video: [https://www.youtube.com/watch?v=OsZDwMpFR0Y](https://www.youtube.com/watch?v=OsZDwMpFR0Y)]

## Usage

1.  **Start the Django development server** (if not already running). **Make sure you are in the `backend` directory** before running: `python manage.py runserver`.
2.  **Access the Price Tracker Web Application:** Open your web browser and go to `http://localhost:8000`.
3.  **Interact with the User Interface:** Use the web interface to browse tracked products from Amazon and Flipkart.



**Disclaimer:** Web scraping can be against the terms of service of websites. Use this price tracker responsibly and ethically. Be mindful of website load and avoid excessive scraping that could harm the target websites. Always check the website's `robots.txt` and terms of service before scraping.

**franciscse**
