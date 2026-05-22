# CPR Lifeline Automation System

## Team Members

1. Rishma Sree Pathakamuri  
2. Michael Nguyen  
3. Thomas Williams  
4. Murtaza Honarpoor  
5. Shreeya Sapkota  
6. Kostyantyn Tymoshchuk
---
## Contact information 
1.rpathakamuri@csus.edu
2.michaelnguyen3@csus.edu
3. thomaslwilliams@csus.edu
4.murtazahonarpoor@csus.edu
5.shreeyasapkota@csus.edu
6. kostyantyntymoshchu@csus.edu

----
# Project Overview

The CPR Lifeline Automation System is a full-stack automation platform developed to simplify and automate CPR course registration management for CPR Lifeline training centers.

The system automatically reads student registration emails from Azure Outlook using the Microsoft Graph API, extracts student information, processes course registrations for BLS, ACLS, and PALS courses, generates RQI-compatible CSV files, uploads files to an SFTP server, synchronizes records with Google Sheets, and automates student reminders.

The project also includes a PyQt5 desktop dashboard that provides real-time analytics, live logs, student tracking, reminder management, location management, and system configuration controls.

This automation reduces manual administrative work, improves processing accuracy, and helps instructors efficiently manage CPR course registrations and communications.

---

# Main Features

- Automated Outlook email reading using Microsoft Graph API
- Student registration extraction from emails
- AHA Atlas automation using Selenium
- Automated student acceptance system
- RQI CSV generation
- SFTP file upload automation
- Google Sheets synchronization
- Automated reminder email system
- PyQt5 analytics dashboard
- Flask web application support
- Student/course/location analytics
- Live log monitoring
- Duplicate registration filtering
- Multi-location support

---

# Technologies Used

## Programming Language
- Python 3.x

## Libraries & Frameworks
- PyQt5
- Flask
- Selenium
- Pandas
- Requests
- MSAL (Microsoft Authentication Library)
- Paramiko
- gspread
- oauth2client
- schedule
- dotenv
- extract-msg

## APIs & Services
- Microsoft Graph API
- Azure Authentication
- Google Sheets API
- SFTP Server
- AHA Atlas System

---

# Project Structure

```text
CPR-Lifeline-Automation/
│
├── app_all_in_one.py
├── dashboard.py
├── app.py
├── azure.py
├── aha_auto_accept.py
├── csv_generator.py
├── google_sheets_reader.py
├── delta_processor.py
├── sftp_upload.py
├── config.py
├── logger.py
├── dropbox_reader.py
├── credentials.json
├── .env
├── requirements.txt
├── README.md
│
├── data/
│   ├── aha_output.csv
│   ├── preprod_cl.csv
│   └── student_progress.csv
│
└── logs/
    └── app.log
```

---

# Installation & Setup

## Step 1: Clone the Repository

```bash
git clone https://github.com/prishmasree1999-crypto/Team-5-achievers.git
cd Team-5-achievers
```

---

## Step 2: Install Python Dependencies

Install all required packages:

```bash
pip install -r requirements.txt
```

Or manually install packages:

```bash
pip install pandas flask pyqt5 selenium requests msal paramiko gspread oauth2client schedule python-dotenv extract-msg webdriver-manager
```

# Environment Configuration

Create a `.env` file in the root project folder.

Example:

```env
SFTP_HOST=your_host
SFTP_PORT=6239
SFTP_USER=your_username
SFTP_PASS=your_password
SFTP_PATH=/uploads/116286
FILE_NAME=preprod_cl.csv
```

# Azure Setup

Update the `config.json` file with:

```json
{
  "azure_client_id": "YOUR_CLIENT_ID",
  "azure_tenant_id": "YOUR_TENANT_ID",
  "aha_user": "YOUR_AHA_USERNAME",
  "aha_pass": "YOUR_AHA_PASSWORD",
  "sftp_host": "YOUR_SFTP_HOST",
  "sftp_user": "YOUR_SFTP_USERNAME",
  "sftp_pass": "YOUR_SFTP_PASSWORD"
}
```

# Google Sheets API Setup

1. Create a Google Cloud Project
2. Enable:
   - Google Sheets API
   - Google Drive API
3. Download service account credentials
4. Save the file as:

```text
credentials.json
```

5. Place it in the project root directory.


# How to Run the Project

## Run the Main Automation Pipeline

This starts:
- Email extraction
- Student processing
- CSV generation
- SFTP upload
- Reminder system

```bash
python app_all_in_one.py
```

## Run the Dashboard Application

Launch the PyQt5 analytics dashboard:

```bash
python dashboard.py
```

Dashboard features include:
- Live logs
- Student analytics
- Reminder controls
- Location management
- Configuration settings
- CSV viewing

---

## Run the Flask Web Application

```bash
python app.py
```

Open browser:

```text
http://127.0.0.1:5000
```

---

# How the System Works

## Step 1: Email Processing
The system connects to Azure Outlook using Microsoft Graph API and fetches CPR registration emails.

## Step 2: Student Extraction
Student information is extracted including:
- Name
- Email
- Course
- Phone number
- Location

## Step 3: AHA Automation
The system uses Selenium to automate AHA Atlas student acceptance.

## Step 4: CSV Generation
RQI-compatible CSV files are generated automatically.

## Step 5: SFTP Upload
Generated CSV files are uploaded to the configured SFTP server.

## Step 6: Google Sheets Sync
Processed student data is synchronized with Google Sheets.

## Step 7: Reminder Automation
Students receive automated reminder emails based on course progress.

---

# Demo Instructions

To reproduce the live demo:

1. Open the dashboard application:
   ```bash
   python dashboard.py
   ```

2. Configure Azure credentials and SFTP settings.

3. Start the automation pipeline.

4. Authenticate with Azure organizational account.

5. Allow the system to:
   - Read Outlook emails
   - Extract student data
   - Generate CSV files
   - Upload files to SFTP
   - Update Google Sheets

6. View:
   - Analytics dashboard
   - Student tables
   - Reminder system
   - Live logs

---

# Dashboard Features

## Dashboard Page
- Automation status
- Student counts
- Course analytics
- Location analytics
- Live logs

## Reminder System
- Manual reminders
- Automated reminders
- Email previews

## Location Management
- Location templates
- Teacher communication tools
- Location mapping

## Analytics
- Student statistics
- Course statistics
- Summary reports

## Settings
- Azure configuration
- AHA credentials
- SFTP settings

# Data Files Generated

| File | Purpose |
|------|----------|
| aha_output.csv | Student registration records |
| preprod_cl.csv | RQI upload file |
| student_progress.csv | Reminder tracking |
| logs.txt | System logs |
| processed_emails.txt | Duplicate filtering |

# Known Issues / Limitations

- Selenium automation depends on AHA website layout stability
- Requires active internet connection
- Azure login requires organizational account
- Google API credentials must remain valid
- SFTP server must be accessible
- Large inboxes may increase processing time

# Future Improvements

- Docker deployment
- Cloud hosting
- Real-time notifications
- Better UI/UX design
- Database integration
- Multi-user authentication
- Mobile dashboard support

# Authors

CSUS Final Project Team

- Rishma Sree Pathakamuri
- Michael Nguyen
- Thomas Williams
- Murtaza Honarpoor
- Shreeya Sapkota
- Kostyantyn Tymoshchuk

---

# License

This project was developed for academic purposes as part of the California State University, Sacramento Final Project Deliverables Package.
