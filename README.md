📝 Django + React JWT Authentication Notes App
This is a full-stack application combining Django REST Framework and React to build a simple Notes app with JWT authentication.

✅ Features

User registration and login with JWT tokens
Token refresh handling on the frontend
Protected routes (only authenticated users can access notes)
Create and delete notes tied to the logged-in user
Modern React frontend with Vite
CORS support for API access


🛠️ Tech Stack

Backend: Django, Django REST Framework, Simple JWT
Frontend: React, Vite, Axios, React Router
Database: SQLite (default Django DB)
Authentication: JSON Web Tokens (JWT)


📂 Project Structure
.
├── backend/
│   ├── api/                # Django app (models, serializers, views, urls)
│   ├── project/            # Django project settings
│   └── manage.py
└── frontend/
    ├── src/                # React components and pages
    ├── public/
    └── package.json


🚀 Getting Started
📦 Backend Setup (Django)

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

The backend API will be available at:👉 http://127.0.0.1:8000/



⚛️ Frontend Setup (React)

Install dependencies
cd frontend
npm install


Start the development server
npm run dev

The React app will be running at:👉 http://localhost:5173/



🌐 API Endpoints

User RegistrationPOST /api/register/ (you may need to create this route)

Token Obtain PairPOST /api/token/

Token RefreshPOST /api/token/refresh/

Notes CRUD  

GET /api/notes/ – list user notes  
POST /api/notes/ – create a new note  
DELETE /api/notes/delete/<id>/ – delete a note by ID




🔑 Authentication Flow

✅ On login:  

The backend issues an access token and a refresh token.  
Tokens are saved in localStorage.


✅ On each request:  

The Authorization: Bearer <access_token> header is automatically sent via Axios.


✅ If the access token expires:  

The frontend automatically refreshes it using the refresh token.




📝 Environment Variables
Create a .env file in your Django backend to store secrets:
SECRET_KEY=your_secret_key
DEBUG=True


🧩 Frontend Structure

Form.jsx: Handles login and registration forms.  
ProtectedRoute.jsx: Protects routes requiring authentication.  
Note.jsx: Displays a single note.  
Home.jsx: Lists notes and handles note creation/deletion.  
App.jsx: Routing configuration.


✅ Running in Production

Set DEBUG=False in Django settings.  

Set ALLOWED_HOSTS appropriately.  

Use a production-ready server (e.g., Gunicorn, Nginx).  

Build the frontend:
npm run build


Serve the static build files or deploy to a service like Vercel or Netlify.



📸 Screenshots
Login Page:(Add screenshot here)
Notes Dashboard:(Add screenshot here)

🤝 Contributing
Feel free to open issues or submit pull requests!

✅ Tip
If you’d like, I can help you tailor this further or create a version with placeholder screenshots and badges. Just let me know!
