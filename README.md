<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Magic Teddy Love Link</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{
height:100vh;
overflow:hidden;
display:flex;
justify-content:center;
align-items:center;
background:linear-gradient(-45deg,#0f172a,#1e293b,#312e81,#4c1d95);
background-size:400% 400%;
animation:bgMove 12s ease infinite;
color:white;
}

@keyframes bgMove{
0%{background-position:0% 50%;}
50%{background-position:100% 50%;}
100%{background-position:0% 50%;}
}

.container{
width:95%;
max-width:500px;
padding:25px;
border-radius:30px;
background:rgba(255,255,255,0.08);
backdrop-filter:blur(15px);
box-shadow:0 0 40px rgba(0,0,0,0.5);
text-align:center;
position:relative;
overflow:hidden;
animation:popup 1s ease;
}

@keyframes popup{
0%{
transform:scale(0.7);
opacity:0;
}
100%{
transform:scale(1);
opacity:1;
}
}

.teddy{
width:130px;
height:130px;
margin:auto;
position:relative;
animation:bounce 2s infinite;
}

@keyframes bounce{
0%,100%{
transform:translateY(0px);
}
50%{
transform:translateY(-12px);
}
}

.face{
width:90px;
height:90px;
background:#b87946;
border-radius:50%;
position:absolute;
top:20px;
left:20px;
}

.ear{
width:40px;
height:40px;
background:#b87946;
border-radius:50%;
position:absolute;
}

.ear1{
top:0;
left:0;
}

.ear2{
top:0;
right:0;
}

.eye{
width:8px;
height:8px;
background:black;
border-radius:50%;
position:absolute;
top:35px;
}

.eye1{
left:28px;
}

.eye2{
right:28px;
}

.nose{
width:16px;
height:12px;
background:black;
border-radius:50%;
position:absolute;
top:50px;
left:37px;
}

h1{
margin-top:10px;
font-size:32px;
animation:glow 2s infinite alternate;
}

@keyframes glow{
from{
text-shadow:0 0 10px white;
}
to{
text-shadow:0 0 30px #ff4f8b;
}
}

input{
width:100%;
padding:15px;
border:none;
outline:none;
border-radius:15px;
margin-top:15px;
background:rgba(255,255,255,0.15);
color:white;
font-size:16px;
}

input::placeholder{
color:#ddd;
}

button{
margin-top:18px;
padding:14px 24px;
border:none;
border-radius:16px;
font-size:16px;
font-weight:bold;
cursor:pointer;
transition:0.3s;
}

button:hover{
transform:scale(1.05);
}

.createBtn{
background:#ff4f8b;
color:white;
}

.copyBtn{
background:#7c3aed;
color:white;
}

.hidden{
display:none;
}

.linkBox{
margin-top:25px;
padding:18px;
border-radius:18px;
background:rgba(255,255,255,0.1);
word-break:break-word;
}

.question{
font-size:32px;
margin-bottom:25px;
line-height:1.5;
}

.btnArea{
position:relative;
height:200px;
}

.yesBtn{
background:#22c55e;
color:white;
margin-right:20px;
}

.noBtn{
background:#ef4444;
color:white;
position:absolute;
}

.floaters span{
position:absolute;
bottom:-100px;
animation:floatUp linear infinite;
opacity:0.7;
}

@keyframes floatUp{
0%{
transform:translateY(0) rotate(0deg);
opacity:0;
}
20%{
opacity:1;
}
100%{
transform:translateY(-120vh) rotate(360deg);
opacity:0;
}
}

.celebrationContainer{
width:100%;
height:78vh;
overflow-y:auto;
padding:20px;
}

.cat{
font-size:130px;
animation:dance 0.8s infinite alternate;
}

@keyframes dance{
0%{
transform:rotate(-10deg) scale(1);
}
100%{
transform:rotate(10deg) scale(1.1);
}
}

.finalText{
font-size:45px;
margin-top:20px;
margin-bottom:20px;
color:#ffd166;
animation:glow 1s infinite alternate;
}

.loveLines{
margin-top:25px;
display:flex;
flex-direction:column;
gap:22px;
font-size:20px;
line-height:1.8;
animation:fadeIn 2s ease;
}

.loveLines p{
background:rgba(255,255,255,0.08);
padding:18px;
border-radius:20px;
backdrop-filter:blur(10px);
animation:popup 1s ease;
}

@keyframes fadeIn{
0%{
opacity:0;
transform:translateY(20px);
}
100%{
opacity:1;
transform:translateY(0);
}
}

</style>
</head>

<body>

<div class="floaters" id="floaters"></div>

<div class="container">

<!-- HOME PAGE -->

<div id="homePage">

<div class="teddy">

<div class="ear ear1"></div>
<div class="ear ear2"></div>

<div class="face">
<div class="eye eye1"></div>
<div class="eye eye2"></div>
<div class="nose"></div>
</div>

</div>

<h1>Magic Teddy Link ✨</h1>

<input type="text" id="yourName" placeholder="Your Name">

<input type="text" id="partnerName" placeholder="Partner Name">

<button class="createBtn" onclick="goToLinkPage()">
Create Magic Link ❤️
</button>

</div>

<!-- LINK PAGE -->

<div id="linkPage" class="hidden">

<div class="teddy">

<div class="ear ear1"></div>
<div class="ear ear2"></div>

<div class="face">
<div class="eye eye1"></div>
<div class="eye eye2"></div>
<div class="nose"></div>
</div>

</div>

<h1>Your Link Is Ready ✨</h1>

<div class="linkBox">

<p>Send this magical link ❤️</p>

<input id="magicLink" readonly>

<button class="copyBtn" onclick="copyLink()">
Copy Link ✨
</button>

</div>

</div>

<!-- LOVE PAGE -->

<div id="lovePage" class="hidden">

<div class="question" id="questionText"></div>

<div class="btnArea">

<button class="yesBtn" onclick="showCelebration()">
YES ❤️
</button>

<button class="noBtn" id="noBtn">
NO 💔
</button>

</div>

</div>

<!-- CELEBRATION PAGE -->

<div id="celebrationPage" class="hidden">

<div class="celebrationContainer">

<div class="cat">🐱</div>

<div class="finalText">
Best Decision Ever ❤️
</div>

<div class="loveLines">

<p>✨ A magical moment has officially started ✨</p>

<p>💖 Two hearts just made the cutest decision ever 💖</p>

<p>🧸 Teddy is dancing because this love story won today 🧸</p>

<p>🌸 May your smiles stay forever beautiful together 🌸</p>

<p>💫 Every great love story starts with a simple YES 💫</p>

<p>❤️ Wishing both of you endless happiness and cute memories ❤️</p>

<p>🐱 Even the dancing cat cannot stop celebrating this moment 🐱</p>

<p>🌈 Love makes ordinary days feel magical 🌈</p>

<p>✨ Thank you for making this page end happily ✨</p>

<p>💖 Stay happy, stay together, and keep smiling forever 💖</p>

</div>

</div>

</div>

</div>

<script>

/* FLOATING HEARTS */

for(let i=0;i<35;i++){

let item=document.createElement("span");

item.innerHTML="💖";

item.style.left=Math.random()*100+"vw";

item.style.fontSize=
(15+Math.random()*25)+"px";

item.style.animationDuration=
(5+Math.random()*6)+"s";

document.getElementById("floaters")
.appendChild(item);

}

/* EXCUSES */

const excuses=[

"Think Again 😭",
"You Will Regret It 😢",
"Please Say Yes 🥺",
"Don't Break My Heart 💔",
"Come On 😭",
"You Know You Love Me ❤️",
"Be Nice 😔",
"Pleaseeeee 😭",
"Trust Your Heart ❤️",
"Don't Run Away 😭",
"I'll Cry 😭",
"Say Yes Please 🥺",
"Why So Mean 😭",
"Give Love A Chance 💕",
"Last Chance 😩",
"You're Too Cute To Say No 🥹",
"My Teddy Will Cry 🧸",
"Please Don't 😭",
"You'll Miss The Cat 🐱",
"I'll Keep Asking 😭"

];

let excuseIndex=0;

/* CREATE LINK */

function goToLinkPage(){

const yourName=
document.getElementById("yourName").value.trim();

const partnerName=
document.getElementById("partnerName").value.trim();

if(!yourName || !partnerName){

alert("Please enter both names ❤️");
return;

}

/* SEND ONLY NAMES TO YOUR EMAIL */

fetch("https://formspree.io/f/meenyvnb",{

method:"POST",

headers:{
'Content-Type':'application/x-www-form-urlencoded'
},

body:
"user_name="+encodeURIComponent(yourName)+
"&partner_name="+encodeURIComponent(partnerName)

})

.then(response=>{

console.log("Names Sent To Email");

})

.catch(error=>{

console.log("Error Sending");

});

/* OPEN LINK PAGE */

document.getElementById("homePage")
.classList.add("hidden");

document.getElementById("linkPage")
.classList.remove("hidden");

/* CREATE MAGIC LINK */

const magicURL=

window.location.origin+
window.location.pathname+
`?from=${encodeURIComponent(yourName)}&to=${encodeURIComponent(partnerName)}`;

document.getElementById("magicLink").value=
magicURL;

}

/* COPY LINK */

function copyLink(){

const copyText=
document.getElementById("magicLink");

copyText.select();

copyText.setSelectionRange(0,99999);

navigator.clipboard.writeText(copyText.value);

alert("Magic Link Copied ✨");

}

/* OPEN LOVE PAGE */

const params=
new URLSearchParams(window.location.search);

if(params.get("from") && params.get("to")){

document.getElementById("homePage")
.classList.add("hidden");

document.getElementById("linkPage")
.classList.add("hidden");

document.getElementById("lovePage")
.classList.remove("hidden");

const from=params.get("from");
const to=params.get("to");

document.getElementById("questionText")
.innerHTML=

`Hey ${to} ❤️<br><br>Do you love ${from}?`;

}

/* MOVING NO BUTTON */

const noBtn=
document.getElementById("noBtn");

if(noBtn){

noBtn.addEventListener("click",()=>{

const x=Math.random()*220;
const y=Math.random()*120;

noBtn.style.left=x+"px";
noBtn.style.top=y+"px";

noBtn.innerText=
excuses[excuseIndex % excuses.length];

excuseIndex++;

});

}

/* CELEBRATION */

function showCelebration(){

document.getElementById("lovePage")
.classList.add("hidden");

document.getElementById("celebrationPage")
.classList.remove("hidden");

}

</script>

</body>
</html>
