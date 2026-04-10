<!DOCTYPE html>
<html>
<head>
<title>Pro Calculator Hub</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
body {
  font-family: Arial;
  text-align: center;
  background: #0f172a;
  color: white;
}

h1 {
  margin-top: 20px;
}

.container {
  margin-top: 20px;
}

input {
  width: 250px;
  height: 40px;
  font-size: 18px;
  margin: 10px;
  text-align: center;
}

button {
  width: 60px;
  height: 60px;
  font-size: 18px;
  margin: 5px;
  border-radius: 10px;
  border: none;
  background: #22c55e;
  color: white;
}

.section {
  margin-top: 30px;
  padding: 20px;
  border: 1px solid #334155;
  border-radius: 10px;
}
</style>
</head>
<body>

<h1>🔥 Calculator Hub</h1>

<!-- BASIC CALCULATOR -->
<div class="section">
<h2>Basic Calculator</h2>
<input type="text" id="result" disabled><br>

<button onclick="add('1')">1</button>
<button onclick="add('2')">2</button>
<button onclick="add('3')">3</button>
<button onclick="add('+')">+</button><br>

<button onclick="add('4')">4</button>
<button onclick="add('5')">5</button>
<button onclick="add('6')">6</button>
<button onclick="add('-')">-</button><br>

<button onclick="add('7')">7</button>
<button onclick="add('8')">8</button>
<button onclick="add('9')">9</button>
<button onclick="add('*')">*</button><br>

<button onclick="add('0')">0</button>
<button onclick="calculate()">=</button>
<button onclick="clearResult()">C</button>
<button onclick="add('/')">/</button>
</div>

<!-- PERCENTAGE CALCULATOR -->
<div class="section">
<h2>Percentage Calculator</h2>
<input type="number" id="num" placeholder="Enter number">
<input type="number" id="percent" placeholder="%"><br>
<button onclick="calcPercent()">Calculate</button>
<h3 id="percentResult"></h3>
</div>

<!-- AGE CALCULATOR -->
<div class="section">
<h2>Age Calculator</h2>
<input type="date" id="dob"><br>
<button onclick="calcAge()">Find Age</button>
<h3 id="ageResult"></h3>
</div>

<script>
function add(value){
  document.getElementById("result").value += value;
}

function calculate(){
  let x = document.getElementById("result").value;
  document.getElementById("result").value = eval(x);
}

function clearResult(){
  document.getElementById("result").value = "";
}

function calcPercent(){
  let num = document.getElementById("num").value;
  let percent = document.getElementById("percent").value;
  let result = (num * percent) / 100;
  document.getElementById("percentResult").innerText = "Result: " + result;
}

function calcAge(){
  let dob = new Date(document.getElementById("dob").value);
  let today = new Date();
  let age = today.getFullYear() - dob.getFullYear();
  document.getElementById("ageResult").innerText = "Age: " + age + " years";
}
</script>

</body>
</html>
