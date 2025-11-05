<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Games</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&display=swap');

body {
    margin: 0;
    font-family: 'Press Start 2P', cursive, Arial, sans-serif;
    background: radial-gradient(circle at center, #0a0a1a 0%, #000010 100%);
    overflow-x: hidden;
    color: #fff;
    text-align: center;
    position: relative;
}

/* Title */
h1 {
    margin-top: 60px;
    font-size: 1.2em;
    text-shadow: 0 0 10px #00ffff, 0 0 20px #00ffff;
    animation: glowTitle 3s ease-in-out infinite alternate;
}
@keyframes glowTitle {
    from { text-shadow: 0 0 10px #00ffff; }
    to { text-shadow: 0 0 25px #00ffff, 0 0 50px #00ffff; }
}

/* Main content container */
.content {
    position: relative;
    z-index: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 40px 20px 100px;
}

/* Tabs inline */
.tabs {
    display: flex;
    gap: 20px;
    margin-bottom: 20px; 
    flex-wrap: wrap;
    justify-content: center;
}

.tab {
    padding: 12px 20px;
    background-color: #333;
    border: 2px solid #666;
    border-radius: 8px 8px 0 0;
    transition: all 0.2s ease, box-shadow 0.2s ease;
    font-size: 0.8em;
    color: #fff;
    text-shadow: 1px 1px #000;
    position: relative;
    cursor: pointer;
    animation: glowPulse 2s infinite;
}

.tab:hover {
    transform: scale(1.05);
    background-color: #555;
}

.tab.active {
    background-color: #111;
    border-color: #00ffff;
    box-shadow: 0 0 30px #00ffff;
    animation: bounce 0.25s, glowPulse 2s infinite;
}

.tab.gold {
    box-shadow: 0 0 25px gold, 0 0 40px gold;
    animation: glowPulseGold 2s infinite;
}

@keyframes bounce {
    0% { transform: scale(1); }
    50% { transform: scale(1.08); }
    100% { transform: scale(1.05); }
}

@keyframes glowPulse {
    0%,100% { box-shadow: 0 0 10px #00ffff; }
    50% { box-shadow: 0 0 20px #00ffff; }
}

@keyframes glowPulseGold {
    0%,100% { box-shadow: 0 0 10px gold; }
    50% { box-shadow: 0 0 20px gold; }
}

/* Tab content */
.tab-content {
    display: none;
    background-color: rgba(20,20,20,0.9);
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.4);
    text-align: center;
    animation: fadeIn 0.4s ease;
    width: 90%;
    max-width: 800px;
    margin-bottom: 60px;
}
.tab-content.active {
    display: block;
}
@keyframes fadeIn {
    from { opacity: 0; transform: translateY(-10px); }
    to { opacity: 1; transform: translateY(0); }
}

/* Game buttons */
a {
    display: inline-block;
    margin: 8px 8px;
    padding: 10px 16px;
    background-color: #ffcc00;
    color: #000;
    font-weight: bold;
    text-decoration: none;
    border: 2px solid #fff;
    border-radius: 6px;
    transition: all 0.2s ease, box-shadow 0.2s ease;
    text-shadow: 1px 1px #000;
    animation: glowPulse2 2s infinite;
}

a:hover {
    transform: scale(1.1);
    box-shadow: 0 0 25px #ff00ff, 0 0 35px #ff00ff;
    background-color: #ffdd33;
}

@keyframes glowPulse2 {
    0%,100% { box-shadow: 0 0 10px #ffcc00; }
    50% { box-shadow: 0 0 20px #ffcc00; }
}

canvas {
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
}

/* Music button */
#music-toggle {
    position: fixed;
    top: 20px;
    right: 20px;
    background: #222;
    color: #00ffff;
    border: 2px solid #00ffff;
    padding: 8px 12px;
    border-radius: 6px;
    font-family: 'Press Start 2P', cursive;
    font-size: 0.6em;
    cursor: pointer;
    transition: 0.3s;
}
#music-toggle:hover {
    background: #00ffff;
    color: #000;
}
</style>
</head>
<body>

<canvas id="background"></canvas>

<h1>🎮 Retro Game Hub 🎮</h1>
<button id="music-toggle">🎵 Music: Off</button>

<div class="content">
    <div class="tabs">
        <div class="tab active" data-tab="games">Top Games</div>
        <div class="tab" data-tab="classics">Classic Games</div>
        <div class="tab" data-tab="collaborators">Collaborators</div>
    </div>

    <div id="games" class="tab-content active">
        <a href="https://slopeio.org/">Slope</a>
        <a href="https://littlealchemy2.com/">Little Alchemy 2</a>
        <a href="https://minecraftforfreex.com/eaglercraft/">Minecraft</a>
        <a href="https://xigency.herokuapp.com/">Cyber Tanks</a>
        <a href="https://play.tetris.com/">Tetris</a>
        <a href="https://krunker.io/">Krunker.io</a>
        <a href="https://shellshock.io/">Shell Shockers</a>
        <a href="https://agar.io/">Agar.io</a>
        <a href="https://paper.io/">Paper.io</a>
        <a href="https://diep.io/">Diep.io</a>
    </div>

    <div id="classics" class="tab-content">
        <a href="https://pacman.live/">Pac-Man</a>
        <a href="https://playtetris.io/">Tetris Classic</a>
        <a href="https://ponggame.io/">Pong</a>
        <a href="https://www.retrogames.cc/">Retro Games Collection</a>
        <a href="https://supermarioemulator.com/">Super Mario</a>
        <a href="https://zelda-classic.com/">The Legend of Zelda</a>
    </div>

    <div id="collaborators" class="tab-content">
        <a href="https://fnaf-2.io/">FNaF 2</a>
        <a href="https://fnafgame.io/fnaf-4">FNaF 4</a>
        <a href="https://granny-games.com/">Granny</a>
        <a href="https://baldi.io/">Baldi’s Basics</a>
        <a href="https://poppy-playtime.io/">Poppy Playtime</a>
    </div>
</div>

<script>
// Tab switching
const tabs = document.querySelectorAll('.tab');
const contents = document.querySelectorAll('.tab-content');
tabs.forEach(tab => {
    tab.addEventListener('click', () => {
        tabs.forEach(t => t.classList.remove('active'));
        tab.classList.add('active');
        contents.forEach(c => c.classList.remove('active'));
        document.getElementById(tab.dataset.tab).classList.add('active');
        window.scrollTo({ top: 0, behavior: 'smooth' });
    });
});

// === Background Shooter Game (unchanged from your version) ===
const canvas = document.getElementById('background');
const ctx = canvas.getContext('2d');
let width = canvas.width = window.innerWidth;
let height = canvas.height = window.innerHeight;

let stars = [], particles = [], bullets = [], targets = [];
let mouseX = width/2, mouseY = height-60;
let alienDir = 1, alienSpeed = 0.5, allDeadColor = false;

function initStars(count){
    stars=[];
    for(let i=0;i<count;i++){
        stars.push({x:Math.random()*width, y:Math.random()*height, radius:Math.random()*2, speed:0.1+Math.random()*0.5});
    }
}
initStars(200);

function initTargets(rows=2, cols=8){
    targets = [];
    const paddingX = 60, paddingY = 50;
    const spacingX = (width - 2*paddingX)/cols;
    const spacingY = 50;
    for(let r=0;r<rows;r++){
        for(let c=0;c<cols;c++){
            targets.push({x:paddingX + c*spacingX, y:paddingY + r*spacingY, alive:true});
        }
    }
}
initTargets();

window.addEventListener('resize',()=>{
    width=canvas.width=window.innerWidth;
    height=canvas.height=window.innerHeight;
    initTargets();
});

function createParticles(x,y,color='red'){
    const useColor = allDeadColor ? 'gold' : color;
    for(let i=0;i<6;i++){
        particles.push({x,y,radius:Math.random()*2+1,speedX:(Math.random()-0.5)*3,speedY:(Math.random()-0.5)*3,alpha:1,decay:0.03+Math.random()*0.02,color:useColor});
    }
    for(let i=0;i<12;i++){
        particles.push({x,y,radius:Math.random()*1+0.5,speedX:(Math.random()-0.5)*6,speedY:(Math.random()-0.5)*6,alpha:1,decay:0.05+Math.random()*0.02,color:useColor});
    }
}

function shootBullet() { bullets.push({x: mouseX, y: mouseY-15, radius: 3, speed: 6}); }

function updateParticles(){
    for(let i=particles.length-1;i>=0;i--){
        let p=particles[i];
        p.x+=p.speedX; p.y+=p.speedY; p.alpha-=p.decay;
        if(p.alpha<=0) particles.splice(i,1);
    }
}

function updateBullets(){
    for(let i=bullets.length-1;i>=0;i--){
        let b = bullets[i];
        b.y -= b.speed;
        targets.forEach(t=>{
            if(t.alive && b.x>t.x && b.x<t.x+24 && b.y>t.y && b.y<t.y+24){
                t.alive = false;
                createParticles(b.x,b.y,'white');
                bullets.splice(i,1);
            }
        });
        if(b.y<0) bullets.splice(i,1);
    }
}

function drawSpaceship(x,y){
    const allDead = targets.every(t=>!t.alive);
    if(allDead && !allDeadColor){
        allDeadColor = true;
        tabs.forEach(t=>t.classList.add('gold'));
    }
    ctx.fillStyle = allDead ? "#FFD700" : "#aaaaaa";
    ctx.fillRect(x-20,y-4,40,8);
    ctx.fillRect(x-12,y-8,24,4);
    ctx.fillRect(x-8,y-12,16,4);
}

function drawAlien(x,y){
    ctx.fillStyle='green';
    const size=4;
    const pattern=[
        "00100",
        "01110",
        "11111",
        "10101",
        "11111",
        "01010",
        "01010"
    ];
    pattern.forEach((row,rowIndex)=>{
        [...row].forEach((col,colIndex)=>{
            if(col==='1') ctx.fillRect(x+colIndex*size,y+rowIndex*size,size,size);
        });
    });
}

function moveAliens(){
    let hitEdge=false;
    targets.forEach(t=>{
        if(t.alive){ t.x+=alienDir*alienSpeed; if(t.x+24>=width||t.x<=0) hitEdge=true; }
    });
    if(hitEdge){ alienDir*=-1; targets.forEach(t=>t.y+=10); }
}

function animate(){
    ctx.clearRect(0,0,width,height);
    const starColor = allDeadColor ? 'gold' : '#fff';
    stars.forEach(star=>{ star.y+=star.speed; if(star.y>height) star.y=0;
        ctx.beginPath(); ctx.arc(star.x,star.y,star.radius,0,Math.PI*2); ctx.fillStyle=starColor; ctx.fill();
    });
    particles.forEach(p=>{ ctx.beginPath(); ctx.arc(p.x,p.y,p.radius,0,Math.PI*2); ctx.fillStyle=allDeadColor?`rgba(255,215,0,${p.alpha})`:`rgba(255,0,0,${p.alpha})`; ctx.fill(); });
    updateParticles();
    bullets.forEach(b=>{ ctx.beginPath(); ctx.arc(b.x,b.y,b.radius,0,Math.PI*2); ctx.fillStyle = allDeadColor?'gold':'red'; ctx.fill(); });
    updateBullets();
    moveAliens();
    targets.forEach(t=>{ if(t.alive) drawAlien(t.x,t.y); });
    drawSpaceship(mouseX, mouseY);
    requestAnimationFrame(animate);
}
animate();

// Controls
document.addEventListener('click', e=>{ createParticles(e.clientX, e.clientY); shootBullet(); });
document.addEventListener('mousemove', e=>{ mouseX = e.clientX; mouseY = height-60; });
document.addEventListener('keydown', e=>{ if(e.code==="Space"){ e.preventDefault(); shootBullet(); createParticles(mouseX, mouseY); } });

// Music toggle
const music = new Audio("https://cdn.pixabay.com/audio/2022/03/15/audio_b6f0a2df62.mp3");
music.loop = true;
const musicBtn = document.getElementById('music-toggle');
let playing = false;
musicBtn.addEventListener('click',()=>{
    playing = !playing;
    if(playing){ music.play(); musicBtn.textContent="🎵 Music: On"; }
    else { music.pause(); musicBtn.textContent="🎵 Music: Off"; }
});
</script>
</body>
</html>
