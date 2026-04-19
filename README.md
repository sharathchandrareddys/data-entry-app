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
git clone https://github.com/sharathchandrareddys/data-entry-app.git
cd data-entry-app
```

### Step 2 — Install dependencies

```bash
pip install -r requirements.txt
```

### Step 3 — Add your logo

Place your `logo.png` file in the project root directory.

### Step 4 — Run the app

```bash
python data_entry_app.py
```

---

## Building the .exe

```bash
pip install pyinstaller
pyinstaller --onefile --windowed --icon=icon.ico data_entry_app.py
```

Your `.exe` will be in the `dist/` folder after building.

---

## Project Structure
