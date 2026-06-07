<!DOCTYPE html>
<html>
<head>
    <title>Calculator</title>
    <style>
        body{
            display:flex;
            justify-content:center;
            align-items:center;
            height:100vh;
            background:#f0f0f0;
            font-family:Arial,sans-serif;
        }

        .calculator{
            background:#222;
            padding:20px;
            border-radius:10px;
        }

        #display{
            width:100%;
            height:50px;
            font-size:24px;
            text-align:right;
            margin-bottom:10px;
        }

        button{
            width:60px;
            height:60px;
            font-size:20px;
            margin:2px;
            cursor:pointer;
        }
    </style>
</head>
<body>

<div class="calculator">
    <input type="text" id="display" readonly>

    <div>
        <button onclick="clearDisplay()">C</button>
        <button onclick="append('/')">/</button>
        <button onclick="append('*')">*</button>
        <button onclick="append('-')">-</button>
    </div>

    <div>
        <button onclick="append('7')">7</button>
        <button onclick="append('8')">8</button>
        <button onclick="append('9')">9</button>
        <button onclick="append('+')">+</button>
    </div>

    <div>
        <button onclick="append('4')">4</button>
        <button onclick="append('5')">5</button>
        <button onclick="append('6')">6</button>
        <button onclick="calculate()">=</button>
    </div>

    <div>
        <button onclick="append('1')">1</button>
        <button onclick="append('2')">2</button>
        <button onclick="append('3')">3</button>
        <button onclick="append('0')">0</button>
    </div>
</div>

<script>
    let display = document.getElementById("display");

    function append(value){
        display.value += value;
    }

    function clearDisplay(){
        display.value = "";
    }

    function calculate(){
        try{
            display.value = eval(display.value);
        }catch{
            display.value = "Error";
        }
    }
</script>

</body>
</html>
