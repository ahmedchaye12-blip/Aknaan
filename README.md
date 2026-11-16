

<!DOCTYPE html>  <html>  
<head>  
<meta charset="UTF-8">  
<meta name="viewport" content="width=device-width, initial-scale=1">  
<title>Cyber Terminal</title>  
<style>  
body {  
 background:#000;  
 color:#00ff41;  
 font-family:monospace;  
 padding:15px;  
 overflow:hidden;  
}  
h2 {  
 color:red;  
 text-align:center;  
 animation:blink .5s infinite;  
}  
#terminal {  
 font-size:13px;  
 line-height:1.6;  
 overflow-wrap:anywhere;  
}  
.alert {  
 color:red;  
 text-align:center;  
 font-size:20px;  
}  
@keyframes blink {  
 50% {opacity:0;}  
}  
button {  
 background:#111;  
 color:#00ff41;  
 border:1px solid #00ff41;  
 padding:15px;  
 width:100%;  
 font-size:17px;  
}  
</style>  
</head>  
<body>  <h2>⚠ SYSTEM WARNING ⚠</h2>  
<div class="alert">CYBER SIMULATION</div>  
<button onclick="start()">START SIMULATION</button>  
<div id="terminal"></div>  <script>  
let running=false;  
  
function start(){  
 if(running) return;  
 running=true;  
  
 let terminal=document.getElementById("terminal");  
 const chars="0123456789ABCDEF";  
 const words=[  
 "INITIALIZING TERMINAL",  
 "LOADING MODULES",  
 "NETWORK SIMULATION",  
 "CHECKING SECURITY",  
 "SYSTEM ANALYSIS",  
 "PROCESS RUNNING"  
 ];  
  
 setInterval(()=>{  
  let code="";  
  for(let i=0;i<45;i++)  
   code+=chars[Math.floor(Math.random()*16)];  
  
  let line=document.createElement("div");  
  line.textContent=  
   words[Math.floor(Math.random()*words.length)]  
   +" :: "+code;  
  
  terminal.appendChild(line);  
  
  if(terminal.children.length>22)  
   terminal.removeChild(terminal.firstChild);  
 },150);  
  
 let audio=new (window.AudioContext||window.webkitAudioContext)();  
 let oscillator=audio.createOscillator();  
 let volume=audio.createGain();  
  
 oscillator.frequency.value=650;  
 volume.gain.value=0.025;  
 oscillator.connect(volume);  
 volume.connect(audio.destination);  
 oscillator.start();  
  
 setTimeout(()=>oscillator.stop(),350);  
}  
</script>  </body>  
</html>  # Aknaan

