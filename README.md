# CampusXHire (Flask Web App) 🚀


CampusXHire is a Flask-based web application that supports student registration/login, job discovery & application, company/job-post management, and student profile management.

---

## Features

- Student registration with OTP verification
- Student login/logout
- Student profile update (personal details, resume/video resume uploads, portfolio link)
- Skill management (SQLAlchemy relationship)
- Job search + recommended jobs based on skill overlap
- Job application flow
- Admin dashboard pages (templates included)

---

## Tech Stack

- **Backend:** Flask
- **Database:** SQLite (see `instance/`)
- **ORM:** SQLAlchemy
- **Frontend:** HTML/Jinja templates + static CSS/JS

---

## Project Structure (high level)

- `run.py` - app entrypoint
- `app/` - Flask app package
  - `routes/` - route handlers
  - `models/` - SQLAlchemy models
  - `controllers/` - app controllers
  - `extensions/` - shared extensions (db/mail, etc.)
  - `templates/` - Jinja templates
  - `static/` - static assets and uploads
- `instance/` - SQLite database files

---

## Setup & Run Locally

### 1) Create & activate a virtual environment

```bash
python -m venv venv
# Windows
venv\Scripts\activate
```

### 2) Install dependencies

```bash
pip install -r requirements.txt
```

### 3) Configure environment

This project uses configuration under `app/config/`.

If the app expects a database, make sure `instance/campusxhire.db` exists (it is included in the repo).

### 4) Run the application

```bash
python run.py
```

Then open:

- http://127.0.0.1:5000

---

## Uploads

Uploads are stored under `app/static/uploads/` (and subfolders such as resumes/photos/video_resumes).

---

## Notes

### Fix included for skills relationship

While updating a student profile, the app correctly handles the SQLAlchemy relationship for `student.skills` by reading a list from the form (`request.form.getlist("skills")`) and updating the relationship collection.

---

## Deployment

For production, use a WSGI server such as **gunicorn** (Linux) or **waitress** (Windows). Do not use Flask’s built-in server.

---

## License

Add your license here (e.g., MIT). 

