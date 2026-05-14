<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI Study Website</title>

<style>

body{
    margin:0;
    font-family:Arial;
    background:#0f172a;
    color:white;
}

header{
    background:#111827;
    padding:15px;
    text-align:center;
    font-size:28px;
    font-weight:bold;
}

.container{
    padding:20px;
}

.card{
    background:#1e293b;
    padding:20px;
    border-radius:15px;
    margin-bottom:20px;
}

h2{
    margin-top:0;
}

input, textarea{
    width:100%;
    padding:12px;
    margin-top:10px;
    border:none;
    border-radius:10px;
    font-size:16px;
}

button{
    margin-top:15px;
    padding:12px 20px;
    border:none;
    border-radius:10px;
    background:#2563eb;
    color:white;
    font-size:16px;
    cursor:pointer;
}

button:hover{
    background:#1d4ed8;
}

.chat-box{
    height:250px;
    overflow-y:auto;
    background:#0f172a;
    padding:10px;
    border-radius:10px;
}

.message{
    padding:10px;
    margin:10px 0;
    border-radius:10px;
    max-width:80%;
}

.user{
    background:#2563eb;
    margin-left:auto;
}

.bot{
    background:#334155;
}

img{
    max-width:100%;
    border-radius:10px;
    margin-top:10px;
}

.feature{
    padding:10px;
    background:#334155;
    border-radius:10px;
    margin-top:10px;
}

</style>
</head>

<body>

<header>
🎓 AI Study Website
</header>

<div class="container">

<!-- AI CHAT -->

<div class="card">

<h2>🤖 AI Guru </h2>

<div class="chat-box" id="chatBox">

<div class="message bot">
Hello Student 👋<br>
Study I Can Help You
  .
</div>

</div>

<input type="text" id="userInput" placeholder="Question likho...">

<button onclick="sendMessage()">Send</button>

</div>

<!-- PHOTO UPLOAD -->

<div class="card">

<h2>📸 Photo Upload</h2>

<input type="file" id="photoInput" accept="image/*">

<div id="preview"></div>

</div>

<!-- NOTES -->

<div class="card">

<h2>📝 Notes Section</h2>

<textarea rows="6" placeholder="Yahan notes likho..."></textarea>

<button>Save Notes</button>

</div>

<!-- FEATURES -->

<div class="card">

<h2>📚 Study Features</h2>

<div class="feature">✅ AI Homework Help</div>

<div class="feature">✅ Notes Writing</div>

<div class="feature">✅ Photo Upload</div>

<div class="feature">✅ Quiz Practice</div>

<div class="feature">✅ Study Chatbot</div>

<div class="feature">✅ Doubt Solving</div>

</div>

</div>

<script>

// CHATBOT

function sendMessage(){

let input = document.getElementById("userInput");

let message = input.value;

if(message.trim() === ""){
return;
}

let chatBox = document.getElementById("chatBox");

// USER MESSAGE

let userDiv = document.createElement("div");

userDiv.classList.add("message","user");

userDiv.innerText = message;

chatBox.appendChild(userDiv);

// BOT REPLY

let botDiv = document.createElement("div");

botDiv.classList.add("message","bot");

if(message.toLowerCase().includes("math")){

botDiv.innerText = "Math answer: 2 + 2 = 4";

}

else if(message.toLowerCase().includes("science")){

botDiv.innerText = "Science is the study of nature.";

}

else{

botDiv.innerText = "AI Reply: " + message;

}

setTimeout(()=>{

chatBox.appendChild(botDiv);

chatBox.scrollTop = chatBox.scrollHeight;

},500);

input.value="";

}

// PHOTO PREVIEW

document.getElementById("photoInput").addEventListener("change", function(event){

let file = event.target.files[0];

if(file){

let reader = new FileReader();

reader.onload = function(e){

document.getElementById("preview").innerHTML = `
<img src="${e.target.result}">
`;

}

reader.readAsDataURL(file);

}

});

</script>

</body>
</html>

