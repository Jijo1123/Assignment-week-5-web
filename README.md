<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Fundamentals and DOM Manipulation</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Part 3: HTML Structure -->
    <h1 id="heading">JavaScript Assignment</h1>
    <p>Learning JavaScript is fun!</p>
    <div id="dynamic-content"></div>

    <script src="script.js"></script>
</body>
</html>

// Part 1: JavaScript Basics

// Variables and Data Types
let name = "John Doe"; // String
let age = 25; // Number
let isStudent = true; // Boolean
let hobbies = ["Reading", "Coding", "Travelling"]; // Array
let person = { name: "John", age: 25, isStudent: true }; // Object

// Log values and types to the console
console.log("Name:", name, "(Type:", typeof name, ")");
console.log("Age:", age, "(Type:", typeof age, ")");
console.log("Is student:", isStudent, "(Type:", typeof isStudent, ")");
console.log("Hobbies:", hobbies, "(Type:", typeof hobbies, ")");
console.log("Person:", person, "(Type:", typeof person, ")");

// Operators: Simple Calculator Function
function calculator() {
    let num1 = parseFloat(prompt("Enter the first number:"));
    let num2 = parseFloat(prompt("Enter the second number:"));
    let operation = prompt("Choose an operation (+, -, *, /):");

    let result;
    if (isNaN(num1) || isNaN(num2)) {
        alert("Please enter valid numbers.");
        return;
    }

    switch (operation) {
        case "+":
            result = num1 + num2;
            break;
        case "-":
            result = num1 - num2;
            break;
        case "*":
            result = num1 * num2;
            break;
        case "/":
            if (num2 === 0) {
                alert("Cannot divide by zero.");
                return;
            }
            result = num1 / num2;
            break;
        default:
            alert("Invalid operation.");
            return;
    }

    alert("Result: " + result);
}

calculator(); // Call the calculator function

// Functions: Greet User
function greetUser(name) {
    return "Hello, " + name + "!";
}

// Display greeting in HTML
let greetingMessage = greetUser("Alice");
document.getElementById("dynamic-content").innerHTML = "<p>" + greetingMessage + "</p>";

// Part 2: JavaScript Control Structures

// If Statements: Check if eligible to vote
let ageForVoting = prompt("What is your age?");
if (ageForVoting >= 18) {
    alert("You are eligible to vote!");
} else {
    alert("You are not eligible to vote yet.");
}

// Loops: Display numbers from 1 to 10
let olElement = document.createElement("ol");
for (let i = 1; i <= 10; i++) {
    let li = document.createElement("li");
    li.textContent = i;
    olElement.appendChild(li);
}

document.body.appendChild(olElement); // Add the list to the body

// Part 3: Introduction to the DOM

// Selecting and Modifying HTML Elements
document.getElementById("heading").textContent = "JavaScript in Action!";
let newParagraph = document.createElement("p");
newParagraph.textContent = "This content was added dynamically using JavaScript.";
document.getElementById("dynamic-content").appendChild(newParagraph);


body {
    font-family: Arial, sans-serif;
    margin: 20px;
    background-color: #f4f4f4;
}

h1 {
    color: #333;
}

p {
    color: #555;
}

ol {
    background-color: #fff;
    padding: 10px;
    list-style-type: decimal;
}

#dynamic-content {
    margin-top: 20px;
}

