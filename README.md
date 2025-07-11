<img width="1076" height="432" alt="Screenshot 2025-07-11 at 8 35 10 PM" src="https://github.com/user-attachments/assets/762d9eed-934f-435a-8d7a-dac771bcd4c8" />

# Django + React JWT Authentication Notes App

A full-stack application combining **Django REST Framework** and **React** to build a simple Notes app with **JWT authentication**.



## Features

- User registration and login with JWT tokens
- Token refresh handling on the frontend
- Protected routes (only authenticated users can access notes)
- Create and delete notes tied to the logged-in user
- Modern React frontend with Vite
- CORS support for API access

## Tech Stack

- **Backend**: Django, Django REST Framework, Simple JWT
- **Frontend**: React, Vite, Axios, React Router
- **Database**: SQLite (default Django DB)
- **Authentication**: JSON Web Tokens (JWT)

## Project Structure

```
.
├── backend/
│   ├── api/                # Django app (models, serializers, views, urls)
│   ├── project/            # Django project settings
│   └── manage.py
└── frontend/
    ├── src/                # React components and pages
    ├── public/
    └── package.json
```

## Getting Started

### Prerequisites

- Python 3.8+
- Node.js 18+
- npm 8+
- Git

### Backend Setup (Django)

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo/backend
   ```

2. **Create and activate a virtual environment**

   ```bash
   python -m venv venv
   # macOS/Linux
   source venv/bin/activate
   # Windows
   venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install django djangorestframework djangorestframework-simplejwt python-dotenv
   ```

4. **Run migrations**

   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. **Create a superuser (optional)**

   ```bash
   python manage.py createsuperuser
   ```

6. **Start the Django server**

   ```bash
   python manage.py runserver
   ```

   The backend API will be available at:  
   `http://127.0.0.1:8000/`

### Frontend Setup (React)

1. **Navigate to the frontend directory**

   ```bash
   cd ../frontend
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Start the development server**

   ```bash
   npm run dev
   ```

   The React app will be running at:  
   `http://localhost:5173/`

## API Endpoints

| Endpoint                        | Method | Description                     |
|---------------------------------|--------|---------------------------------|
| `/api/register/`                | POST   | Register a new user             |
| `/api/token/`                   | POST   | Obtain JWT access/refresh tokens|
| `/api/token/refresh/`           | POST   | Refresh JWT access token        |
| `/api/notes/`                   | GET    | List user notes                 |
| `/api/notes/`                   | POST   | Create a new note               |
| `/api/notes/delete/<id>/`       | DELETE | Delete a note by ID             |

## Authentication Flow

- **On login**: The backend issues an access token and a refresh token, stored in `localStorage`.
- **On each request**: The `Authorization: Bearer <access_token>` header is sent via Axios.
- **If the access token expires**: The frontend uses the refresh token to obtain a new access token.

## Environment Variables

Create a `.env` file in the `backend` directory:

```ini
SECRET_KEY=your_secret_key
DEBUG=True
```

## Frontend Structure

- `Form.jsx`: Handles login and registration forms.
- `ProtectedRoute.jsx`: Protects routes requiring authentication.
- `Note.jsx`: Displays a single note.
- `Home.jsx`: Lists notes and handles note creation/deletion.
- `App.jsx`: Routing configuration.

## Running in Production

1. Set `DEBUG=False` in `backend/project/settings.py`.
2. Configure `ALLOWED_HOSTS` in Django settings.
3. Use a production-ready server (e.g., Gunicorn, Nginx).
4. Build the frontend:

   ```bash
   cd frontend
   npm run build
   ```

5. Serve the static build files or deploy to a service like Vercel or Netlify.
<img width="1076" height="432" alt="Screenshot 2025-07-11 at 8 35 10 PM" src="https://github.com/user-attachments/assets/3ded66a1-ef17-4e0c-b8f2-7f160569232c" />

## Screenshots

**Login Page**  

![Login Page](<img width="1116" height="527" alt="Screenshot 2025-07-11 at 8 34 51 PM" src="https://github.com/user-attachments/assets/7718d3df-5c37-4221-970c-127053fa27a7" />)
![Register Page](<img width="1076" height="432" alt="Screenshot 2025-07-11 at 8 35 10 PM" src="https://github.com/user-attachments/assets/3ded66a1-ef17-4e0c-b8f2-7f160569232c" />)
**Notes Dashboard**  <img width="1238" height="653" alt="Screenshot 2025-07-11 at 8 33 55 PM" src="https://github.com/user-attachments/assets/38f434c0-ec53-4a27-a932-8d0f4fc7cfe9" />

![Notes Dashboard](<img width="1238" height="653" alt="Screenshot 2025-07-11 at 8 33 55 PM" src="https://github.com/user-attachments/assets/38f434c0-ec53-4a2<img width="2" height="6" alt="Screenshot 2025-07-11 at 8 34 39 PM" src="https://github.com/user-attachments/assets/51125677-71f6-4069-85e0-be235767ea63" />
7-a932-8d0f4fc7cfe9" />)




