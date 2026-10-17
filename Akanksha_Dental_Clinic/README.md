# SmileCraft Dental Website

A polished, responsive Flask website starter for a dental clinic. Includes service pages/sections, appointment request capture, a password-protected clinic manager, appointment status updates, and photo uploads.

## Before giving this to a client
1. Confirm the clinic's exact name, complete street address, map pin, opening hours, phone number, and services with the owner.
2. Replace sample stock photos with clinic-owned/licensed photos.
3. Add a strong `SECRET_KEY`, `ADMIN_USERNAME`, and `ADMIN_PASSWORD` environment variables before first launch.
4. Test appointment requests and photo uploads on the actual hosted website.
5. Ask the clinic to approve all text, claims, photos, privacy wording and contact details.

## Run locally on Windows
1. Install Python 3.11+ from https://www.python.org/downloads/ (tick "Add Python to PATH").
2. Extract this ZIP, open the `SmileCraft_Dental_Website` folder in VS Code.
3. Open Terminal > New Terminal and run:
   ```powershell
   py -m venv .venv
   .\.venv\Scripts\Activate.ps1
   pip install -r requirements.txt
   $env:SECRET_KEY="Prajwal"
   $env:ADMIN_USERNAME="clinicadmin"
   $env:ADMIN_PASSWORD="Clinic123"
   $env:CLINIC_NAME="Akanksha Dental Clinic"
   $env:CLINIC_ADDRESS="Shop no 5, laxmi complex, gat no 1446, mhetre wasti, Tower Line Rd, Chikhali, pune, Maharashtra 411062"
   $env:CLINIC_PHONE="8483835641"
   $env:CLINIC_MAPS_URL="Shop no 5, laxmi complex, gat no 1446, mhetre wasti, Tower Line Rd, Chikhali, pune, Maharashtra 411062"
   python app.py
   ```
4. Open http://127.0.0.1:5000
5. Admin: http://127.0.0.1:5000/admin/login

If PowerShell blocks activation, run `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` in that terminal, then activate again. You can also use `.\.venv\Scripts\python.exe -m pip install -r requirements.txt`.

## Admin workflow
- Sign in at `/admin/login`.
- View, search and filter appointment requests.
- Call the patient to confirm availability; requests are not automatically confirmed.
- Change status to New, Confirmed, Completed or Cancelled.
- In Photo gallery, select a photo, add an optional caption and upload. The photo appears in the public website gallery.
- Remove photos with the Remove photo button.
- Sign out when finished.

## Deploying
This project is suitable for a persistent Python host such as PythonAnywhere. Create a web app using a supported Python version, upload/push the project, create a virtual environment, install `requirements.txt`, set environment variables, configure the WSGI file to import `app`, set the working directory, and reload. Follow the host's current instructions because dashboard labels can change.

**Important:** SQLite and uploaded images must be stored on persistent storage. Do not deploy to an ephemeral filesystem and assume uploads/database will survive restarts. Configure HTTPS, backups, strong admin credentials and a non-default secret key. Test a form submission and a photo upload after deployment.

## Current details in starter
- Phone: 8483835641
- Hours shown: Monday–Saturday 10 AM–2 PM and 5 PM–10 PM; Sunday/holidays call to confirm.
- Address and Maps URL are placeholders/configurable because the provided search link does not clearly expose a verified street address in this brief.
- Website name "SmileCraft Dental Clinic" is a temporary brand name and must be approved/replaced.

## Production checklist
- [ ] Exact clinic name/address/map pin verified
- [ ] Real logo, colours and clinic photos approved
- [ ] All 19 services approved by clinic
- [ ] Appointment request tested on mobile and desktop
- [ ] Admin credentials changed and kept private
- [ ] HTTPS enabled
- [ ] Database and uploads backup plan established
- [ ] Privacy notice and consent process reviewed
- [ ] Clinic staff trained on appointment manager
