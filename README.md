# Data Entry Desktop App

> A Windows desktop application built with Python and Tkinter. Enables team members to enter, validate, and export company contact data into password-protected Excel files.

![Python](https://img.shields.io/badge/Python-3.8+-blue) ![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey) ![License](https://img.shields.io/badge/License-MIT-green)

---

## Features

- Secure login system with per-user credentials
- Smart autocomplete dropdowns for US cities, states, job positions, and industries
- Live preview panel — see your entry before submitting
- Duplicate detection with user confirmation prompt
- Data saved to password-protected and encrypted `.xlsx` files
- Paste protection on all fields — manual entry only
- Session table shows all entries made in the current session
- Auto-filename based on username and timestamp
- Files organized per user in the `user_data/` directory

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.8+ | Core language |
| Tkinter + ttk | GUI framework |
| xlsxwriter | Create Excel files |
| openpyxl | Append to existing Excel files |
| win32com | Excel password encryption |
| PyInstaller | Package as standalone `.exe` |

---

## Prerequisites

- Windows 10 or 11
- Python 3.8 or higher
- Microsoft Excel installed (required for encryption via win32com)

---

## Installation

### Step 1 — Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/data-entry-app.git
cd data-entry-app
```

### Step 2 — Install dependencies

```bash
pip install -r requirements.txt
```

### Step 3 — Add your logo

Place your `logo.png` file in the project root directory:

```
data-entry-app/
└── logo.png
```

### Step 4 — Run the app

```bash
python data_entry_app.py
```

---

## Building the .exe

### Step 1 — Install PyInstaller

```bash
pip install pyinstaller
```

### Step 2 — Build the executable

```bash
pyinstaller --onefile --windowed --icon=icon.ico data_entry_app.py
```

### Step 3 — Find your executable

```
dist/
└── data_entry_app.exe
```

---

## Project Structure

```
data-entry-app/
├── data_entry_app.py       # Main application
├── requirements.txt        # Python dependencies
├── icon.ico                # App icon
├── logo.png                # Logo image
├── README.md               # This file
├── .gitignore              # Files excluded from Git
├── user_data/              # Auto-created — stores Excel output files
└── docs/
    └── screenshots/
        ├── login.png
        ├── form.png
        └── preview.png
```

---

## How It Works

### Login
Each team member logs in with their username and password. The username is automatically stamped on every entry they submit in the `RA User` field.

### Data Entry
The form has 17 fields covering company and contact information. Dropdowns for Position, City, State, Industry, and Employee Size use smart autocomplete — type a few letters and matching options appear instantly.

### Paste Protection
All fields block paste operations (Ctrl+V, Shift+Insert, right-click) to enforce manual data entry and reduce copy-paste errors.

### File Management
- Each user gets their own `.xlsx` file named `username_YYYY-MM-DD_HH-MM AM/PM.xlsx`
- A new file is created if no file exists within the last hour
- Existing files within the hour are appended to
- All files are saved in the `user_data/` directory

### Encryption
Files are password-protected using Excel's built-in encryption via `win32com`. Requires Microsoft Excel to be installed.

### Duplicate Detection
Before saving, the app checks if the same data was already entered in the current session. If a duplicate is detected, the user is prompted to confirm before saving.

---

## Data Fields

| Field | Type | Validation |
|-------|------|-----------|
| Company Name | Text | Required |
| First Name | Text | Required |
| Last Name | Text | Required |
| E-Mail ID | Text | Valid email format |
| Position | Dropdown | Required |
| City | Dropdown | Required |
| State | Dropdown | Required |
| Status | Text | Required |
| Contact No | Text | 10-digit number |
| Job Posting Link | Text | Required |
| Company Weblink | Text | Required |
| Employee Size | Dropdown | Required |
| Contact Name | Text | Required |
| Designation | Dropdown | Required |
| LinkedIn URL | Text | Required |
| Industry | Dropdown | Required |
| RA User | Auto-filled | Read-only |

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `win32com` error on startup | Run: `pip install pywin32` |
| Logo not loading | Place `logo.png` in the same folder as `data_entry_app.py` |
| Excel encryption fails | Make sure Microsoft Excel is installed |
| App not starting | Run `python data_entry_app.py` from CMD to see the error |
| `.exe` crashes immediately | Rebuild with `--console` flag to see error output |

---

## License

MIT License — free to use, modify, and build on.

---

## Author

**Sharath** — Python desktop application development.  
Building automation tools for data entry workflows.
