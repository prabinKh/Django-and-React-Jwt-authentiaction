

# Django + React JWT Authentication Notes App

A full-stack application combining **Django REST Framework** and **React** to build a simple Notes app with **JWT authentication**.

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![Django](https://img.shields.io/badge/django-4.2+-green.svg)](https://www.djangoproject.com/)
[![React](https://img.shields.io/badge/react-18.2+-blue.svg)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/vite-5.0+-yellow.svg)](https://vitejs.dev/)

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

## Screenshots

**Login Page**  
![Login Page](screenshots/login.png)

**Notes Dashboard**  
![Notes Dashboard](screenshots/dashboard.png)

*Note: Replace `screenshots/login.png` and `screenshots/dashboard.png` with actual screenshot paths after adding them to the repository.*

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or feedback, open an issue or contact [your-email@example.com](mailto:your-email@example.com).

---

*Tip*: If you'd like to add specific badges, placeholders for screenshots, or further customization, let me know!

