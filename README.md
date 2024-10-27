<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title>Designing Front Page</title>
	<style>
		body {
			background-color: grey;
			display: flex;
			justify-content: center; 
			align-items: center; 
			height: 100vh; 
			margin: 0; 
		}
		div {
			width: 250px;
			height: 300px;
			text-align: center; 
			transition: width 0.5s ease-in-out, transform 1s ease-in-out; 
			display: flex;
			flex-direction: column; 
			justify-content: center; 
			background-color: white; 
			border-radius: 10px; 
			box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
		}
		div:hover {
			width: 750px;
			transform: rotate(360deg); 
		}
		input, select {
			width: 90%; 
			margin: 5px ; 
		}
	</style>
</head>

<body>
	<div>
		<form>
			<h1>Welcome To My Form</h1>
			<label for="first_name">First name:</label><br>
			<input type="text" id="first_name" name="first_name" placeholder="Enter your first name" required>
			<br>
			<label for="middle_name">Middle name:</label><br>
			<input type="text" id="middle_name" name="middle_name" placeholder="Enter your middle name">
			<br>
			<label for="last_name">Last name:</label><br>
			<input type="text" id="last_name" name="last_name" placeholder="Enter your last name" required>
			<br>
			<label for="dob">Date of Birth:</label><br>
			<input type="date" id="dob" name="dob" required>
			<br>
			<label for="address">Address:</label><br>
			<input type="text" id="address" name="address" placeholder="Enter your Address" required>
			<br>
			<label for="email">Email:</label><br>
			<input type="email" id="email" name="email" placeholder="Enter your Email" required>
			<br>
			<label for="contact">Contact no:</label><br>
			<input type="tel" id="contact" name="contact" required>
			<br>
			<label for="gender">Gender:</label><br>
			<select id="gender" name="gender" required>
				<option value="male">Male</option>
				<option value="female">Female</option>
			</select>
			<br>
			<input type="submit" value="Submit">
		</form>
	</div>
</body>
</html>
