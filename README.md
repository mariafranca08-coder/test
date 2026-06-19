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

.like{background:#00d4ff; color: #000; font-weight: bold;}
.dislike{background:#ff4d4d; color: #fff; font-weight: bold;}

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
color: #333;
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
<p>Tecnologia e inovação nos oceanos</p>
</div>

<div class="search-box">
<input type="text" id="pesquisa" placeholder="Pesquisar posts...">
</div>

<section class="posts" id="posts">

<div class="post">
<img src="data:image/jpeg;base64,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