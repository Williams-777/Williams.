<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f5f5f5;
        }

        .calculator {
            width: 300px;
            border: 2px solid #ccc;
            border-radius: 10px;
            background-color: #fff;
            padding: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        .display {
            width: 100%;
            height: 50px;
            font-size: 30px;
            text-align: right;
            margin-bottom: 10px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f5f5f5;
            color: #333;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .button {
            padding: 20px;
            font-size: 20px;
            background-color: #f0f0f0;
            border: 1px solid #ccc;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.2s;
        }

        .button:hover {
            background-color: #ddd;
        }

        .equal {
            background-color: #4CAF50;
            color: white;
            grid-column: span 2;
        }

        .equal:hover {
            background-color: #45a049;
        }

        button:active {
            transform: scale(0.98);
        }
    </style>
</head>
<body>

    <div class="calculator">
        <input type="text" id="display" class="display" disabled />
        <div class="buttons">
            <button class="button" onclick="appendToDisplay('7')">7</button>
            <button class="button" onclick="appendToDisplay('8')">8</button>
            <button class="button" onclick="appendToDisplay('9')">9</button>
            <button class="button" onclick="appendToDisplay('/')">/</button>

            <button class="button" onclick="appendToDisplay('4')">4</button>
            <button class="button" onclick="appendToDisplay('5')">5</button>
            <button class="button" onclick="appendToDisplay('6')">6</button>
            <button class="button" onclick="appendToDisplay('*')">*</button>

            <button class="button" onclick="appendToDisplay('1')">1</button>
            <button class="button" onclick="appendToDisplay('2')">2</button>
            <button class="button" onclick="appendToDisplay('3')">3</button>
            <button class="button" onclick="appendToDisplay('-')">-</button>

            <button class="button" onclick="appendToDisplay('0')">0</button>
            <button class="button" onclick="appendToDisplay('.')">.</button>
            <button class="button" onclick="clearDisplay()">C</button>
            <button class="button" onclick="appendToDisplay('+')">+</button>
            
            <button class="button equal" onclick="calculate()">=</button>
        </div>
    </div>

    <script>
        let display = document.getElementById('display');

        // Append a value to the display
        function appendToDisplay(value) {
            display.value += value;
        }

        // Clear the display
        function clearDisplay() {
            display.value = '';
        }

        // Perform the calculation
        function calculate() {
            try {
                display.value = eval(display.value);
            } catch (error) {
                display.value = 'Error';
            }
        }
    </script>

</body>
</html>
