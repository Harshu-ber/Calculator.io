<!DOCTYPE html>
<html>
<head>
<title>Student Quiz Hub</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
  font-family: Arial;
  background: #0f172a;
  color: white;
  text-align: center;
}

.container {
  padding: 20px;
}

select, button {
  padding: 10px;
  margin: 10px;
  font-size: 16px;
}

.question {
  margin: 15px 0;
  text-align: left;
}

button {
  background: #22c55e;
  border: none;
  border-radius: 8px;
  color: white;
}
</style>
</head>

<body>

<h1>📚 Student Quiz Hub</h1>

<div class="container" id="setup">

<select id="class">
<option>Class 1</option>
<option>Class 2</option>
<option>Class 3</option>
<option>Class 4</option>
<option>Class 5</option>
<option>Class 6</option>
<option>Class 7</option>
<option>Class 8</option>
<option>Class 9</option>
<option>Class 10</option>
</select>

<select id="subject">
<option>Maths</option>
<option>Science</option>
<option>SST</option>
<option>English</option>
</select>

<select id="count">
<option>5</option>
<option>10</option>
<option>20</option>
</select>

<br>
<button onclick="startQuiz()">Start Quiz</button>

</div>

<div id="quiz"></div>

<script>

let questions = [
{
q: "2 + 2 = ?",
options: ["3","4","5","6"],
answer: "4"
},
{
q: "Capital of India?",
options: ["Delhi","Mumbai","Kolkata","Chennai"],
answer: "Delhi"
},
{
q: "Water formula?",
options: ["H2O","CO2","O2","NaCl"],
answer: "H2O"
},
{
q: "5 x 5 = ?",
options: ["10","20","25","30"],
answer: "25"
},
{
q: "Sun is a?",
options: ["Planet","Star","Moon","Galaxy"],
answer: "Star"
}
];

let selected = [];

function startQuiz(){
  document.getElementById("setup").style.display="none";

  let count = document.getElementById("count").value;

  selected = questions.sort(() => 0.5 - Math.random()).slice(0,count);

  let html = "";

  selected.forEach((q,i)=>{
    html += `<div class="question">
    <p>${i+1}. ${q.q}</p>`;

    q.options.forEach(opt=>{
      html += `<input type="radio" name="q${i}" value="${opt}"> ${opt}<br>`;
    });

    html += "</div>";
  });

  html += `<button onclick="submitQuiz()">Submit</button>`;

  document.getElementById("quiz").innerHTML = html;
}

function submitQuiz(){
  let score = 0;

  selected.forEach((q,i)=>{
    let ans = document.querySelector(`input[name="q${i}"]:checked`);
    if(ans && ans.value === q.answer){
      score++;
    }
  });

  let percent = (score/selected.length)*100;

  document.getElementById("quiz").innerHTML = `
  <h2>Result</h2>
  <p>Correct: ${score}</p>
  <p>Total: ${selected.length}</p>
  <p>Percentage: ${percent.toFixed(2)}%</p>
  `;
}

</script>

</body>
</html>
