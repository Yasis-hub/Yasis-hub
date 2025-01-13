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
            background-color: #f9f9f9;
        }
        form {
            text-align: center;
            width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
            background-color: #fff;
        }
        input, select, button {
            width: calc(100% - 20px);
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            box-sizing: border-box;
        }
        button {
            cursor: pointer;
            background-color: #007BFF;
            color: #fff;
            border: none;
        }
        button:hover {
            background-color: #0056b3;
        }
        button[type="reset"] {
            background-color: #dc3545;
        }
        button[type="reset"]:hover {
            background-color: #c82333;
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
        <input type="text" id="address" name="address" placeholder="Enter your address" required><br>

        <label for="email">Email:</label><br>
        <input type="email" id="email" name="email" placeholder="Enter your email" required><br>

        <label for="contact">Contact no:</label><br>
        <input type="tel" id="contact" name="contact" placeholder="Enter your contact number" required><br>

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
