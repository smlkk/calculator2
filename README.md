<!DOCTYPE html>
<html>

<head>
    <title>Hesap Makinası</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
        }

        #calculator {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 10px;
            width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            background-color: #fff;
        }

        input[type="text"] {
            grid-column: span 4;
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            box-sizing: border-box;
            font-size: 16px;
            text-align: right;
            color: #333;
            border: none;
            border-bottom: 2px solid #ccc;
            outline: none;
        }

        input[type="button"] {
            width: 100%;
            padding: 15px;
            box-sizing: border-box;
            cursor: pointer;
            font-size: 16px;
            color: #fff;
            border: none;
            border-radius: 5px;
            outline: none;
        }

        input[type="button"]:hover {
            background-color: #007BFF;
        }

        input[type="button"]:active {
            background-color: #0056b3;
        }

        input[value="="] {
            background-color: #28a745;
        }

        input[value="C"] {
            background-color: #dc3545;
        }

        input[value="0"] {
            grid-column: span 2;
        }
    </style>
</head>

<body>
    <div id="calculator">
        <input type="text" id="display" disabled>
        <input type="button" value="7" onclick="addToDisplay('7')" style="background-color: #007BFF;">
        <input type="button" value="8" onclick="addToDisplay('8')" style="background-color: #007BFF;">
        <input type="button" value="9" onclick="addToDisplay('9')" style="background-color: #007BFF;">
        <input type="button" value="/" onclick="addToDisplay('/')" style="background-color: #007BFF;">
        <input type="button" value="4" onclick="addToDisplay('4')" style="background-color: #007BFF;">
        <input type="button" value="5" onclick="addToDisplay('5')" style="background-color: #007BFF;">
        <input type="button" value="6" onclick="addToDisplay('6')" style="background-color: #007BFF;">
        <input type="button" value="-" onclick="addToDisplay('-')" style="background-color: #007BFF;">
        <input type="button" value="1" onclick="addToDisplay('1')" style="background-color: #007BFF;">
        <input type="button" value="2" onclick="addToDisplay('2')" style="background-color: #007BFF;">
        <input type="button" value="3" onclick="addToDisplay('3')" style="background-color: #007BFF;">
        <input type="button" value="+" onclick="addToDisplay('+')" style="background-color: #007BFF;">
        <input type="button" value="0" onclick="addToDisplay('0')" style="background-color: #007BFF;">
        <input type="button" value="." onclick="addToDisplay('.')"
            style="background-color: #007BFF;">
        <input type="button" value="=" onclick="calculate()" style="background-color: #28a745;">
        <input type="button" value="C" onclick="clearDisplay()" style="background-color: #dc3545;">
    </div>

    <script>
        function addToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function calculate() {
            var expression = document.getElementById('display').value;
            try {
                var result = eval(expression);
                document.getElementById('display').value = result;
            } catch (error) {
                document.getElementById('display').value = 'Hata';
            }
        }
    </script>
</body>

</html>
