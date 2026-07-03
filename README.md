<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Oceano Inteligente</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,sans-serif;
scroll-behavior:smooth;
}

body{
background:linear-gradient(180deg,#001f3f,#003f7f,#0077b6);
color:white;
transition:0.4s;
}

body.dark{
background:#0b0b0b;
color:#eaeaea;
}

header{
background:rgba(0,0,0,0.4);
padding:15px;
position:sticky;
top:0;
backdrop-filter:blur(10px);
z-index:1000;
}

nav{
display:flex;
justify-content:center;
gap:25px;
flex-wrap:wrap;
}

nav a{
color:white;
text-decoration:none;
font-weight:bold;
}

.lua-btn{
position:fixed;
top:20px;
right:20px;
width:55px;
height:55px;
border-radius:50%;
border:none;
cursor:pointer;
font-size:22px;
background:#111;
color:white;
z-index:2000;
}

.top-title{
text-align:center;
padding:20px;
background:#00152d;
}

.top-title h1{
color:#00d4ff;
font-size:2.2rem;
text-shadow:0 0 10px #00d4ff;
}

.search-box{
text-align:center;
padding:15px;
}

#pesquisa{
padding:10px 15px;
width:300px;
max-width:90%;
border:none;
border-radius:20px;
outline:none;
}

.posts{
padding:50px 10%;
display:grid;
grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
gap:20px;
}

.post{
background:rgba(255,255,255,0.1);
border-radius:15px;
overflow:hidden;
backdrop-filter:blur(8px);
transition:0.3s;
}

body.dark .post{
background:#1a1a1a;
}

.post img{
width:100%;
height:200px;
object-fit:cover;
}

.post-content{
padding:15px;
}

.actions{
display:flex;
justify-content:space-between;
margin-top:10px;
}

button{
padding:8px 12px;
border:none;
border-radius:10px;
cursor:pointer;
}

