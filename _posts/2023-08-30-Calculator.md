---
toc: true
comments: true
layout: post
title: Yuri's Calculator
description: Yuri's Calculator
courses: { lab: {week: 2}, csa: {week: 2} }
type: hacks
---

<html>
<head>
    <h1>Calculator</h1>
</head>
<body>
    <div id="calculator">
        <input type="text" id="display" disabled><!-- THis sets the button as text and id is to identify specific parameters, disable is used so you cant type in the calculator by text -->
        <button onclick="setattributes('1')">1</button> <!-- First set the button and call the function append to display, then sets the attribute at 1 and when the button 1 is clicked then the append to display is called, when the button is clicked the set attribute function is called and takes the value/attribute linked to that specific value.  -->
        <button onclick="setattributes('2')">2</button>
        <button onclick="setattributes('3')">3</button>
        <button onclick="setattributes('4')">4</button>
        <button onclick="setattributes('5')">5</button>
        <button onclick="setattributes('6')">6</button>
        <button onclick="setattributes('7')">7</button>
        <button onclick="setattributes('8')">8</button>
        <button onclick="setattributes('9')">9</button>
        <button onclick="setattributes('0')">0</button>
        <button onclick="setattributes('+')">+</button>
         <button onclick="setattributes('-')">-</button>
        <button onclick="setattributes('*')">*</button>
        <button onclick="setattributes('/')">/</button>
        <button onclick="clearDisplay()">C</button> <!-- This is a way to clear, how it works is when this button is clicked the clear display function is called it then sets the value displayed to an empty string clearing any previous inputs, then it gets the value by id and clear all of the attributes from the calculator.  -->
        <button onclick="calculate()">=</button> <!-- This is a single-line HTML comment -->
    </div>
    <script> let displayValue = ""; // This lets the display value == nothing
function setattributes(value) {
    displayValue += value;
    document.getElementById("display").value = displayValue; // display value is the way to keep track of the function so if you input 1+2 it converts to a string and you get "1" "+" "2"
}
function clearDisplay() {
    displayValue = "";// This removes the value that was stored previously from the other time you inputted something. 
    document.getElementById("display").value = "";
}
function calculate() {
    try {
        const result = eval(displayValue); // eval() is a js function for math operation, so when you enter those numbers in this will allow you to get an answer becuase it is set in js, so it evaluates the attributes of the numbers that are inputted. 
        document.getElementById("display").value = result;
        displayValue = result.toString(); // Converts Number into String
    } catch (error) {
        document.getElementById("display").value = "Error";// THis error is used to understand if the values inputted are math expressions and if they arent then it displays - 
        displayValue = ""; //however if the catch goes through and you are able to evaluate the error then it means that an error is not present and the value can be displayed.
    }
}
</script>
 <style>
        #calculator { /* The # Refers to the id of the calculator set in the button to style it  */
            width: 300px;
            margin: 0 auto;
            text-align: center;
            display: flex;/* This is a way to set the buttons in a row */
            flex-wrap: wrap; /* This is to rap around if the size is too big */
            justify-content: center;
        }
        #calculator button {
            width: 60px;
            height: 60px;
            margin: 5px;
            background-color:  #0074D9; 
            border: none;
            color: white;
            font-size: 18px;
        }
        #calculator button:hover {
            background-color: #45a049; 
        }
    </style>
</body>
</html>





