Django + React JWT Authentication Notes App
A full-stack application combining Django REST Framework and React to build a simple Notes app with JWT authentication.

Features

User registration and login with JWT tokens
Token refresh handling on the frontend
Protected routes (only authenticated users can access notes)
Create and delete notes tied to the logged-in user
Modern React frontend with Vite
CORS support for API access

Tech Stack

Backend: Django, Django REST Framework, Simple JWT
Frontend: React, Vite, Axios, React Router
Database: SQLite (default Django DB)
Authentication: JSON Web Tokens (JWT)

Project Structure
.
├── backend/
│   ├── api/                # Django app (models, serializers, views, urls)
│   ├── project/            # Django project settings
│   └── manage.py
└── frontend/
    ├── src/                # React components and pages
    ├── public/
    └── package.json

Getting Started
Prerequisites

Python 3.8+
Node.js 18+
npm 8+
Git

Backend Setup (Django)

Clone the repository
git clone https://github.com/your-username/your-repo.git
cd your-repo/backend


Create and activate a virtual environment
python -m venv venv
# macOS/Linux
source venv/bin/activate
# Windows
venv\Scripts\activate


Install dependencies
pip install django djangorestframework djangorestframework-simplejwt python-dotenv


Run migrations
python manage.py makemigrations
python manage.py migrate


Create a superuser (optional)
python manage.py createsuperuser


Start the Django server
python manage.py runserver

The backend API will be available at:http://127.0.0.1:8000/


Frontend Setup (React)

Navigate to the frontend directory
cd ../frontend


Install dependencies
npm install


Start the development server
npm run dev

The React app will be running at:http://localhost:5173/


API Endpoints



Endpoint
Method
Description



/api/register/
POST
Register a new user


/api/token/
POST
Obtain JWT access/refresh tokens


/api/token/refresh/
POST
Refresh JWT access token


/api/notes/
GET
List user notes


/api/notes/
POST
Create a new note


/api/notes/delete/<id>/
DELETE
Delete a note by ID


Authentication Flow

On login: The backend issues an access token and a refresh token, stored in localStorage.
On each request: The Authorization: Bearer <access_token> header is sent via Axios.
If the access token expires: The frontend uses the refresh token to obtain a new access token.

Environment Variables
Create a .env file in the backend directory:
SECRET_KEY=your_secret_key
DEBUG=True

Frontend Structure

Form.jsx: Handles login and registration forms.
ProtectedRoute.jsx: Protects routes requiring authentication.
Note.jsx: Displays a single note.
Home.jsx: Lists notes and handles note creation/deletion.
App.jsx: Routing configuration.

Running in Production

Set DEBUG=False in backend/project/settings.py.

Configure ALLOWED_HOSTS in Django settings.

Use a production-ready server (e.g., Gunicorn, Nginx).

Build the frontend:
cd frontend
npm run build


Serve the static build files or deploy to a service like Vercel or Netlify.


Screenshots
Login Page
Notes Dashboard
Note: Replace screenshots/login.png and screenshots/dashboard.png with actual screenshot paths after adding them to the repository.
Contributing
Contributions are welcome! Please follow these steps:

Fork the repository.
Create a new branch (git checkout -b feature/your-feature).
Commit your changes (git commit -m "Add your feature").
Push to the branch (git push origin feature/your-feature).
Open a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For questions or feedback, open an issue or contact your-email@example.com.

Tip: If you'd like to add specific badges, placeholders for screenshots, or further customization, let me know!
