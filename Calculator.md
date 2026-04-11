<!DOCTYPE html>
<html>
<head>
<title>🔥 AI Quiz Pro</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
  margin:0;
  font-family:-apple-system, BlinkMacSystemFont;
  background:#0a0a0a;
  color:white;
  text-align:center;
}

h1{
  padding:20px;
  color:#ff3b3b;
}

.card{
  background:#111;
  margin:15px auto;
  padding:20px;
  border-radius:20px;
  max-width:420px;
  box-shadow:0 0 20px rgba(255,0,0,0.3);
  animation:fade 0.6s ease;
}

@keyframes fade{
  from{opacity:0; transform:translateY(20px);}
  to{opacity:1; transform:translateY(0);}
}

select,button{
  width:90%;
  padding:12px;
  margin:10px;
  border-radius:12px;
  border:none;
  font-size:16px;
}

button{
  background:#ff3b3b;
  color:white;
  transition:0.3s;
}

button:hover{
  transform:scale(1.05);
}

.question{
  text-align:left;
  margin:10px 0;
}

.result{
  font-size:20px;
}
</style>
</head>

<body>

<h1>🔥 AI Quiz Pro</h1>

<div class="card" id="setup">

<select id="count">
<option value="10">10 MCQ</option>
<option value="20">20 MCQ</option>
<option value="50">50 MCQ</option>
<option value="100">100 MCQ</option>
</select>

<button onclick="startQuiz()">Start Quiz</button>

</div>

<div id="quiz"></div>

<script>

// MASSIVE QUESTION GENERATOR
function generateQuestions(n){
  let arr = [];
  for(let i=1;i<=n;i++){
    let a = Math.floor(Math.random()*20)+1;
    let b = Math.floor(Math.random()*20)+1;
    let correct = a + b;

    let options = [
      correct,
      correct+1,
      correct-1,
      correct+2
    ].sort(()=>0.5-Math.random());

    arr.push({
      q: `${a} + ${b} = ?`,
      options: options,
      answer: correct
    });
  }
  return arr;
}

let selected=[];

function startQuiz(){
  let count = parseInt(document.getElementById("count").value);

  document.getElementById("setup").style.display="none";

  selected = generateQuestions(count);

  let html="";

  selected.forEach((q,i)=>{
    html+=`<div class="card question">
    <p>${i+1}. ${q.q}</p>`;

    q.options.forEach(opt=>{
      html+=`<input type="radio" name="q${i}" value="${opt}"> ${opt}<br>`;
    });

    html+="</div>";
  });

  html+=`<button onclick="submitQuiz()">Submit</button>`;

  document.getElementById("quiz").innerHTML=html;
}

function submitQuiz(){
  let score=0;

  selected.forEach((q,i)=>{
    let ans=document.querySelector(`input[name="q${i}"]:checked`);
    if(ans && parseInt(ans.value)===q.answer){
      score++;
    }
  });

  let percent=(score/selected.length)*100;

  document.getElementById("quiz").innerHTML=`
  <div class="card result">
  <h2>🎯 Result</h2>
  <p>Correct: ${score}</p>
  <p>Total: ${selected.length}</p>
  <p>Percentage: ${percent.toFixed(2)}%</p>
  </div>`;
}
</script>

</body>
</html>
