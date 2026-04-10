<!DOCTYPE html>

<html>

<head>

<title>My Calculator</title>

<style>

body {

  text-align: center;

  font-family: Arial;

}

input {

  width: 200px;

  height: 40px;

  font-size: 20px;

}

button {

  width: 50px;

  height: 50px;

  font-size: 18px;

  margin: 5px;

}

</style>

</head>

<body>



<h1>Free Calculator</h1>



<input type="text" id="result" disabled><br><br>



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

</script>



</body>

</html>