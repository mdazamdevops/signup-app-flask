# Simple User Signup & Login Application

### Introduction

Welcome to this full-stack user authentication application. This project was built from the ground up to serve as a practical example of a secure, modern web application. It features a Python backend powered by the Flask framework and a dynamic, user-friendly frontend built with standard HTML, CSS, and JavaScript.

**Project created by Mohd Azam Uddin.**

---
## What is this App?

This application provides a fundamental user authentication system. Its core purpose is to allow new users to create a secure account and for existing users to sign in. It serves as a solid foundation for any web application that requires user management.

**Key Features:**
* Secure user registration with password hashing.
* User login and a personalized welcome dashboard.
* A clean, responsive user interface.

---
## How It Was Built - The Journey

This project started with a simple goal: create a functional signup system. The process evolved as we tackled common development challenges.

#### 1. The Initial Backend
The first version of the application was a simple **Flask** server. Initially, user data was stored in a plain text file called `users.json`. While this worked for a basic prototype, it quickly led to an **"Internal Server Error"** due to file permission issues and the risk of data corruption.

#### 2. Upgrading to a Real Database
To fix the errors and make the application more stable, the backend was upgraded to use a proper database. We chose **SQLite** because it's lightweight and built into Python. The `Flask-SQLAlchemy` library was used to manage the database, which solved all the data storage problems and made the application much more robust.

#### 3. Building the Frontend
The user interface was built with standard **HTML** and **CSS**, with a focus on a clean and modern design. All the user interactions, like submitting forms and showing messages, are handled by **vanilla JavaScript**. A simple Node.js/Express server is used to serve the `index.html` file.

---
## Technologies & Dependencies Used

#### Backend (Python)
* **Flask**: The core web framework for building the API.
* **Flask-SQLAlchemy**: For managing the SQLite database.
* **Flask-CORS**: To handle Cross-Origin Resource Sharing between the frontend and backend.
* **Werkzeug**: For secure password hashing.

#### Frontend
* **HTML5, CSS3, Vanilla JavaScript**: For building the entire client-side user interface and interactions.
* **Node.js & Express.js**: A lightweight backend server is used to serve the static `index.html` file and manage the frontend's local development environment.

---
## How to Run Locally

To run this application on your local machine, you will need to run the backend and frontend in two separate terminals.

#### 1. Run the Backend
```bash
# Navigate to the backend directory
cd backend

# Create and activate a Python virtual environment
python -m venv venv
source venv/bin/activate  # On Windows, use: venv\Scripts\activate

# Install the required packages
pip install -r requirements.txt

# Start the Flask server
python app.py
```
*The backend will be run at `http://localhost:5000`.*

#### 2. Run the Frontend
```bash
# Navigate to the frontend directory
cd frontend

# Install the Node.js dependencies
npm install

# Start the frontend server
npm start
```
*The frontend will be run at `http://localhost:3000`.*

---
## Final Project Structure
```
.
├── backend/
│   ├── app.py
│   ├── requirements.txt
│   └── database.db
└── frontend/
    ├── index.html
    ├── server.js
    └── package.json
```