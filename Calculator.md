<!DOCTYPE html>
<html>
<head>
<title>🔥 AI Quiz Master Pro</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
  margin:0;
  font-family:-apple-system;
  background:#0a0a0a;
  color:white;
  text-align:center;
}

h1{
  color:#ff3b3b;
}

.card{
  background:#111;
  margin:15px auto;
  padding:20px;
  border-radius:20px;
  max-width:420px;
  box-shadow:0 0 20px rgba(255,0,0,0.3);
}

input,select,button{
  width:90%;
  padding:12px;
  margin:10px;
  border-radius:10px;
  border:none;
}

button{
  background:#ff3b3b;
  color:white;
}
</style>
</head>

<body>

<h1>🔥 Quiz Master Pro</h1>

<!-- LOGIN -->
<div class="card" id="login">
<h2>Enter Your Name</h2>
<input id="username" placeholder="Your Name">
<button onclick="login()">Start</button>
</div>

<!-- SETUP -->
<div class="card" id="setup" style="display:none">

<select id="subject">
<option>Maths</option>
<option>Science</option>
<option>SST</option>
<option>English</option>
</select>

<select id="count">
<option value="10">10 MCQ</option>
<option value="20">20 MCQ</option>
<option value="50">50 MCQ</option>
</select>

<button onclick="startQuiz()">Start Quiz</button>

</div>

<div id="quiz"></div>
<div id="leaderboard"></div>

<script>

let user="";

// LOGIN
function login(){
  user=document.getElementById("username").value;
  if(user===""){
    alert("Enter name");
    return;
  }
  localStorage.setItem("user",user);
  document.getElementById("login").style.display="none";
  document.getElementById("setup").style.display="block";
}

// QUESTION GENERATOR
function generateQuestions(subject,count){
  let arr=[];
  for(let i=1;i<=count;i++){
    let a=Math.floor(Math.random()*20)+1;
    let b=Math.floor(Math.random()*20)+1;
    let ans=a+b;

    let options=[ans,ans+1,ans-1,ans+2].sort(()=>0.5-Math.random());

    arr.push({
      q:`${a}+${b}=?`,
      options:options,
      answer:ans
    });
  }
  return arr;
}

let selected=[];

function startQuiz(){
  let subject=document.getElementById("subject").value;
  let count=parseInt(document.getElementById("count").value);

  document.getElementById("setup").style.display="none";

  selected=generateQuestions(subject,count);

  let html="";

  selected.forEach((q,i)=>{
    html+=`<div class="card">
    <p>${i+1}. ${q.q}</p>`;

    q.options.forEach(opt=>{
      html+=`<input type="radio" name="q${i}" value="${opt}"> ${opt}<br>`;
    });

    html+="</div>";
  });

  html+=`<button onclick="submitQuiz()">Submit</button>`;

  document.getElementById("quiz").innerHTML=html;
}

// SUBMIT
function submitQuiz(){
  let score=0;

  selected.forEach((q,i)=>{
    let ans=document.querySelector(`input[name="q${i}"]:checked`);
    if(ans && parseInt(ans.value)===q.answer){
      score++;
    }
  });

  let percent=(score/selected.length)*100;

  saveScore(user,percent);

  document.getElementById("quiz").innerHTML=`
  <div class="card">
  <h2>🎯 Result</h2>
  <p>${user}</p>
  <p>Score: ${score}/${selected.length}</p>
  <p>${percent.toFixed(2)}%</p>
  </div>`;

  showLeaderboard();
}

// SAVE SCORE
function saveScore(name,score){
  let data=JSON.parse(localStorage.getItem("scores"))||[];
  data.push({name,score});
  data.sort((a,b)=>b.score-a.score);
  localStorage.setItem("scores",JSON.stringify(data));
}

// SHOW LEADERBOARD
function showLeaderboard(){
  let data=JSON.parse(localStorage.getItem("scores"))||[];

  let html="<div class='card'><h2>🏆 Leaderboard</h2>";

  data.slice(0,5).forEach((p,i)=>{
    html+=`<p>${i+1}. ${p.name} - ${p.score.toFixed(1)}%</p>`;
  });

  html+="</div>";

  document.getElementById("leaderboard").innerHTML=html;
}

</script>

</body>
</html>
