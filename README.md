# 🛡️ SentinelOS

**A Flask-based cybersecurity utility dashboard for basic file risk checks, cryptographic hashing, file integrity verification, and security-related utilities.**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Render-46A2F1?logo=render&logoColor=white)](https://sentinelos-9dbv.onrender.com)
[![Python](https://img.shields.io/badge/Python-3-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Framework-Flask-black?logo=flask)](https://flask.palletsprojects.com/)

**Live Demo:** https://sentinelos-9dbv.onrender.com

> **Hosting note:** SentinelOS is deployed on Render's Free plan. The service may spin down after inactivity, so the first request can take additional time. Its local SQLite database uses an ephemeral filesystem, so stored scan history may not persist across restarts or redeployments.

---

## 📌 About

SentinelOS is an educational cybersecurity utility project built with Python and Flask. It brings together several basic security-related utilities in a single web dashboard.

The project focuses on practical implementation of file handling, cryptographic hashing, file integrity verification, SQLite database operations, and web application development.

## ✨ Features

### 📁 File Scanner
- Accepts uploaded files for basic risk classification.
- Flags files with selected potentially risky extensions.
- Classifies scan records as `Safe` or `Dangerous`.
- Stores filenames, scan status, and timestamps in SQLite.

**Important:** This is an extension-based check. It does not inspect file contents or detect malware.

### 🔐 SHA-256 Hash Generator
- Generates SHA-256 hashes for uploaded files.
- Uses Python's `hashlib` library.
- Produces a hexadecimal digest for file verification.

### 🛡️ File Integrity Checker
- Calculates the SHA-256 hash of an uploaded file.
- Compares it against a previously generated hash.
- Helps identify whether file contents have changed.

### 🔑 Password Strength Checker
- Evaluates passwords using length and character-type criteria.
- Checks uppercase letters, lowercase letters, numbers, and special characters.
- Classifies password strength as Weak, Medium, or Strong.

### 📞 Phone Number Validator
- Checks whether the entered phone number contains exactly 10 digits.

### 📜 Scan History
- Displays recorded file scans and timestamps.
- Supports updating scan status.
- Supports deleting individual records.
- Supports clearing the scan history.

### 📊 Security Dashboard
- Displays total scans, safe files, and dangerous files.
- Calculates statistics using SQLite scan records.

---

## 📸 Screenshots

### Security Dashboard
![SentinelOS Dashboard](screenshots/dashboard.png.png)

### File Integrity Checker
![File Integrity Checker](screenshots/integrity-checker.png.png)

### Scan History
![Scan History](screenshots/scan-history.png.png)

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| Language | Python |
| Backend | Flask |
| Frontend | HTML, CSS |
| Database | SQLite |
| Cryptographic Hashing | SHA-256, hashlib |
| WSGI Server | Gunicorn |
| Version Control | Git, GitHub |
| Deployment | Render |

---

## 📂 Project Structure

```text
SentinelOS/
│
├── app.py
├── database.py
├── Procfile
├── requirements.txt
├── README.md
│
├── static/
│   └── style.css
│
├── templates/
│   ├── index.html
│   ├── scanner.html
│   ├── phone.html
│   ├── password.html
│   ├── history.html
│   ├── hash.html
│   ├── integrity.html
│   └── report.html
│
└── screenshots/
    ├── dashboard.png.png
    ├── integrity-checker.png.png
    └── scan-history.png.png
```

## ⚙️ Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/ShipraSharma08/SentinelOS.git
cd SentinelOS
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the virtual environment

**Windows:**
```bash
venv\Scripts\activate
```

**Linux / macOS:**
```bash
source venv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the application

```bash
python app.py
```

### 6. Open in your browser

```text
http://127.0.0.1:5000
```

The SQLite database and required scan history table are initialized by the application.

---

## 🔍 How File Integrity Verification Works

1. Upload a file through the SHA-256 Hash Generator.
2. Generate its SHA-256 digest.
3. Keep the generated hash as a reference.
4. Upload the file again through the File Integrity Checker.
5. Enter the original hash.
6. SentinelOS calculates the current hash and compares both values.

If the hashes match, the file contents match the contents represented by the reference hash.

---

## ☁️ Deployment

SentinelOS is deployed using **Render**.

- **Platform:** Render
- **Service:** Web Service
- **Runtime:** Python 3
- **WSGI Server:** Gunicorn
- **Branch:** `main`
- **Live URL:** https://sentinelos-9dbv.onrender.com

### Free-tier considerations

- The service can spin down after a period of inactivity.
- The first request after inactivity may take longer because the service needs to wake up.
- The SQLite database is stored on the service filesystem.
- Data stored on the ephemeral filesystem may be lost after restarts or redeployments.

---

## 🎯 What I Learned

While building SentinelOS, I gained practical experience with:

- Flask routing and form handling.
- Handling file uploads in a web application.
- SHA-256 cryptographic hashing.
- File integrity verification.
- SQLite database operations.
- CRUD operations.
- Dynamic dashboard statistics.
- HTML and CSS for web interfaces.
- Git and GitHub version control.
- Deploying a Python web application using Gunicorn and Render.

---

## ⚠️ Project Scope and Limitations

SentinelOS is an educational cybersecurity utility project.

- File classification is based on selected filename extensions, not malware analysis.
- Password strength evaluation is rule-based and does not guarantee password security.
- Phone number validation checks the 10-digit format only; it does not verify ownership or number registration.
- SHA-256 hash matching verifies content consistency against a supplied reference hash; it does not independently establish file authenticity.
- Free-tier deployment does not guarantee persistent SQLite storage.

SentinelOS should not be considered a replacement for professional antivirus software or enterprise security solutions.

---

## 🚀 Possible Future Improvements

- File hash reputation checking through a trusted threat-intelligence service.
- Advanced file analysis.
- Authentication and user-specific scan history.
- Search and filtering for scan history.
- More security utilities and reporting capabilities.
- Persistent database storage.

---

## 👤 Author

**Shipra Sharma**

B.Tech – Information Technology

Interested in Cybersecurity, Networking, and Software Development.

**GitHub:** https://github.com/ShipraSharma08

**Project Repository:** https://github.com/ShipraSharma08/SentinelOS

**Live Demo:** https://sentinelos-9dbv.onrender.com

---

*Built as a practical project to strengthen my understanding of Python, web development, and cybersecurity fundamentals.*
