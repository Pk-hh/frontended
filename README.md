# Web Development Visual Course Website

This repository contains the Flask application for the 4-week visual web development course. It serves the interactive slides and course materials, providing a self-hosted platform for learning web development fundamentals.

## Table of Contents
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Local Setup](#local-setup)
- [Deployment](#deployment)
- [Course Content](#course-content)
- [License](#license)

## Features
- **Interactive Slides:** HTML-based slides with visual aids and code examples.
- **Comprehensive Course Material:** Includes HTML, CSS, JavaScript, Responsive Design, and Deployment basics.
- **Self-Hosted:** Can be deployed on various web servers.
- **Easy Navigation:** A central `index.html` provides easy access to all course weeks and slides.

## Prerequisites
Before you begin, ensure you have the following installed:
- **Python 3.x:** The Flask application runs on Python.
- **pip:** Python package installer (usually comes with Python).
- **Git:** For version control and cloning the repository.

## Local Setup
To run this application on your local machine for development or testing:

1. **Clone the repository:**
   ```bash
   git clone <repository_url>
   cd web_dev_course_site
   ```
   (Note: Replace `<repository_url>` with the actual URL if this project is hosted on GitHub or similar.)

2. **Create a virtual environment (recommended):**
   ```bash
   python3 -m venv venv
   ```

3. **Activate the virtual environment:**
   - On macOS/Linux:
     ```bash
     source venv/bin/activate
     ```
   - On Windows:
     ```bash
     .\venv\Scripts\activate
     ```

4. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

5. **Run the Flask application:**
   ```bash
   python src/main.py
   ```

   The application will typically run on `http://127.0.0.1:5000` or `http://localhost:5000`.

## Deployment
For permanent deployment, you will need a web server and a hosting provider. Here are general steps and considerations:

### General Deployment Steps:
1. **Choose a Hosting Provider:** Popular choices include Heroku, AWS, Google Cloud, DigitalOcean, PythonAnywhere, etc. Each has its own deployment process.
2. **Prepare your Application:** Ensure your `requirements.txt` is up-to-date and all necessary files are included.
3. **Set up a Production WSGI Server:** For production, you should use a WSGI server like Gunicorn or uWSGI instead of Flask's built-in development server.
   - Install Gunicorn:
     ```bash
     pip install gunicorn
     ```
   - Run with Gunicorn (example):
     ```bash
     gunicorn -w 4 -b 0.0.0.0:8000 src.main:app
     ```
     (This runs 4 worker processes on port 8000. Adjust as needed.)
4. **Configure a Reverse Proxy (Optional but Recommended):** Use Nginx or Apache to proxy requests to your Gunicorn server. This allows you to serve static files efficiently and handle SSL.
5. **Domain Name and SSL:** Configure your domain name to point to your server and set up SSL certificates (e.g., using Let's Encrypt) for HTTPS.

### Example Deployment (Conceptual - specific steps vary by provider):

**Using a PaaS (Platform as a Service) like Heroku:**
1. **Create a `Procfile`** in the root of your project:
   ```
   web: gunicorn src.main:app
   ```
2. **Push to Heroku Git:**
   ```bash
   heroku create
   git push heroku main
   ```

**Using a VPS (Virtual Private Server) like DigitalOcean/AWS EC2:**
1. **SSH into your server.**
2. **Install Python, pip, Git, and Gunicorn.**
3. **Clone your repository.**
4. **Set up a virtual environment and install dependencies.**
5. **Run Gunicorn** (as shown above) and use a process manager like `systemd` or `supervisor` to keep it running.
6. **Configure Nginx** to serve your Flask app and static files.

## Course Content
The course content is located in the `src/static/` directory. You can access the main course page by navigating to the root URL of the deployed application.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

---
*Authored by Manus AI*

