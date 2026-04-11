<!DOCTYPE html>
<html>
<head>
<title>Student Quiz Hub</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
  font-family: Arial;
  background: linear-gradient(135deg,#0f172a,#1e293b);
  color: white;
  text-align: center;
  animation: fadeIn 1s ease-in;
}

@keyframes fadeIn {
  from {opacity:0;}
  to {opacity:1;}
}

.container {
  padding: 20px;
}

select, button {
  padding: 10px;
  margin: 10px;
  font-size: 16px;
  border-radius: 8px;
  border: none;
}

button {
  background: #22c55e;
  color: white;
  transition: 0.3s;
}

button:hover {
  transform: scale(1.1);
}

.question {
  margin: 15px 0;
  text-align: left;
  animation: slideUp 0.5s ease;
}

@keyframes slideUp {
  from {transform: translateY(20px); opacity:0;}
  to {transform: translateY(0); opacity:1;}
}
</style>
</head>

<body>

<h1>📚 Student Quiz Hub</h1>

<div class="container" id="setup">

<select id="subject">
<option>Maths</option>
<option>Science</option>
<option>SST</option>
<option>English</option>
</select>

<select id="count">
<option value="5">5</option>
<option value="10">10</option>
<option value="20">20</option>
</select>

<br>
<button onclick="startQuiz()">Start Quiz</button>

</div>

<div id="quiz"></div>

<script>

let questions = [
{subject:"Maths", q:"2+2=?", options:["3","4","5","6"], answer:"4"},
{subject:"Maths", q:"5x5=?", options:["20","25","30","35"], answer:"25"},
{subject:"Science", q:"H2O is?", options:["Water","Oxygen","Hydrogen","Salt"], answer:"Water"},
{subject:"Science", q:"Sun is?", options:["Planet","Star","Moon","Gas"], answer:"Star"},
{subject:"SST", q:"Capital of India?", options:["Delhi","Mumbai","Kolkata","Chennai"], answer:"Delhi"},
{subject:"English", q:"Opposite of big?", options:["Small","Tall","Short","Fat"], answer:"Small"},
{subject:"Maths", q:"10/2=?", options:["2","3","5","6"], answer:"5"},
{subject:"Science", q:"Earth is?", options:["Star","Planet","Galaxy","Moon"], answer:"Planet"},
{subject:"SST", q:"India got independence in?", options:["1947","1950","1930","1960"], answer:"1947"},
{subject:"English", q:"Plural of child?", options:["Childs","Children","Childes","Child"], answer:"Children"}
];

let selected = [];

function startQuiz(){
  document.getElementById("setup").style.display="none";

  let subject = document.getElementById("subject").value;
  let count = parseInt(document.getElementById("count").value);

  let filtered = questions.filter(q => q.subject === subject);

  selected = filtered.sort(() => 0.5 - Math.random()).slice(0, count);

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
  <h2>🎯 Result</h2>
  <p>Correct: ${score}</p>
  <p>Total: ${selected.length}</p>
  <p>Percentage: ${percent.toFixed(2)}%</p>
  `;
}

</script>

</body>
</html>
