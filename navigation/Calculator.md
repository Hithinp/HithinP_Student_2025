---
layout: base
title: Calculator
permalink: /Calculator
---


<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Refined Futuristic Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
        }

        .calculator {
            background-color: #333;
            padding: 20px;
            border-radius: 10px;
            width: 350px;
            box-shadow: 0 4px 10px 0 rgba(0,0,0,0.2);
        }

        .calculator-screen {
            width: 100%;
            height: 60px;
            background-color: #000;
            color: #fff;
            border: none;
            text-align: right;
            padding-right: 20px;
            padding-left: 10px;
            font-size: 2rem;
            border-radius: 8px;
            margin-bottom: 10px;
        }

        .button {
            width: 60px;
            height: 60px;
            margin: 5px;
            font-size: 1.5rem;
            border-radius: 8px;
            border: 1px solid #777;
            cursor: pointer;
            color: white;
        }

        .button-function {
            background-color: #4CAF50;
        }

        .button-clear {
            background-color: #f44336;
        }

        .button-equal {
            background-color: #00E676;
            grid-column: span 2;
        }

        .button-operator, .button-number {
            background-color: #555;
        }

        .calculator-buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
    </style>
</head>
<body>

<div class="calculator">
    <input type="text" class="calculator-screen" id="screen" value="0" disabled>
    <div class="calculator-buttons">
        <!-- Functional buttons -->
        <button class="button button-function">2nd</button>
        <button class="button button-function">M</button>
        <button class="button button-clear" onclick="clearScreen()">C</button>
        <button class="button button-operator" onclick="appendOperator('/')">/</button>

        <!-- Numeric buttons -->
        <button class="button button-number" onclick="appendNumber(7)">7</button>
        <button class="button button-number" onclick="appendNumber(8)">8</button>
        <button class="button button-number" onclick="appendNumber(9)">9</button>
        <button class="button button-operator" onclick="appendOperator('*')">*</button>

        <button class="button button-number" onclick="appendNumber(4)">4</button>
        <button class="button button-number" onclick="appendNumber(5)">5</button>
        <button class="button button-number" onclick="appendNumber(6)">6</button>
        <button class="button button-operator" onclick="appendOperator('-')">-</button>

        <button class="button button-number" onclick="appendNumber(1)">1</button>
        <button class="button button-number" onclick="appendNumber(2)">2</button>
        <button class="button button-number" onclick="appendNumber(3)">3</button>
        <button class="button button-operator" onclick="appendOperator('+')">+</button>

        <button class="button button-number" onclick="appendNumber(0)">0</button>
        <button class="button button-number" onclick="appendNumber('.')">.</button>
        <button class="button button-equal" onclick="calculate()">=</button>
    </div>
</div>

<script>
    let screen = document.getElementById('screen');
    let currentInput = "0";

    function appendNumber(number) {
        if (currentInput === "0" && number !== '.') {
            currentInput = number;
        } else {
            currentInput += number;
        }
        screen.value = currentInput;
    }

    function appendOperator(operator) {
        if(currentInput !== "0") {
            currentInput += operator;
            screen.value = currentInput;
        }
    }

    function clearScreen() {
        currentInput = "0";
        screen.value = currentInput;
    }

    function calculate() {
        try {
            currentInput = eval(currentInput).toString();
            screen.value = currentInput;
        } catch (error) {
            screen.value = "Error";
        }
    }
</script>

</body>
</html>
