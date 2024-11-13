from flask import Flask, request, redirect, url_for, render_template_string
import sqlite3
import os

app = Flask(__name__)

# HTML form template as a string
form_html = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Form</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
        }
        form {
            text-align: center;
            width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body>
    <form method="POST" action="/">
        <h1>Welcome To My Form</h1>
        <label for="first_name">First name:</label><br>
        <input type="text" id="first_name" name="first_name" placeholder="Enter your first name" required><br>

        <label for="middle_name">Middle name:</label><br>
        <input type="text" id="middle_name" name="middle_name" placeholder="Enter your middle name"><br>

        <label for="last_name">Last name:</label><br>
        <input type="text" id="last_name" name="last_name" placeholder="Enter your last name" required><br>

        <label for="dob">Date of Birth:</label><br>
        <input type="date" id="dob" name="dob" required><br>

        <label for="address">Address:</label><br>
        <input type="text" id="address" name="address" placeholder="Enter your Address" required><br>

        <label for="email">Email:</label><br>
        <input type="email" id="email" name="email" placeholder="Enter your Email" required><br>

        <label for="contact">Contact no:</label><br>
        <input type="tel" id="contact" name="contact" required><br>

        <label for="gender">Gender:</label><br>
        <select id="gender" name="gender" required>
            <option value="">Select</option>
            <option value="male">Male</option>
            <option value="female">Female</option>
        </select><br><br>

        <button type="submit">Submit</button>
        <button type="reset">Reset</button>
    </form>
</body>
</html>
"""

# Database initialization function
def init_db():
    if not os.path.exists("users.db"):
        with sqlite3.connect("users.db") as conn:
            conn.execute("""
            CREATE TABLE IF NOT EXISTS users (
                id INTEGER PRIMARY KEY AUTOINCREMENT,
                first_name TEXT,
                middle_name TEXT,
                last_name TEXT,
                dob TEXT,
                address TEXT,
                email TEXT,
                contact TEXT,
                gender TEXT
            )
            """)
            conn.commit()

init_db()  # Initialize the database if it doesn't already exist

@app.route("/", methods=["GET", "POST"])
def form():
    if request.method == "POST":
        # Get form data
        first_name = request.form.get("first_name")
        middle_name = request.form.get("middle_name")
        last_name = request.form.get("last_name")
        dob = request.form.get("dob")
        address = request.form.get("address")
        email = request.form.get("email")
        contact = request.form.get("contact")
        gender = request.form.get("gender")

        # Insert data into the database
        with sqlite3.connect("users.db") as conn:
            cursor = conn.cursor()
            cursor.execute("""
            INSERT INTO users (first_name, middle_name, last_name, dob, address, email, contact, gender)
            VALUES (?, ?, ?, ?, ?, ?, ?, ?)
            """, (first_name, middle_name, last_name, dob, address, email, contact, gender))
            conn.commit()

        # Redirect back to the form page after submission
        return redirect(url_for("form"))

    # Render the form HTML
    return render_template_string(form_html)

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=8080, debug=True)
