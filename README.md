# Divyaa-patel 
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Cutieeee ❤️</title>

<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600&family=Poppins:wght@300;500&display=swap" rel="stylesheet">

<style>
body{
    margin:0;
    padding:0;
    font-family:'Poppins',sans-serif;
    background:linear-gradient(to bottom,#ffdde1,#ee9ca7);
    overflow-x:hidden;
    text-align:center;
    color:white;
}

/* Falling Hearts */
.heart{
    position:fixed;
    top:-10px;
    color:red;
    animation:fall linear forwards;
}
@keyframes fall{
    to{
        transform:translateY(100vh);
        opacity:0;
    }
}

/* Hero Section */
.hero{
    padding:100px 20px;
}
.hero h1{
    font-family:'Dancing Script',cursive;
    font-size:50px;
    animation:glow 2s infinite alternate;
}
@keyframes glow{
    from{text-shadow:0 0 10px #fff;}
    to{text-shadow:0 0 20px #ff4d6d;}
}

/* Sections */
.section{
    padding:60px 20px;
}

button{
    padding:12px 25px;
    margin:10px;
    border:none;
    border-radius:30px;
    font-size:16px;
    cursor:pointer;
    transition:0.3s;
}
.yes{
    background:#ff4d6d;
    color:white;
}
.always{
    background:#ff85a2;
    color:white;
}
button:hover{
    transform:scale(1.1);
}

/* Game */
#gameArea{
    position:relative;
    height:300px;
    background:rgba(255,255,255,0.2);
    border-radius:20px;
    overflow:hidden;
}
.gameHeart{
    position:absolute;
    font-size:25px;
    cursor:pointer;
}

/* Footer */
footer{
    padding:30px;
    font-family:'Dancing Script',cursive;
    font-size:22px;
}
</style>
</head>

<body>

<div class="hero">
    <h1>To My Forever Love, Cutieeee 💕</h1>
    <p>You are the most beautiful chapter of my life 💖</p>
</div>

<div class="section">
    <h2>💌 My Love Message</h2>
    <p>
        From the moment you walked into my life, everything became brighter.
        Your smile is my sunshine, your laugh is my favorite song,
        and your love is my biggest blessing.
        Cutieeee, will you be mine forever? 💍❤️
    </p>
</div>

<div class="section">
    <h2>💍 Proposal</h2>
    <p>Cutieeee, will you be my Valentine forever?</p>
    <button class="yes" onclick="yesClicked()">Yes 💖</button>
    <button class="always" onclick="alwaysClicked()">Always Yes 😍</button>
    <p id="proposalMessage"></p>
</div>

<div class="section">
    <h2>🎮 Catch My Heart Game</h2>
    <p>Click 10 hearts to win 💕</p>
    <div id="gameArea"></div>
    <p id="scoreText">Hearts Caught: 0</p>
</div>

<div class="section">
    <h2>⏳ Loving You Since...</h2>
    <p id="loveCounter"></p>
</div>

<footer>
    Made with endless love for my Cutieeee ❤️
</footer>

<audio autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mpeg">
</audio>

<script>

/* Falling Hearts Animation */
function createHeart(){
    const heart=document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML="💖";
    heart.style.left=Math.random()*100+"vw";
    heart.style.fontSize=Math.random()*20+15+"px";
    heart.style.animationDuration=Math.random()*3+3+"s";
    document.body.appendChild(heart);

    setTimeout(()=>{
        heart.remove();
    },5000);
}
setInterval(createHeart,300);

/* Proposal Buttons */
function yesClicked(){
    document.getElementById("proposalMessage").innerHTML="Yayyy! I love you so much 🥰💕";
}

function alwaysClicked(){
    document.getElementById("proposalMessage").innerHTML="You are my forever ❤️💍✨";
}

/* Game */
let score=0;
const gameArea=document.getElementById("gameArea");
const scoreText=document.getElementById("scoreText");

function createGameHeart(){
    const heart=document.createElement("div");
    heart.classList.add("gameHeart");
    heart.innerHTML="❤️";
    heart.style.left=Math.random()*90+"%";
    heart.style.top="0px";
    gameArea.appendChild(heart);

    let fall=setInterval(()=>{
        heart.style.top=(heart.offsetTop+5)+"px";
        if(heart.offsetTop>280){
            heart.remove();
            clearInterval(fall);
        }
    },50);

    heart.onclick=function(){
        score++;
        scoreText.innerHTML="Hearts Caught: "+score;
        heart.remove();
        clearInterval(fall);

   
         if(score>=10){
            alert("You caught my heart, Cutieeee! 💕");
            score=0;
            scoreText.innerHTML="Hearts Caught: 0";
        }
    }
}
setInterval(createGameHeart,1000);

/* Love Counter */
const startDate=new Date("February 14, 2024 00:00:00").getTime();
setInterval(()=>{
    const now=new Date().getTime();
    const distance=now-startDate;

    const days=Math.floor(distance/(1000*60*60*24));
    const hours=Math.floor((distance%(1000*60*60*24))/(1000*60*60));
    const minutes=Math.floor((distance%(1000*60*60))/(1000*60));

    document.getElementById("loveCounter").innerHTML=
    days+" Days "+hours+" Hours "+minutes+" Minutes 💖";
},1000);

</script>

</body>
</html>
