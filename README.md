# Price Tracker for Amazon & Flipkart (Django & MySQL)

## Overview

This project is a web application built with Django and MySQL to track prices of products on Amazon and Flipkart. It allows users to monitor the prices of items they are interested in, identify deals and price drops, and view product categories through a user-friendly web interface created using Django templates (HTML and CSS).

## Key Features

- **Multi-Platform Support:** Tracks product data from both Amazon and Flipkart.
- **Detailed Product Information:** Extracts and stores comprehensive product details including name, image link, product URL, and offer information.
- **Price History Tracking:** Stores historical price data as JSON lists, allowing for tracking price changes over time.
- **Offer Detection:** Extracts and displays offer information when available on product listings.
- **Product Categorization:** Organizes products into categories for browsing.
- **Trending Products:** Identifies and flags products as "trending" (implementation for trending logic would be needed).
- **User-Friendly Web Interface:** Provides a simple and functional web interface using Django templates.
- **Django Backend:** Utilizes Django for handling web scraping, data processing, storage, and serving web pages.
- **MySQL Database Storage:** Persists product data, including price history and categories.

## Features

- **Price Tracking:** Continuously monitors product prices on Amazon and Flipkart.
- **Data Extraction:** Scrapes the following product attributes:
  - Product Name
  - Image Link
  - Product URL
  - Offer Details
  - Price (historical prices stored as JSON lists with dates)
- **Product Categorization:** Allows browsing organized categories.
- **Trending Products Display:** Highlights products marked as trending.
- **Historical Price Data:** Stores and visualizes historical price data (visualization requires implementation).
- **Database Storage:** Uses MySQL to store product data.
- **Scheduled Scraping:** Automated mechanism to update product information regularly.

## Technologies Used

### Backend (Django)

- **Python 3.7+**: The core programming language.
- **Django 4.1.7:** High-level web framework.
- **requests 2.28.2:** For fetching web content (Flipkart).
- **BeautifulSoup4 4.12.2:** For parsing HTML content (Flipkart).
- **Selenium 3.141.0+:** For browser automation (Amazon).
- **Chrome WebDriver:** Required for Selenium.
- **MySQL 8.0+:** For data storage.
- **mysqlclient 2.1.1:** Python MySQL driver.

### Frontend (Django Templates)

- **Django Templates:** Dynamic HTML generation.
- **HTML5:** Page structure.
- **CSS3:** Page styling.

## Python Dependencies

Dependencies are listed in `requirements.txt`. Install them with:

```bash
pip install -r requirements.txt
```

### Key Dependencies

```
beautifulsoup4==4.12.2
bs4==0.0.1
django==4.1.7
mysqlclient==2.1.1
pandas==2.0.0
requests==2.28.2
selenium==3.141.0
```

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
    git clone https://github.com/franciscse/Price-Tracker.git
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

      * Download it from: [ChromeDriver Download](https://chromedriver.chromium.org/downloads)
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

[Link to YouTube Video: [How to Run Price Tracker Project](https://www.youtube.com/watch?v=OsZDwMpFR0Y)]

## Usage

1.  **Start the Django development server** (if not already running). **Make sure you are in the `backend` directory** before running: `python manage.py runserver`.
2.  **Access the Price Tracker Web Application:** Open your web browser and go to `http://localhost:8000`.
3.  **Interact with the User Interface:** Use the web interface to browse tracked products from Amazon and Flipkart.



## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

## Disclaimer

Web scraping can be against the terms of service of websites. Use this price tracker responsibly and ethically. Be mindful of website load and avoid excessive scraping that could harm the target websites. Always check the website's robots.txt and terms of service before scraping.

**franciscse**
