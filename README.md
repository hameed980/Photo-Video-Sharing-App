# Photo-Video-Sharing-App

🚀 Project Overview

This is a full-stack photo & video sharing application built with FastAPI on the backend and Streamlit on the frontend.
Users can register, log in, upload images/videos, view content, delete posts, and interact with protected API endpoints.

The project demonstrates real-world backend engineering skills, including authentication, database integration, media handling, and REST API design.

🧱 Features
✅ Backend (FastAPI)

Robust REST API for posts & user management

JWT Authentication (login, protected routes)

CRUD operations for posts

Image & video uploads using ImageKit

SQL Database integration

Pydantic validation models

Error handling & status codes

Auto-generated docs with Swagger UI

🎨 Frontend (Streamlit)

Upload photos/videos

View uploaded posts

Login/logout flow (JWT stored on client side)

Calls FastAPI endpoints

Clean & responsive UI

🛠️ Tech Stack
Backend

FastAPI

Python 3.10+

SQL (PostgreSQL / SQL Server / SQLite)

SQLAlchemy

Pydantic

ImageKit Python SDK

JWT (python-jose)

Frontend

Streamlit

📚 Project Architecture
project/
│── app/
│   ├── main.py
│   ├── models.py
│   ├── schemas.py
│   ├── database.py
│   ├── oauth2.py
│   ├── routers/
│   │    ├── users.py
│   │    ├── auth.py
│   │    ├── posts.py
│── frontend/
│   └── streamlit_app.py
│── requirements.txt
│── README.md

⚙️ Installation & Setup
1️⃣ Clone the Repository
git clone https://github.com/yourusername/photo-video-sharing-app.git
cd photo-video-sharing-app

2️⃣ Create Virtual Environment
python -m venv env
source env/bin/activate   # Mac/Linux
env\Scripts\activate      # Windows

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Set Environment Variables

Create a .env file:

DATABASE_URL=your_db_url
SECRET_KEY=your_secret_key
ALGORITHM=HS256
IMAGEKIT_PUBLIC_KEY=xxx
IMAGEKIT_PRIVATE_KEY=xxx
IMAGEKIT_URL_ENDPOINT=xxx

5️⃣ Run FastAPI Backend
uvicorn app.main:app --reload

6️⃣ Run Streamlit Frontend
cd frontend
streamlit run streamlit_app.py

🔐 API Endpoints Summary
Auth
Method	Endpoint	Description
POST	/auth/login	Login & get JWT token
POST	/users/	User registration
Posts
Method	Endpoint	Auth	Description
GET	/posts/	❌	Get all posts
GET	/posts/{id}	❌	Get a single post
POST	/posts/	✔️	Create post (upload media)
DELETE	/posts/{id}	✔️	Delete post
🏗️ How It Works

User registers → stored in DB

User logs in → JWT token created

Streamlit frontend stores token in session 

Users upload image/video → sent to ImageKit

FastAPI saves metadata in DB

Streamlit displays posts from API


#### Improvements / Future Work

Add comments & likes system

Add role-based authorization

Add user profiles

Add background tasks for video compression

Add Redis caching
