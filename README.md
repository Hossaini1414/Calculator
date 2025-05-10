# Calculator
A practical and simple calculator
<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <title>ماشین حساب ساده</title>
    <style>
        body {
            background-color: rgb(226, 226, 226);
            font-family: sans-serif;
        }
        form {
            width: 220px;
            margin: 100px auto;
            padding: 20px;
            background-color: rgb(226, 226, 226);
            box-shadow: 2px 2px 10px #333;
            border-radius: 18px;
            text-align: center;
        }
        input[type="text"] {
            width: 180px;
            height: 30px;
            margin-bottom: 20px;
            border: 4px inset #fff;
            border-radius: 14px;
            text-align: right;
            padding-right: 8px;
        }
        input[type="button"],
        input[type="reset"] {
            width: 40px;
            height: 40px;
            margin: 4px;
            border-radius: 6px;
            border: none;
            background-color: rgb(226, 226, 226);
            box-shadow: -2px -2px 5px white, 2px 2px 5px #999;
            cursor: pointer;
        }
        .op {
            background-color: brown;
            color: white;
        }
        .color {
            background-color: rgb(78, 75, 75);
            color: white;
        }
    </style>
    <script>
        function display(val) {
            document.getElementById("result").value += val;
        }

        function deleteLast() {
            let result = document.getElementById("result").value;
            document.getElementById("result").value = result.slice(0, -1);
        }

        function calculate() {
            try {
                let result = document.getElementById("result").value;
                result = result.replace(/\^/g, '**');
                let output = eval(result);
                document.getElementById("result").value = output;
            } catch {
                document.getElementById("result").value = "خطا";
            }
        }

        function clearDisplay() {
            document.getElementById("result").value = "";
        }
    </script>
</head>
<body>
    <form onsubmit="return false;">
        <input type="text" id="result" disabled placeholder="0">
        <br>
        <input type="button" value="DEL" onclick="deleteLast()" class="op">
        <input type="button" value="^" onclick="display('^')" class="color">
        <input type="button" value="." onclick="display('.')" class="color">
        <input type="button" value="√" onclick="display('Math.sqrt(')" class="color">
        <br>
        <input type="button" value="7" onclick="display('7')">
        <input type="button" value="8" onclick="display('8')">
        <input type="button" value="9" onclick="display('9')">
        <input type="button" value="+" onclick="display('+')" class="color">
        <br>
        <input type="button" value="4" onclick="display('4')">
        <input type="button" value="5" onclick="display('5')">
        <input type="button" value="6" onclick="display('6')">
        <input type="button" value="-" onclick="display('-')" class="color">
        <br>
        <input type="button" value="1" onclick="display('1')">
        <input type="button" value="2" onclick="display('2')">
        <input type="button" value="3" onclick="display('3')">
        <input type="button" value="×" onclick="display('*')" class="color">
        <br>
        <input type="reset" value="C" onclick="clearDisplay()" class="op">
        <input type="button" value="0" onclick="display('0')">
        <input type="button" value="=" onclick="calculate()" class="color">
        <input type="button" value="÷" onclick="display('/')" class="color">
    </form>
</body>
</html>
