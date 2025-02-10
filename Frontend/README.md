# Price Tracker Frontend

## Overview

This directory contains the frontend of the Price Tracker project. The frontend provides an interactive user interface for tracking and monitoring product prices from Amazon and Flipkart. Built using modern web technologies, it allows users to view product details and pricing trends seamlessly.

---

## Key Features

- **User-Friendly Interface:** Clean and intuitive design for easy navigation.
- **Responsive Design:** Optimized for different screen sizes, including mobile and desktop.
- **API Integration:** Fetches data from the backend to display product details.
- **Dynamic Product Display:** Showcases the latest prices and trends.

---

## Project Structure

```plaintext
frontend/
├── index.html            # Main HTML file
├── css/                   # Stylesheets for the project
│   └── styles.css         # Main CSS file
├── js/                    # JavaScript files
│   └── app.js             # Main JavaScript logic
└── assets/                # Static assets like images and icons
```

---

## Setup and Installation

### Prerequisites

- A modern web browser (Chrome, Firefox, etc.)
- Live Server (optional for local development)

---

### Installation Steps

1. **Navigate to the Frontend Directory:**

   ```bash
   cd frontend
   ```

2. **Open the Application Locally:**

   If you have Live Server installed, run it in the frontend directory to serve the `index.html` file.

   Alternatively, open `index.html` directly in your browser.

   ```bash
   live-server .
   ```

3. **Configure API Endpoint:**

   Update the `API_URL` variable in `js/app.js` to point to your backend server:

   ```javascript
   const API_URL = 'http://localhost:8000/api/products';
   ```

---

## Usage

1. **Launch the Frontend:**

   Open `index.html` in a browser or run Live Server.

2. **Interact with the Application:**
   - View tracked products from Amazon and Flipkart.
   - Monitor pricing trends and offers.

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

Ensure responsible and ethical use when interacting with external APIs or web scraping services. Be mindful of website terms of service and usage guidelines.
