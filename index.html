<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MonthLits – Full Interactive Photo & Compilation Editor</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&family=Patrick+Hand&family=Courier+Prime&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/html2canvas@1.4.1/dist/html2canvas.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/jspdf@2.5.1/dist/jspdf.umd.min.js"></script>

<style>
:root{--pink:#f7b6c8;--apricot:#ffcf9f;--dark:#5a2a3a}
body{margin:0;font-family:Poppins;background:linear-gradient(135deg,var(--pink),var(--apricot));color:var(--dark)}
header{text-align:center;padding:30px;background:rgba(255,255,255,.35);backdrop-filter:blur(6px)}
main{max-width:1200px;margin:auto;padding:40px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:25px}
.month-card{background:white;border-radius:20px;padding:20px;box-shadow:0 10px 25px rgba(0,0,0,.12);text-align:center}
.month-card h2{margin:10px 0}
.photo-box{width:100%;height:140px;border-radius:15px;background:linear-gradient(135deg,var(--pink),var(--apricot));display:flex;align-items:center;justify-content:center;color:white;font-weight:bold;margin-bottom:10px}
.buttons{margin-top:10px;display:flex;flex-direction:column;gap:10px}
input[type=file]{border-radius:15px;padding:6px}
button{padding:10px;border-radius:20px;border:none;background:var(--pink);color:var(--dark);font-weight:bold;cursor:pointer}
button:hover{background:var(--apricot)}
.counter{font-size:.85rem;margin-top:5px}
.compile{margin-top:50px;text-align:center}
.compile button{padding:15px 30px;font-size:1.1rem}
.qr-output{margin-top:10px}

/* Editor Styles */
#editorWrap{display:none}
#editor{position:relative;max-width:900px;min-height:550px;margin:20px auto;background:#fff;border-radius:25px;box-shadow:0 20px 40px rgba(0,0,0,.25);overflow:hidden}
.toolbar{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;margin-bottom:15px}
.item{position:absolute;cursor:move}
.item img{max-width:180px;border-radius:15px}
.text{border:1px dashed #aaa;padding:6px}
.sticker{font-size:38px}
#templateControls{display:flex;flex-wrap:wrap;justify-content:center;gap:10px;margin:10px auto}
#templateControls input[type=number]{width:60px}
</style>
</head>
<body>

<header>
<h1>MonthLits</h1>
<p>Edit your monthly memories & create compilations</p>
</header>

<main>
<div class="grid" id="months"></div>

<div class="compile">
<h2>Compile All Photos</h2>
<button onclick="openCompilation()">Create Compilation</button>
</div>

<!-- Editor -->
<div id="editorWrap">
<h2 id="editorTitle" style="text-align:center"></h2>

<div class="toolbar">
<button onclick="addText()">Text</button>
<button onclick="addSticker('💗')">💗</button>
<button onclick="addSticker('✨')">✨</button>
<button onclick="addSticker('🎀')">🎀</button>
<input type="file" accept="image/*" onchange="addImage(event)">
<label>Background: <input type="color" id="bgColor" onchange="setBackgroundColor(this.value)"></label>
<label>Font: 
<select id="fontSelect" onchange="setFont(this.value)">
<option value="Poppins">Poppins</option>
<option value="Patrick Hand">Scrapbook</option>
<option value="Courier Prime">Diary</option>
</select>
</label>
<button onclick="applyTemplate()">Apply Template</button>
<button onclick="saveEditor()">Save</button>
<button onclick="exportPNG()">PNG</button>
<button onclick="exportPDF()">PDF</button>
<button onclick="closeEditor()">Close</button>
</div>

<!-- Template Layout Controls -->
<div id="templateControls">
<label>Columns: <input type="number" id="gridCols" value="4" min="1" max="10"></label>
<label>GapX: <input type="number" id="gapX" value="10" min="0"></label>
<label>GapY: <input type="number" id="gapY" value="10" min="0"></label>
<label>Rotation: <input type="number" id="rotationRange" value="10" min="0" max="45"></label>
<button onclick="applyLayout()">Preview Layout</button>
</div>

<div id="editor"></div>

<div style="margin-top:20px;text-align:center">
<h3>Compilation Templates</h3>
<div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(120px,1fr));gap:10px;max-width:800px;margin:auto">
<button onclick="loadTemplate('scrapbook')">Scrapbook</button>
<button onclick="loadTemplate('pastel')">Pastel</button>
<button onclick="loadTemplate('polaroid')">Polaroid</button>
<button onclick="loadTemplate('vintage')">Vintage</button>
<button onclick="loadTemplate('diary')">Diary</button>
<button onclick="loadTemplate('cute')">Cute</button>
<button onclick="loadTemplate('film')">Film</button>
<button onclick="loadTemplate('collage')">Collage</button>
<button onclick="loadTemplate('minimal')">Minimal</button>
<button onclick="loadTemplate('retro')">Retro</button>
<button onclick="enableCustomTemplate()">Custom</button>
</div>
</div>

</div>
</main>

<script>
const months=['January','February','March','April','May','June','July','August','September','October','November','December'];
const MAX_PHOTOS=150;
const uploads={};
let currentKey='';

const container=document.getElementById('months');
months.forEach(m=>{
 uploads[m]=[];
 const card=document.createElement('div');
 card.className='month-card';
 card.innerHTML=`
   <div class="photo-box">${m} Photos</div>
   <h2>${m}</h2>
   <input type="file" accept="image/*" multiple onchange="handleUpload('${m}', this)">
   <div class="counter" id="count-${m}">0 / ${MAX_PHOTOS} uploaded</div>
   <div class="buttons">
     <button onclick="generateQR('${m}', this)">Generate QR</button>
     <div class="qr-output"></div>
     <button onclick="openMonthEditor('${m}')">Edit ${m}</button>
   </div>`;
 container.appendChild(card);
});

function handleUpload(month,input){
 const files=Array.from(input.files);
 if(uploads[month].length+files.length>MAX_PHOTOS){alert(`Max ${MAX_PHOTOS} photos for ${month}`);input.value='';return}
 uploads[month].push(...files);
 document.getElementById(`count-${month}`).innerText=`${uploads[month].length} / ${MAX_PHOTOS}`;
 input.value='';
}

function generateQR(month,btn){
 const qrDiv=btn.nextElementSibling;
 qrDiv.innerHTML='';
 new QRCode(qrDiv,{text:window.location.href+`#${month}`,width:120,height:120});
}

/* Editor Logic */
const editorWrap=document.getElementById('editorWrap');
const editor=document.getElementById('editor');
const bgColorInput=document.getElementById('bgColor');
const fontSelect=document.getElementById('fontSelect');

function openMonthEditor(month){
 currentKey='month-'+month;
 openEditor(month);
 loadMonthImages(month);
}

function openCompilation(){
 currentKey='compilation';
 openEditor('Compilation');
 editor.innerHTML='';
 months.forEach(m=>{
   loadMonthImages(m);
 });
}

function loadMonthImages(month){
 uploads[month].forEach(file=>{
   const reader=new FileReader();
   reader.onload=e=>{
     let div=document.createElement('div');
     div.className='item';
     let img=document.createElement('img');
     img.src=e.target.result;
     div.appendChild(img);
     placeItem(div);
   };
   reader.readAsDataURL(file);
 });
 // Also load previously saved edited items
 let saved = localStorage.getItem('month-'+month);
 if(saved){
   let temp = document.createElement('div');
   temp.innerHTML=saved;
   Array.from(temp.children).forEach(c=>editor.appendChild(c));
 }
}

function openEditor(title){
 editorWrap.style.display='block';
 document.getElementById('editorTitle').innerText=title;
 if(currentKey!=='compilation') editor.innerHTML=localStorage.getItem(currentKey)||'';
}

function closeEditor(){editorWrap.style.display='none'}
function saveEditor(){
 localStorage.setItem(currentKey,editor.innerHTML);
 alert('Saved ✨');
}

function addText(){let t=document.createElement('div');t.className='item text';t.contentEditable=true;t.innerText='Edit text';placeItem(t);}
function addSticker(s){let t=document.createElement('div');t.className='item sticker';t.innerText=s;placeItem(t);}
function addImage(e){
 let r=new FileReader();
 r.onload=x=>{
   let i=document.createElement('img');i.src=x.target.result;
   let t=document.createElement('div');t.className='item';t.appendChild(i);placeItem(t);
 }
 r.readAsDataURL(e.target.files[0]);
}

function placeItem(el){el.style.left='50px';el.style.top='50px';enableDrag(el);editor.appendChild(el);}
function enableDrag(el){
 let x,y;
 el.onpointerdown=e=>{
   x=e.clientX-el.offsetLeft;y=e.clientY-el.offsetTop;
   editor.setPointerCapture(e.pointerId);
   editor.onpointermove=m=>{el.style.left=m.clientX-x+'px';el.style.top=m.clientY-y+'px'}
 }
 el.onpointerup=()=>editor.onpointermove=null;
 el.onwheel=e=>{e.preventDefault();let sc=parseFloat(el.style.scale||1)+(e.deltaY<0?.05:-.05);el.style.scale=Math.max(.2,sc)}
}

function setBackgroundColor(c){editor.style.background=c;}
function setFont(f){editor.style.fontFamily=f;}

function exportPNG(){
 html2canvas(editor).then(c=>{
   let a=document.createElement('a');a.href=c.toDataURL();a.download='MonthLits.png';a.click();
 });
}
function exportPDF(){
 html2canvas(editor).then(c=>{
   let p=new jspdf.jsPDF('p','px',[c.width,c.height]);
   p.addImage(c.toDataURL(),'PNG',0,0);
   p.save('MonthLits.pdf');
 });
}

/* Templates */
const templates={
scrapbook:{bg:'#87b5e5',font:'Patrick Hand'},
pastel:{bg:'linear-gradient(135deg,#f7b6c8,#ffcf9f)',font:'Poppins'},
polaroid:{bg:'#fff',font:'Poppins',border:'8px solid #f7b6c8'},
vintage:{bg:'#f2e6d8',font:'Poppins',filter:'sepia(0.3)'},
diary:{bg:'#fffbe6',font:'Courier Prime'},
cute:{bg:'#ffe6f0',font:'Poppins',radius:'25px'},
film:{bg:'#222',font:'Poppins',color:'#fff'},
collage:{bg:'#cce0ff',font:'Poppins'},
minimal:{bg:'#ffffff',font:'Poppins'},
retro:{bg:'#fde4b0',font:'Courier Prime',radius:'10px'}
};

function loadTemplate(name){
 const t=templates[name];
 editor.style.background=t.bg||'#fff';
 editor.style.fontFamily=t.font||'Poppins';
 if(t.border) editor.style.border=t.border; else editor.style.border='';
 if(t.radius) editor.style.borderRadius=t.radius; else editor.style.borderRadius='25px';
 if(t.color) editor.style.color=t.color; else editor.style.color='var(--dark)';
 if(t.filter) editor.style.filter=t.filter; else editor.style.filter='';
}

function enableCustomTemplate(){
 alert('Custom template enabled! Use color picker, font select, and adjust layout.');
}

function applyTemplate(){
 editor.style.background=bgColorInput.value;
 editor.style.fontFamily=fontSelect.value;
}

/* Layout Preview */
function applyLayout(){
 let cols=parseInt(document.getElementById('gridCols').value);
 let gapX=parseInt(document.getElementById('gapX').value);
 let gapY=parseInt(document.getElementById('gapY').value);
 let rotation=parseInt(document.getElementById('rotationRange').value);
 let items=Array.from(editor.querySelectorAll('.item img')).map(i=>i.parentElement);
 items.forEach((el,i)=>{
   let row=Math.floor(i/cols);
   let col=i%cols;
   el.style.left=(gapX + col*(150+gapX))+'px';
   el.style.top=(gapY + row*(150+gapY))+'px';
   let rot=Math.random()*rotation*2-rotation;
   el.style.transform=`rotate(${rot}deg)`;
 });
}
</script>

</body>
</html>
