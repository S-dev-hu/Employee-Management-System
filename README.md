# Employee-Management-System
Employee Management System
GitHub Structure
Employee-Management-System/
│
├── app.py
├── database.py
├── requirements.txt
├── README.md
│
├── database/
│   └── employees.db
│
├── screenshots/
│   ├── dashboard.png
│   ├── add_employee.png
│   └── reports.png
│
└── docs/
    └── project_report.pdf
Features

✅ Add Employee

✅ Update Employee

✅ Delete Employee

✅ Search Employee

✅ Employee Reports

✅ SQLite Database

Skills Demonstrated
Python
SQLite
CRUD Operations
Data Management
GUI Development
Problem Solving
README.md
# Employee Management System

## Overview

The Employee Management System is a Python-based desktop application that helps organizations manage employee records efficiently.

## Features

- Add Employee
- Edit Employee Information
- Delete Employee
- Search Employees
- Employee Database
- Reporting

## Technologies

- Python
- Tkinter
- SQLite

## Installation

```bash
git clone https://github.com/yourusername/Employee-Management-System.git
cd Employee-Management-System
pip install -r requirements.txt
python app.py
```

## Skills Demonstrated

- Software Development
- Database Management
- CRUD Operations
- Python Programming
Core Code (app.py)
import sqlite3
from tkinter import *

conn = sqlite3.connect("employees.db")
cursor = conn.cursor()

cursor.execute("""
CREATE TABLE IF NOT EXISTS employees(
id INTEGER PRIMARY KEY,
name TEXT,
department TEXT,
email TEXT
)
""")

conn.commit()

def add_employee():
    cursor.execute(
        "INSERT INTO employees(name,department,email) VALUES(?,?,?)",
        (name.get(), dept.get(), email.get())
    )
    conn.commit()

root = Tk()
root.title("Employee Management System")

Label(root,text="Name").grid(row=0,column=0)
name = Entry(root)
name.grid(row=0,column=1)

Label(root,text="Department").grid(row=1,column=0)
dept = Entry(root)
dept.grid(row=1,column=1)

Label(root,text="Email").grid(row=2,column=0)
email = Entry(root)
email.grid(row=2,column=1)

Button(root,text="Add Employee",command=add_employee).grid(row=3,column=1)

root.mainloop()
