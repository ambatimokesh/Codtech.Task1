# Codtech.Task1

BODY MASS INDEX APPLICATION.

# HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BMI Calculator</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>BMI Calculator</h1>
        <div class="input-group">
            <label for="height">Height (cm):</label>
            <input type="number" id="height" placeholder="Enter height in cm">
        </div>
        <div class="input-group">
            <label for="weight">Weight (kg):</label>
            <input type="number" id="weight" placeholder="Enter weight in kg">
        </div>
        <button onclick="calculateBMI()">Calculate BMI</button>
        <div id="result"></div>
    </div>
    <script src="app.js"></script>
</body>
</html>


#CSS
/* styles.css */

body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f0f0f0;
}

.container {
    background: #f8d1d1;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 300px;
    text-align: center;
}

h1 {
    margin-bottom: 20px;
}

.input-group {
    margin-bottom: 15px;
}

label {
    display: block;
    margin-bottom: 5px;
}

input {
    width: 100%;
    padding: 8px;
    box-sizing: border-box;
}

button {
    background-color: #030c17;
    color: #fff;
    padding: 10px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #000000;
}

#result {
    margin-top: 20px;
    font-size: 18px;
    font-weight: bold;
}


#JAVASCRIPT
// app.js

function calculateBMI() {
    const height = document.getElementById('height').value;
    const weight = document.getElementById('weight').value;

    if (height === '' || weight === '') {
        alert('Please enter both height and weight');
        return;
    }

    const heightInMeters = height / 100;
    const bmi = (weight / (heightInMeters * heightInMeters)).toFixed(2);

    let resultText = `Your BMI is ${bmi}. `;
    if (bmi < 18.5) {
        resultText += "You are underweight.";
    } else if (bmi >= 18.5 && bmi < 24.9) {
        resultText += "You have a normal weight.";
    } else if (bmi >= 25 && bmi < 29.9) {
        resultText += "You are overweight.";
    } else {
        resultText += "You are obese.";
    }

    document.getElementById('result').innerText = resultText;
}


FEATURES:
* By using this application you can measure your health conditon.
* By using this formula weight / heightInMeters * heightInMeters 
