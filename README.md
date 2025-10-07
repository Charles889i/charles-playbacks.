<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Loja de Playbacks</title>
  <style>
  .pix-info {
    font-family: 'Poppins', sans-serif;
    background-color: #f0f0f0;
    padding: 15px;
    border-radius: 10px;
    margin-bottom: 15px;
    text-align: center;
  }

  .pix-info p {
    font-size: 18px;
    color: #333;
    margin: 8px 0;
  }

  .pix-button {
    background-color: #25d366;
    color: white;
    padding: 10px 20px;
    border: none;
    font-size: 16px;
    border-radius: 8px;
    cursor: pointer;
    font-family: 'Poppins', sans-serif;
    margin-top: 10px;
  }
</style>
  <style>
    :root{
      --amarelo:#ffd400;
      --cinza:#f5f5f7;
      --texto:#0f1115;
      --muted:#6b7280;
      --cta:#2563eb;
      --danger:#ef4444;
      --ok:#16a34a;
      --radius:18px;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial;
      color:var(--texto);
      background:#fff;
      min-height:100dvh;
      display:flex; flex-direction:column;
    }
    .topbar{background:var(--amarelo); padding:12px 16px; position:sticky; top:0; z-index:5}
    .topbar .search{display:flex; align-items:center; gap:10px; max-width:900px; margin:0 auto;}
    input[type="search"]{flex:1; padding:14px 16px; border-radius:999px; border:none; outline:none; font-size:16px;}
    .bell{position:relative; width:36px; height:36px; border-radius:50%; display:grid; place-items:center}
    .badge{position:absolute; right:-2px; top:-2px; background:#f43f5e; color:#fff; font-weight:700; border-radius:999px; padding:2px 6px; font-size:12px}
    main{flex:1; max-width:1100px; width:100%; margin:0 auto; padding:12px 16px 88px}
    h1{font-size:32px; margin:14px 6px}
    .grid{display:grid; grid-template-columns:repeat(auto-fill,minmax(220px,1fr)); gap:14px}
    .card{border:1px solid #e5e7eb; border-radius:18px; overflow:hidden; background:#fff; box-shadow:0 2px 6px rgba(0,0,0,.05); transition:.2s}
    .card:hover{transform:translateY(-2px); box-shadow:0 6px 12px rgba(0,0,0,.1)}
    .cover{aspect-ratio:1/1; width:100%; object-fit:cover; background:var(--cinza)}
    .card-body{padding:12px}
    .title{font-weight:700; font-size:16px; margin:2px 0 4px}
    .price{color:#111827; font-weight:800}
    .muted{color:var(--muted); font-size:13px}
    .row{display:flex; align-items:center; gap:8px}
    .row.space{justify-content:space-between}

    /* Botões mais bonitos */
    .btn{
      padding:12px 14px;
      border-radius:14px;
      border:none;
      font-weight:600;
      cursor:pointer;
      font-size:15px;
      transition:all .2s ease;
      box-shadow:0 2px 5px rgba(0,0,0,.1);
    }
    .btn:hover{transform:translateY(-2px); box-shadow:0 6px 12px rgba(0,0,0,.15)}
    .btn:active{transform:scale(.95); box-shadow:0 2px 4px rgba(0,0,0,.2)}
    .btn.primary{background:var(--cta); color:#fff;}
    .btn.danger{background:var(--danger); color:#fff;}
    .btn.ghost{background:#fff; border:1px solid #e5e7eb;}
    .btn.full{width:100%}

    audio{width:100%}
    .tabbar{position:fixed; left:0; right:0; bottom:0; height:70px; border-top:1px solid #e5e7eb; background:#fff; display:grid; grid-template-columns:repeat(5,1fr);}
    .tab{display:flex; flex-direction:column; align-items:center; justify-content:center; gap:4px; font-size:12px; color:#6b7280; border:none; background:none; cursor:pointer; transition:.2s}
    .tab.active{color:#111827; font-weight:700}
    .tab:hover{color:#2563eb; transform:scale(1.05)}
    .bubble{position:absolute; transform:translate(12px,-10px); background:#2563eb; color:#fff; border-radius:999px; padding:2px 6px; font-size:12px}
    .section{display:none}
    .section.active{display:block}
    .panel{max-width:720px; margin:6px auto; padding:16px; background:#fff; border:1px solid #e5e7eb; border-radius:18px}
    .field{display:grid; gap:6px; margin-bottom:12px}
    label{font-size:13px; color:#374151}
    input[type="text"], input[type="number"], input[type="file"]{padding:10px 12px; border-radius:12px; border:1px solid #d1d5db}
    .empty{color:#9ca3af; text-align:center; padding:40px 12px}
    .inline{display:flex; gap:8px; align-items:center}
    .right{margin-left:auto}
    .pill{background:#eef2ff; color:#3730a3; padding:4px 8px; border-radius:12px; font-size:12px}
    
  </style>
  <head>
  ...
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap" rel="stylesheet">
  ...
</head>
</head>
<body>
  <!-- TOPO -->
  <header class="topbar">
    <div class="search">
      <input id="search" type="search" placeholder="Buscar" autocomplete="off" />
      <div class="bell" title="Notificações">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none"><path d="M12 22a2.5 2.5 0 0 0 2.45-2h-4.9A2.5 2.5 0 0 0 12 22Zm7-6V11a7 7 0 1 0-14 0v5l-2 2v1h18v-1l-2-2Z" fill="#111827"/></svg>
        <span class="badge" id="badge">4</span>
      </div>
    </div>
  </header>

  <!-- PRINCIPAL -->
  <main>
    <h1 id="titulo">Início</h1>

    <!-- Seções -->
    <section id="home" class="section active">
      <div id="list" class="grid"></div>
      <p id="home-empty" class="empty" style="display:none">Nenhum playback cadastrado ainda.</p>
    </section>

    <section id="downloads" class="section">
      <div class="panel">
        <div class="inline"><strong>Downloads</strong><span class="pill" id="qtyDownloads">0</span></div>
        <div id="downloadsList" class="grid" style="margin-top:12px"></div>
        <p id="downloads-empty" class="empty" style="display:none">Você ainda não baixou nada.</p>
      </div>
    </section>

    <section id="carrinho" class="section">
      <div class="panel">
        <div class="inline"><strong>Seu carrinho</strong><span class="pill right" id="qtyCart">0</span></div>
        <div id="cartList" class="grid" style="margin-top:12px"></div>
        <p id="cart-empty" class="empty" style="display:none">Seu carrinho está vazio.</p>
        <div class="row space" style="margin-top:16px">
          <div class="muted" id="cartTotal">Total: R$ 0,00</div>
          <button class="btn primary" id="checkoutBtn">Excluir</button>
          <!-- Botão Pagar com PIX -->
<div style="margin-top: 12px;">
  <!-- BOTÃO PAGAR COM PIX -->
<button onclick="mostrarPix()" style="background-color: #28a745; color: white; padding: 10px 20px; border: none; border-radius: 8px; font-family: 'Poppins', sans-serif;">Pagar com Pix</button>

<!-- ÁREA PARA EXIBIR CHAVE PIX -->
<div id="infoPix" style="margin-top: 10px;"></div>
  <div id="qrpix" style="display:none; margin-top:10px; text-align:center;">
    <img src="link-do-seu-qr-code.png" alt="QR Code PIX" width="200" />
    <p>Escaneie com o app do seu banco</p>
        </div>
      </div>
    </section>

    <section id="admin" class="section">
      <div class="panel">
        <form id="form">
          <div class="field"><label>Título</label><input id="tituloInput" type="text" required /></div>
          <div class="field"><label>Preço (R$)</label><input id="precoInput" type="number" step="0.01" value="9.90" required /></div>
          <div class="field"><label>Capa</label><input id="capaInput" type="file" accept="image/*" required /></div>
          <div class="field"><label>Áudio</label><input id="audioInput" type="file" accept="audio/*" required /></div>
          <button class="btn primary full" type="submit">Salvar playback</button>
        </form>
      </div>
      <div class="panel">
        <strong>Playbacks cadastrados</strong>
        <div id="adminList" class="grid" style="margin-top:12px"></div>
        <p id="admin-empty" class="empty" style="display:none">Sem itens cadastrados.</p>
      </div>
    </section>

    <section id="menu" class="section">
      <div class="panel"><strong>Menu</strong><p class="muted">Links e informações da sua loja.</p></div>
    </section>
  </main>

  <!-- BARRA DE NAVEGAÇÃO -->
  <nav class="tabbar">
    <button class="tab active" data-tab="home">🏠<span>Início</span></button>
    <button class="tab" data-tab="carrinho" style="position:relative">🛒<span>Carrinho</span><span class="bubble" id="cartCount">0</span></button>
    <button class="tab" onclick="abrirAdmin()">⚙<span>Admin</span></button>
    <button class="tab" data-tab="menu">☰<span>Menu</span></button>
  </nav>

  <!-- SCRIPT -->
  <script>
  const DB_NAME='playbacksDB'; const DB_VER=1; let db;
  function openDB(){return new Promise((res,rej)=>{const r=indexedDB.open(DB_NAME,DB_VER);r.onupgradeneeded=e=>{const d=e.target.result;if(!d.objectStoreNames.contains('items'))d.createObjectStore('items',{keyPath:'id',autoIncrement:true})};r.onsuccess=()=>{db=r.result;res(db)};r.onerror=()=>rej(r.error)});}
  function tx(store,mode='readonly'){return db.transaction(store,mode).objectStore(store);}
  async function addItem(it){return new Promise((res,rej)=>{const r=tx('items','readwrite').add(it);r.onsuccess=()=>res(r.result);r.onerror=()=>rej(r.error)})}
  async function getAll(){return new Promise((res,rej)=>{const r=tx('items').getAll();r.onsuccess=()=>res(r.result||[]);r.onerror=()=>rej(r.error)})}
  async function delItem(id){return new Promise((res,rej)=>{const r=tx('items','readwrite').delete(id);r.onsuccess=()=>res();r.onerror=()=>rej(r.error)})}
  const fmt=n=>n.toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
  let ITEMS=[]; let CART=JSON.parse(localStorage.getItem('cart')||'[]');
  function saveCart(){localStorage.setItem('cart',JSON.stringify(CART))}
  function el(t,a={},c=[]){const e=document.createElement(t);Object.entries(a).forEach(([k,v])=>{if(k==='class')e.className=v;else if(k==='html')e.innerHTML=v;else e.setAttribute(k,v)});c.forEach(ch=>e.appendChild(ch));return e;}
  function fileToDataURL(f){return new Promise((res,rej)=>{const r=new FileReader();r.onload=()=>res(r.result);r.onerror=rej;r.readAsDataURL(f);});}
  function fileToBlob(f){return new Promise((res,rej)=>{const r=new FileReader();r.onload=()=>res(new Blob([r.result]));r.onerror=rej;r.readAsArrayBuffer(f);});}

  function renderHome(){const list=document.getElementById('list');list.innerHTML='';const q=document.getElementById('search').value.toLowerCase();const rows=ITEMS.filter(i=>i.title.toLowerCase().includes(q));document.getElementById('home-empty').style.display=rows.length?'none':'block';rows.forEach(it=>{const card=el('div',{class:'card'});const img=el('img',{class:'cover',src:it.cover});const body=el('div',{class:'card-body'});const t=el('div',{class:'title',html:it.title});const p=el('div',{class:'price',html:fmt(it.price)});// cria o elemento <audio>
const audio = el('audio',{controls:true, controlsList:"nodownload noplaybackrate"});
audio.src = URL.createObjectURL(it.audio);

// limita o preview a 120 segundos
const MAX_PREVIEW = 120;

audio.addEventListener('timeupdate', () => {
  if (audio.currentTime >= MAX_PREVIEW) {
    audio.pause();
    audio.currentTime = 0; // volta pro início (se quiser só pausar, tire essa linha)
    alert("Prévia de 2 minuto encerrada. Compre para ouvir completo!");
  }
});

audio.addEventListener('seeking', () => {
  if (audio.currentTime > MAX_PREVIEW) {
    audio.currentTime = MAX_PREVIEW;
  }
});const btn=el('button',{class:'btn primary full'});btn.textContent='Comprar Agora';btn.onclick=()=>{CART.push(it.id);updateCart();saveCart();};body.appendChild(t);body.appendChild(p);body.appendChild(audio);body.appendChild(btn);card.appendChild(img);card.appendChild(body);list.appendChild(card);});}
  function renderAdmin(){const list=document.getElementById('adminList');list.innerHTML='';document.getElementById('admin-empty').style.display=ITEMS.length?'none':'block';ITEMS.forEach(it=>{const card=el('div',{class:'card'});const img=el('img',{class:'cover',src:it.cover});const body=el('div',{class:'card-body'});const t=el('div',{class:'title',html:it.title});const p=el('div',{class:'muted',html:`Preço: ${fmt(it.price)}`});const rm=el('button',{class:'btn danger full'});rm.textContent='Remover';rm.onclick=async()=>{await delItem(it.id);await hydrate();};body.appendChild(t);body.appendChild(p);body.appendChild(rm);card.appendChild(img);card.appendChild(body);list.appendChild(card);});}
  function renderCart(){const items=CART.map(id=>ITEMS.find(i=>i.id===id)).filter(Boolean);const wrap=document.getElementById('cartList');wrap.innerHTML='';let total=0;items.forEach(i=>total+=Number(i.price)||0);document.getElementById('cartTotal').textContent=`Total: ${fmt(total)}`;document.getElementById('cart-empty').style.display=items.length?'none':'block';items.forEach(it=>{const card=el('div',{class:'card'});const img=el('img',{class:'cover',src:it.cover});const body=el('div',{class:'card-body'});const t=el('div',{class:'title',html:it.title});const p=el('div',{class:'price',html:fmt(it.price)});const rm=el('button',{class:'btn danger full'});rm.textContent='Remover do carrinho';rm.onclick=()=>{CART=CART.filter(id=>id!==it.id);saveCart();updateCart();renderCart();};body.appendChild(t);body.appendChild(p);body.appendChild(rm);card.appendChild(img);card.appendChild(body);wrap.appendChild(card);});}
  function updateCart(){document.getElementById('cartCount').textContent=CART.length;document.getElementById('qtyCart').textContent=CART.length;}
  async function hydrate(){await openDB();ITEMS=await getAll();renderHome();renderAdmin();renderCart();updateCart();}
  document.querySelectorAll('.tab').forEach(b=>b.addEventListener('click',()=>{document.querySelectorAll('.tab').forEach(x=>x.classList.remove('active'));b.classList.add('active');const t=b.dataset.tab;document.getElementById('titulo').textContent=t==='home'?'Início':t.charAt(0).toUpperCase()+t.slice(1);document.querySelectorAll('.section').forEach(s=>s.classList.remove('active'));document.getElementById(t).classList.add('active');if(t==='carrinho')renderCart();}));
  document.getElementById('search').addEventListener('input',renderHome);
  document.getElementById('form').addEventListener('submit',async e=>{e.preventDefault();const title=document.getElementById('tituloInput').value.trim();const price=parseFloat(document.getElementById('precoInput').value||'0');const capa=document.getElementById('capaInput').files[0];const audioF=document.getElementById('audioInput').files[0];if(!title||!capa||!audioF)return alert('Preencha todos os campos');const cover=await fileToDataURL(capa);const audio=await fileToBlob(audioF);await addItem({title,price,cover,audio});e.target.reset();await hydrate();alert('Playback cadastrado!');});
  document.getElementById('checkoutBtn').addEventListener('click',()=>{if(!CART.length)return alert('Carrinho vazio');CART=[];saveCart();updateCart();renderCart();alert('Excluido com sucesso !')});
  hydrate();
  </script>
  <script>
  function abrirAdmin() {
    const senhaCorreta = "C626G7@#"; // 🔑 coloque a senha que você quiser
    const senha = prompt("Acesso Apenas para admin:");

    if (senha === senhaCorreta) {
      // Ativa a aba do Admin manualmente
      document.querySelectorAll(".section").forEach(sec => sec.classList.remove("active"));
      document.getElementById("admin").classList.add("active");
      document.getElementById("titulo").textContent = "Admin";

      // Também remove destaque dos outros botões
      document.querySelectorAll(".tab").forEach(btn => btn.classList.remove("active"));
      event.currentTarget.classList.add("active");
    } else {
      alert("Você não é um Admin!");
    }
  }
</script>
<script>
  function mostrarPix() {
    const divPix = document.getElementById("infoPix");
    divPix.innerHTML = `
      <div class="pix-info">
        <p><strong>Chave Pix:</strong> 88994387701</p>
        <a href="https://wa.me/5588994387701" target="_blank">
          <button class="pix-button">Enviar comprovante</button>
        </a>
      </div>
    `;
    divPix.style.display = "block";
  }
</script>
</body>
</html>
