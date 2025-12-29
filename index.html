<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>MonthLits – Advanced Editor</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&family=Patrick+Hand&family=Courier+Prime&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/html2canvas@1.4.1/dist/html2canvas.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/jspdf@2.5.1/dist/jspdf.umd.min.js"></script>

<style>
:root{--pink:#f7b6c8;--apricot:#ffcf9f}
body{margin:0;font-family:Poppins;background:linear-gradient(135deg,var(--pink),var(--apricot))}
header{text-align:center;padding:30px;background:rgba(255,255,255,.4);backdrop-filter:blur(8px)}
h1{margin:0;font-size:3rem}
main{padding:20px;max-width:1300px;margin:auto}

#editor{position:relative;max-width:900px;min-height:550px;margin:20px auto;background:#fff;border-radius:25px;box-shadow:0 20px 40px rgba(0,0,0,.25);overflow:hidden;touch-action:none}

.toolbar{display:flex;flex-wrap:wrap;gap:8px;justify-content:center}
button,input,select{border:none;border-radius:20px;padding:8px 14px;font-weight:bold;cursor:pointer}
button{background:var(--pink)}
button:hover{background:var(--apricot)}

.item{position:absolute;cursor:move}
.item img{max-width:180px;border-radius:15px}
.text{border:1px dashed #aaa;padding:6px}
.sticker{font-size:38px}
.layer{position:relative}

#login{display:flex;justify-content:center;gap:10px;margin:10px}

footer{text-align:center;padding:30px;opacity:.7}
</style>
</head>
<body>
<header>
<h1>MonthLits</h1>
<p>Full Canva‑Style Scrapbook Editor</p>
</header>

<main>

<!-- LOGIN -->
<div id="login">
<input id="username" placeholder="Enter name">
<button onclick="login()">Login</button>
</div>

<!-- TOOLBAR -->
<div class="toolbar">
<button onclick="addText()">Text</button>
<button onclick="addSticker('⭐')">⭐</button>
<button onclick="addSticker('✨')">✨</button>
<button onclick="addSticker('💗')">💗</button>
<button onclick="addSticker('📌')">📌</button>
<button onclick="addSticker('🎀')">🎀</button>
<button onclick="bringFront()">Front</button>
<button onclick="sendBack()">Back</button>
<button onclick="setFont('Patrick Hand')">Scrapbook</button>
<button onclick="setFont('Courier Prime')">Diary</button>
<input type="color" onchange="editor.style.background=this.value">
<input type="file" accept="image/*" onchange="addBackground(event)">
<button onclick="saveBoard()">Save</button>
<button onclick="exportPNG()">PNG</button>
<button onclick="exportPDF()">PDF</button>
</div>

<div id="editor"></div>

</main>
<footer>MonthLits © Advanced Memory Project</footer>

<script>
let editor=document.getElementById('editor');
let active=null;

function login(){
 const u=document.getElementById('username').value;
 if(!u)return alert('Enter name');
 localStorage.setItem('user',u);
 alert('Welcome '+u);
}

function addText(){
 const t=document.createElement('div');
 t.className='item text';
 t.contentEditable=true;
 t.innerText='Edit text';
 addItem(t);
}

function addSticker(s){
 const d=document.createElement('div');
 d.className='item sticker';
 d.innerText=s;
 addItem(d);
}

function addItem(el){
 el.style.left='50px';el.style.top='50px';
 enable(el);
 editor.appendChild(el);
 active=el;
}

function enable(el){
 let sx=0,sy=0;
 el.onpointerdown=e=>{
  active=el;
  sx=e.clientX-el.offsetLeft;
  sy=e.clientY-el.offsetTop;
  editor.setPointerCapture(e.pointerId);
  editor.onpointermove=m=>{
    el.style.left=m.clientX-sx+'px';
    el.style.top=m.clientY-sy+'px';
  }
 }
 el.onpointerup=()=>editor.onpointermove=null;
 el.onwheel=e=>{e.preventDefault();let sc=parseFloat(el.style.scale||1)+(e.deltaY<0?.05:-.05);el.style.scale=Math.max(.2,sc)}
}

function bringFront(){if(active)active.style.zIndex=1000}
function sendBack(){if(active)active.style.zIndex=1}
function setFont(f){editor.style.fontFamily=f}

function addBackground(e){
 let r=new FileReader();
 r.onload=x=>editor.style.background=`url(${x.target.result}) center/cover`;
 r.readAsDataURL(e.target.files[0]);
}

function saveBoard(){
 localStorage.setItem('board',editor.innerHTML);
 localStorage.setItem('bg',editor.style.background);
 alert('Saved ✨');
}

function exportPNG(){
 html2canvas(editor).then(c=>{
  let a=document.createElement('a');
  a.download='MonthLits.png';
  a.href=c.toDataURL();
  a.click();
 })
}

function exportPDF(){
 html2canvas(editor).then(c=>{
  const pdf=new jspdf.jsPDF('p','px',[c.width,c.height]);
  pdf.addImage(c.toDataURL(),'PNG',0,0,c.width,c.height);
  pdf.save('MonthLits.pdf');
 })
}

window.onload=()=>{
 if(localStorage.board)editor.innerHTML=localStorage.board;
 if(localStorage.bg)editor.style.background=localStorage.bg;
}
</script>
</body>
</html>
