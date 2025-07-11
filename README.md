# Django + React JWT Authentication Notes App

This is a full-stack application combining **Django REST Framework** and **React** to build a simple Notes app with **JWT authentication**.

✅ **Features:**
- User registration and login with JWT tokens
- Token refresh handling on the frontend
- Protected routes (only authenticated users can access notes)
- Create and delete notes tied to the logged-in user
- Modern React frontend with Vite
- CORS support for API access

---

## 🛠️ Tech Stack

- **Backend**: Django, Django REST Framework, Simple JWT
- **Frontend**: React, Vite, Axios, React Router
- **Database**: SQLite (default Django DB)
- **Authentication**: JSON Web Tokens (JWT)

---

## 📂 Project Structure
├── backend/
│ ├── api/ # Django app (models, serializers, views, urls)
│ ├── project/ # Django project settings
│ └── manage.py
└── frontend/
├── src/ # React components and pages
├── public/
└── package.json



---

## 🚀 Getting Started

### Backend Setup (Django)

1. **Create and activate a virtual environment**

   ```bash
   python -m venv venv
   source venv/bin/activate  # macOS/Linux
   venv\Scripts\activate     # Windows


```
pip install django djangorestframework djangorestframework-simplejwt python-dotenv


python manage.py makemigrations
python manage.py migrate


python manage.py createsuperuser

python manage.py runserver
http://127.0.0.1:8000/



cd frontend

npm install

npm run dev

http://localhost:5173/```






