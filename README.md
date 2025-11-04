# AI-Based Smart Alert and Resource Allocation System (Full Version)

## What is included
- Django project `smartalert`
- App `alertapp` with:
  - DisasterAlert, Resource, Allocation models
  - Simple ML prediction (trained on CSV at runtime)
  - Role support via `UserProfile` (Admin / Officer / Viewer)
  - PDF report generation (ReportLab)
  - CSV export
- `dataset/disaster_data.csv` sample for ML training

## Quick steps to run (EASIEST: use default SQLite)
1. Open VS Code and open this folder.
2. Create & activate a virtual environment:
   - Windows:
     ```bash
     python -m venv venv
     venv\Scripts\activate
     ```
   - macOS / Linux:
     ```bash
     python -m venv venv
     source venv/bin/activate
     ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Apply migrations and create a superuser:
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   python manage.py createsuperuser
   ```
5. Run the development server:
   ```bash
   python manage.py runserver
   ```
6. Open http://127.0.0.1:8000 in your browser.
   - Login using the superuser you created (Admin can access admin panel at /admin/ and assign roles).
   - Default pages: Dashboard, Add Alert, Add Resource, Export, Generate PDF

## Optional: Use PostgreSQL instead of SQLite
1. Install PostgreSQL and create a database (e.g., `smartalertdb`) and a user.
2. Replace `DATABASES` in `smartalert/settings.py` with your PostgreSQL details.
3. Install `psycopg2-binary` and run migrations.

## Files of interest
- `alertapp/ml_model.py` – simple ML training & predict function (trains on CSV each time for simplicity)
- `alertapp/views.py` – views for dashboard, alerts, resources, export, PDF
- `dataset/disaster_data.csv` – sample CSV used by the ML model

---
If you want I can modify the project to use Postgres by default or add a Dockerfile.
