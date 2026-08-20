!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Student Registration</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #74ebd5, #ACB6E5);
            min-height: 100vh;
            margin: 0;
            padding: 40px;
        }

        .container {
            width: 450px;
            margin: auto;
            background-color: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        h1 {
            text-align: center;
            color: #6a11cb;
            margin-bottom: 25px;
        }

        label {
            display: block;
            margin-top: 15px;
            font-weight: bold;
            color: #333;
        }

        input, select {
            width: 100%;
            padding: 12px;
            margin-top: 7px;
            border: 2px solid #b8a9ff;
            border-radius: 8px;
            box-sizing: border-box;
            font-size: 15px;
        }

        input:focus, select:focus {
            border-color: #6a11cb;
            outline: none;
        }

        button {
            padding: 12px 18px;
            margin-top: 20px;
            margin-right: 8px;
            border: none;
            border-radius: 8px;
            color: white;
            font-weight: bold;
            cursor: pointer;
        }

        #displayBtn {
            background-color: #28a745;
        }

        #displayBtn:hover {
            background-color: #218838;
        }

        #removeBtn {
            background-color: #dc3545;
        }

        #removeBtn:hover {
            background-color: #c82333;
        }

        #profile {
            margin-top: 25px;
            padding: 20px;
            background: linear-gradient(135deg, #fff3cd, #d4edda);
            border: 3px solid #6a11cb;
            border-radius: 15px;
        }

        .profile-title {
            text-align: center;
            color: #6a11cb;
        }

        #profile p {
            background-color: white;
            padding: 10px;
            border-radius: 6px;
            margin: 8px 0;
        }
    </style>
</head>

<body>

<div class="container">

    <h1>Student Registration</h1>

    <label>Name:</label>
    <input type="text" id="name" placeholder="Enter your name">

    <label>Register Number:</label>
    <input type="text" id="regno" placeholder="Enter register number">

    <label>Department:</label>
    <input type="text" id="department" placeholder="Enter department">

    <label>Year of Study:</label>
    <select id="year">
        <option value="">Select Year</option>
        <option value="1st Year">1st Year</option>
        <option value="2nd Year">2nd Year</option>
        <option value="3rd Year">3rd Year</option>
        <option value="4th Year">4th Year</option>
    </select>

    <button id="displayBtn">Display Profile</button>
    <button id="removeBtn">Remove Profile</button>

    <div id="profile"></div>

</div>

<script>

    // Selecting HTML elements using getElementById()
    const nameInput = document.getElementById("name");
    const regnoInput = document.getElementById("regno");
    const departmentInput = document.getElementById("department");
    const yearInput = document.getElementById("year");

    const displayBtn = document.getElementById("displayBtn");
    const removeBtn = document.getElementById("removeBtn");
    const profile = document.getElementById("profile");


    // Display Profile button
    displayBtn.addEventListener("click", function() {

        const name = nameInput.value;
        const regno = regnoInput.value;
        const department = departmentInput.value;
        const year = yearInput.value;

        // Check whether all fields are filled
        if (name === "" || regno === "" || department === "" || year === "") {
            alert("Please fill all the fields.");
            return;
        }

        // Clear old profile
        profile.innerHTML = "";

        // Create heading
        const heading = document.createElement("h2");
        heading.textContent = "Student Profile";
        heading.classList.add("profile-title");

        // Create name
        const namePara = document.createElement("p");
        namePara.textContent = "Name: " + name;

        // Create register number
        const regPara = document.createElement("p");
        regPara.textContent = "Register Number: " + regno;

        // Create department
        const deptPara = document.createElement("p");
        deptPara.textContent = "Department: " + department;

        // Create year
        const yearPara = document.createElement("p");
        yearPara.textContent = "Year of Study: " + year;

        // Add elements to profile
        profile.appendChild(heading);
        profile.appendChild(namePara);
        profile.appendChild(regPara);
        profile.appendChild(deptPara);
        profile.appendChild(yearPara);

    });


    // Remove Profile button
    removeBtn.addEventListener("click", function() {

        profile.innerHTML = "";

    });

</script>

</body>
</html>
