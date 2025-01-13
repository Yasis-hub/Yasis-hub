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
            background-color: lightgreen;
        }
        form {
            text-align: center;
            width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
            background-color: lightskyblue;
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
        <label>First name:</label><br>
        <input type="text" id="first_name"  placeholder="Enter your first name"><br><br>

        <label>Middle name:</label><br>
        <input type="text" id="middle_name" placeholder="Enter your middle name"><br><br>

        <label for="last_name">Last name:</label><br>
        <input type="text" id="last_name"  placeholder="Enter your last name" ><br><br>

        <label for="dob">Date of Birth:</label><br>
        <input type="date" id="dob" ><br><br>

        <label for="address">Address:</label><br>
        <input type="text" id="address"  placeholder="Enter your address"><br><br>

        <label for="email">Email:</label><br>
        <input type="email" id="email"  placeholder="Enter your email"><br><br>

        <label for="contact">Contact no:</label><br>
        <input type="tel" id="contact"  placeholder="Enter your contact number"><br><br>

        <label>Gender:</label><br>
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
