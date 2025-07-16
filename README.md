# Birthday Database Web App

This project is a simple web application for storing and displaying people's birthdays. Built with Python, Flask, SQLite, and Bootstrap, it allows users to add new birthdays and view all stored entries in a user-friendly interface.

## Features

- **Add Birthdays:**  
  Users can submit a person's name, birth month, and day through a web form. Input validation ensures only valid dates are accepted.

- **View Birthdays:**  
  All stored birthdays are displayed on the homepage in a table format.

- **Persistent Storage:**  
  Birthdays are stored in a SQLite database (`birthdays.db`), ensuring data is retained between sessions.

- **Responsive Design:**  
  The interface uses Bootstrap for a clean and responsive layout.

## How It Works

1. **Homepage (`/`):**
    - On a GET request, displays all birthdays from the database.
    - On a POST request, processes the form to add a new birthday after validating the input.

2. **Database:**
    - Uses a SQLite database with a `birthdays` table containing `name`, `month`, and `day` columns.

3. **Templates:**
    - Renders HTML templates (e.g., `index.html`) to display the form and the list of birthdays.

## File Structure

```
birthday/
├── app.py             # Main Flask application
├── birthdays.db       # SQLite database file
├── templates/
│   └── index.html     # HTML template for homepage
├── static/
│   └── styles.css     # (Optional) Custom CSS styles
```

## Getting Started

1. **Install dependencies:**
    ```sh
    pip install flask
    pip install cs50
    ```

2. **Set up the database:**
    - Ensure a `birthdays.db` SQLite database exists with a `birthdays` table:
      ```sql
      CREATE TABLE birthdays (
          id INTEGER PRIMARY KEY AUTOINCREMENT,
          name TEXT NOT NULL,
          month INTEGER NOT NULL,
          day INTEGER NOT NULL
      );
      ```

3. **Run the app:**
    ```sh
    flask run
    ```
    - Visit `http://localhost:5000` in your browser.

## Example Usage

- Enter a name, month, and day in the form and submit.
- The new birthday will appear in the list below the form.

## Notes

- Input validation ensures only valid months (1–12) and days (1–31) are accepted.
- The project can be extended with features like editing or deleting entries.

---

This project is ideal for learning the basics of web development with Flask, working with databases, and handling user input in