.like{background:#00d4ff;}
.dislike{background:#ff4d4d;}

.comment-box{
margin-top:10px;
}

.comment-box input{
width:100%;
padding:8px;
border-radius:8px;
border:none;
margin-top:8px;
outline:none;
}

.comment-list{
margin-top:8px;
font-size:14px;
opacity:0.9;
}

.hidden{
display:none !important;
}

footer{
text-align:center;
padding:30px;
background:rgba(0,0,0,0.3);
margin-top:40px;
}

/* Estilo para destacar o nome do autor */
.artigo-autor {
font-size: 0.9rem;
opacity: 0.8;
margin-bottom: 10px;
font-style: italic;
}

</style>
</head>

<body>

<button class="lua-btn" onclick="toggleTema()">🌙</button>

<header>
<nav>
<a href="#inicio">Início</a>
<a href="#posts">Posts</a>
</nav>
</header>

<div class="top-title">
<h1>🌊 Oceano Inteligente</h1>
<p>Tecnologia e inovação nos oceanos por Maria Eduarda</p>
</div>

<div class="search-box">
<input type="text" id="pesquisa" placeholder="Pesquisar posts...">
</div>

<section class="posts" id="posts">

<div class="post">
<img src="imagem-blog.png" alt="Logotipo conceitual de tecnologia e educacao: um livro aberto de onde emerge um cérebro digital brilhante, cercado por ícones de Wi-Fi, circuitos e lâmpada de ideia. Cores em tons de azul e branco.">
<div class="post-content">
<h3>Meu primeiro post</h3>
<p class="artigo-autor">Por: Marcelo Paludetto</p>
<p>Boas-vindas ao meu novo blog! Aqui vou compartilhar dicas de programação e curiosidades da área de tecnologia aplicada ao mar.</p>

<div class="actions">
<button class="like" onclick="like(this)">❤️ <span>0</span></button>
<button class="like" onclick="like(this)">👍 <span>0</span></button>
</div>

<div class="comment-box">
<input type="text" placeholder="Escreva um comentário..." onkeydown="addComment(event,this)">
<div class="comment-list"></div>
</div>
</div>
</div>

<div class="post">
<img src="imagem-blog.png" alt="Logotipo conceitual de tecnologia e educacao: um livro aberto de onde emerge um cérebro digital brilhante, cercado por ícones de Wi-Fi, circuitos e lâmpada de ideia. Cores em tons de azul e branco.">
<div class="post-content">
<h3>Meu primeiro post</h3>
<p class="artigo-autor">Por: Marcelo Paludetto</p>
<p>Boas-vindas ao meu novo blog! Aqui vou compartilhar dicas de programação e curiosidades da área de tecnologia.</p>

<div class="actions">
<button class="like" onclick="like(this)">❤️ <span>0</span></button>
<button class="like" onclick="like(this)">👍 <span>0</span></button>
</div>

<div class="comment-box">
<input type="text" placeholder="Escreva um comentário..." onkeydown="addComment(event,this)">
<div class="comment-list"></div>
</div>
</div>
</div>

<div class="post">
<img src="https://images.unsplash.com/photo-1582967788606-a171c1080cb0?auto=format&fit=crop&w=800&q=80">
<div class="post-content">
<h3>🤖 Robôs Submarinos</h3>
<p>
Os robôs submarinos são equipamentos desenvolvidos para explorar regiões profundas do oceano onde a presença humana não é possível devido à pressão extrema e à ausência de luz natural.
<br><br>
Eles são usados em pesquisas científicas, exploração de recursos e estudos do fundo do mar.
</p>

<div class="actions">
<button class="like" onclick="like(this)">👍 <span>0</span></button>
<button class="dislike" onclick="dislike(this)">👎 <span>0</span></button>
</div>

<div class="comment-box">
<input type="text" placeholder="Escreva um comentário..." onkeydown="addComment(event,this)">
<div class="comment-list"></div>
</div>

</div>
</div>

<div class="post">
<img src="https://images.unsplash.com/photo-1559827260-dc66d52bef19?auto=format&fit=crop&w=800&q=80">
<div class="post-content">
<h3>🛰️ Satélites Oceânicos</h3>
<p>
Satélites monitoram temperatura do oceano, clima e correntes marítimas em escala global.
<br><br>
Esses dados ajudam na previsão de tempestades e mudanças climáticas.
</p>

<div class="actions">
<button class="like" onclick="like(this)">👍 <span>0</span></button>
<button class="dislike" onclick="dislike(this)">👎 <span>0</span></button>
</div>

<div class="comment-box">
<input type="text" placeholder="Escreva um comentário..." onkeydown="addComment(event,this)">
<div class="comment-list"></div>
</div>

</div>
</div>

<div class="post">
<img src="https://images.unsplash.com/photo-1500375592092-40eb2168fd21?auto=format&fit=crop&w=800&q=80">
<div class="post-content">
<h3>🌊 Sensores Marinhos</h3>
<p>
Sensores coletam dados como temperatura, salinidade e poluição diretamente do oceano em tempo real.
<br><br>
Eles ajudam cientistas a entender melhor o ambiente marinho.
</p>

<div class="actions">
<button class="like" onclick="like(this)">👍 <span>0</span></button>
<button class="dislike" onclick="dislike(this)">👎 <span>0</span></button>
</div>

<div class="comment-box">
<input type="text" placeholder="Escreva um comentário..." onkeydown="addComment(event,this)">
<div class="comment-list"></div>
</div>

</div>
</div>

<div class="post">
<img src="https://images.unsplash.com/photo-1567899378494-47b22a2ae96a?auto=format&fit=crop&w=800&q=80">
<div class="post-content">
<h3>🚢 Navios Inteligentes</h3>
<p>
Navios modernos usam inteligência artificial para otimizar rotas e aumentar a segurança no transporte marítimo.
<br><br>
Isso reduz custos e melhora a eficiência.
</p>

<div class="actions">
<button class="like" onclick="like(this)">👍 <span>0</span></button>
<button class="dislike" onclick="dislike(this)">👎 <span>0</span></button>
</div>

<div class="comment-box">
<input type="text" placeholder="Escreva um comentário..." onkeydown="addComment(event,this)">
<div class="comment-list"></div>
</div>

</div>
</div>

<div class="post">
<img src="https://images.unsplash.com/photo-1504198453319-5ce911bafcde?auto=format&fit=crop&w=800&q=80">
<div class="post-content">
<h3>🔋 Energia das Ondas</h3>
<p>
A energia das ondas transforma o movimento do mar em eletricidade limpa e renovável.
<br><br>
É uma alternativa sustentável para o futuro.
</p>

<div class="actions">
<button class="like" onclick="like(this)">👍 <span>0</span></button>
<button class="dislike" onclick="dislike(this)">👎 <span>0</span></button>
</div>

<div class="comment-box">
<input type="text" placeholder="Escreva um comentário..." onkeydown="addComment(event,this)">
<div class="comment-list"></div>
</div>

</div>
</div>

</section>

<footer>
🌊 Oceano Inteligente - Desenvolvido por Maria Eduarda
</footer>

<script>

function toggleTema(){
document.body.classList.toggle("dark");
}

function like(btn){
let span = btn.querySelector("span");
span.innerText = Number(span.innerText) + 1;
}

function dislike(btn){
let span = btn.querySelector("span");
span.innerText = Number(span.innerText) + 1;
}

function addComment(event,input){
if(event.key === "Enter"){
let text = input.value.trim();
if(text === "") return;

let list = input.nextElementSibling;

let div = document.createElement("div");
div.innerText = "💬 " + text;

list.appendChild(div);

input.value = "";
}
}

document.getElementById("pesquisa").addEventListener("input", function(){
let texto = this.value.toLowerCase();

document.querySelectorAll(".post").forEach(post=>{
post.classList.toggle("hidden",
!post.innerText.toLowerCase().includes(texto)
);
});
});

</script>

</body>
</html>