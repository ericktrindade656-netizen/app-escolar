<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>App Escolar - Cardápio Interativo</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

body { font-family:'Roboto', sans-serif; margin:0; padding:0; background:#e0f7fa; }
header { background: linear-gradient(135deg,#00796b,#004d40); color:#fff; text-align:center; padding:25px 20px; font-size:28px; font-weight:700; border-bottom-left-radius:20px; border-bottom-right-radius:20px; box-shadow:0 4px 8px rgba(0,0,0,0.2);}
.container { padding:20px; }
.card { background:#fff; margin:15px 0; padding:20px; border-radius:15px; box-shadow:0 4px 8px rgba(0,0,0,0.1); transition:0.3s; }
.card:hover { transform:translateY(-3px); box-shadow:0 6px 12px rgba(0,0,0,0.15); }
h2 { color:#004d40; margin-top:0; }
input, select { width:100%; padding:12px; margin:8px 0; border-radius:8px; border:1px solid #ccc; font-size:16px; }
.btn { background:#00796b; color:white; border:none; padding:14px; margin-top:10px; width:100%; border-radius:12px; font-size:16px; cursor:pointer; transition:0.3s; }
.btn:hover { background:#004d40; }
.back { background:#d32f2f; }
.back:hover { background:#b71c1c; }
.hidden { display:none; }
ul { padding-left:20px; }
</style>
</head>
<body>

<header>📚 App Escolar Interativo</header>

<!-- ESCOLHA LOGIN -->
<div id="chooseLoginPage" class="container">
  <h2>👋 Bem-vindo</h2>
  <button class="btn" onclick="showPage('userLoginPage')">Login Estudante</button>
  <button class="btn" onclick="showPage('adminLoginPage')">Login Administrador</button>
  <button class="btn" onclick="showPage('registerPage')">Criar Nova Conta</button>
</div>

<!-- LOGIN USUÁRIO -->
<div id="userLoginPage" class="container hidden">
  <h2>🔐 Login Estudante</h2>
  <input type="text" id="userId" placeholder="Digite seu ID">
  <input type="password" id="userSenha" placeholder="Digite sua senha">
  <button class="btn" onclick="loginUser()">Entrar</button>
  <button class="btn back" onclick="showPage('chooseLoginPage')">Voltar</button>
</div>

<!-- LOGIN ADMIN -->
<div id="adminLoginPage" class="container hidden">
  <h2>⚙️ Login Administrador</h2>
  <input type="text" id="adminId" placeholder="ID do administrador">
  <input type="password" id="adminSenha" placeholder="Senha do administrador">
  <button class="btn" onclick="loginAdmin()">Entrar</button>
  <button class="btn back" onclick="showPage('chooseLoginPage')">Voltar</button>
</div>

<!-- CADASTRO -->
<div id="registerPage" class="container hidden">
  <h2>📝 Criar Conta</h2>
  <input type="text" id="newId" placeholder="Escolha um ID">
  <input type="password" id="newSenha" placeholder="Escolha uma senha">
  <button class="btn" onclick="createUser()">Enviar Solicitação</button>
  <button class="btn back" onclick="showPage('chooseLoginPage')">Voltar</button>
</div>

<!-- USUÁRIO -->
<div id="userPage" class="container hidden">
  <h2>Bem-vindo, Estudante 👩‍🎓</h2>

  <div class="card">
    <h3>🕒 Relógio Atual</h3>
    <p id="clock" style="font-size:22px; font-weight:bold;"></p>
    <p>Dia da semana: <span id="currentDay"></span></p>
  </div>

  <div class="card">
    <label>Selecione o dia:</label>
    <select id="userDaySelect" onchange="loadUserData()">
      <option value="segunda">Segunda-feira</option>
      <option value="terca">Terça-feira</option>
      <option value="quarta">Quarta-feira</option>
      <option value="quinta">Quinta-feira</option>
      <option value="sexta">Sexta-feira</option>
    </select>
  </div>

  <div class="card">
    <p><strong>🏀 Esporte do Dia:</strong> <span id="dailySport"></span></p>
    <p><strong>🍽️ Cardápio do Dia:</strong></p>
    <ul>
      <li>Café da manhã: <span id="cafeManha"></span></li>
      <li>Merenda da manhã: <span id="merendaManha"></span></li>
      <li>Almoço: <span id="almoco"></span></li>
      <li>Café da tarde: <span id="cafeTarde"></span></li>
    </ul>
  </div>

  <button class="btn back" onclick="logout()">Sair</button>
</div>

<!-- ADMIN -->
<div id="adminPage" class="container hidden">
  <h2>Bem-vindo, Administrador ⚙️</h2>

  <div class="card">
    <h3>👥 Solicitações Pendentes</h3>
    <ul id="pendingList"></ul>
  </div>

  <div class="card">
    <h3>✏️ Atualizar Cardápio</h3>
    <label>Selecione o dia:</label>
    <select id="adminDaySelect" onchange="loadAdminData()">
      <option value="segunda">Segunda-feira</option>
      <option value="terca">Terça-feira</option>
      <option value="quarta">Quarta-feira</option>
      <option value="quinta">Quinta-feira</option>
      <option value="sexta">Sexta-feira</option>
    </select>
    <input type="text" id="updateSport" placeholder="Esporte do dia">
    <input type="text" id="updateCafe" placeholder="Café da manhã">
    <input type="text" id="updateMerenda" placeholder="Merenda da manhã">
    <input type="text" id="updateAlmoco" placeholder="Almoço">
    <input type="text" id="updateCafeTarde" placeholder="Café da tarde">
    <button class="btn" onclick="saveMenuAdmin()">Salvar Cardápio</button>
  </div>

  <button class="btn back" onclick="logout()">Sair</button>
</div>

<script>
// ===================== CONSTANTES =====================
const STORAGE_KEYS = { USERS:'appUsers', PENDING:'pendingUsers', MENU:'weeklyMenu' };
const DAYS=['segunda','terca','quarta','quinta','sexta'];
const DEFAULT_MENU={
  segunda:{cafe:'Pão e leite', merenda:'Banana', almoco:'Arroz, feijão e frango', cafeTarde:'Bolo e suco', esporte:'Futsal'},
  terca:{cafe:'Biscoito e suco', merenda:'Maçã', almoco:'Macarrão e frango', cafeTarde:'Pão doce', esporte:'Basquete'},
  quarta:{cafe:'Cuscuz com ovo', merenda:'Melancia', almoco:'Arroz, peixe', cafeTarde:'Bolacha', esporte:'Queimada'},
  quinta:{cafe:'Tapioca', merenda:'Pera', almoco:'Arroz, feijão e peixe', cafeTarde:'Bolo de cenoura', esporte:'Vôlei'},
  sexta:{cafe:'Pão com queijo', merenda:'Laranja', almoco:'Feijoada', cafeTarde:'Biscoito', esporte:'Futebol'}
};

// Inicializa localStorage
if(!localStorage.getItem(STORAGE_KEYS.USERS)) localStorage.setItem(STORAGE_KEYS.USERS,JSON.stringify({}));
if(!localStorage.getItem(STORAGE_KEYS.PENDING)) localStorage.setItem(STORAGE_KEYS.PENDING,JSON.stringify([]));
if(!localStorage.getItem(STORAGE_KEYS.MENU)) localStorage.setItem(STORAGE_KEYS.MENU,JSON.stringify(DEFAULT_MENU));

// ===================== PÁGINAS =====================
function showPage(pageId){ document.querySelectorAll('.container').forEach(c=>c.classList.add('hidden')); document.getElementById(pageId).classList.remove('hidden'); }
function logout(){ showPage('chooseLoginPage'); }

// ===================== LOGIN / CADASTRO =====================
function loginUser(){
  const id=document.getElementById('userId').value.trim();
  const senha=document.getElementById('userSenha').value.trim();
  const users=JSON.parse(localStorage.getItem(STORAGE_KEYS.USERS));
  if(users[id]){ if(users[id].approved){ showPage('userPage'); loadUserData(); } else { alert('⏳ Usuário ainda não aprovado pelo administrador.'); } } else { alert('❌ ID ou senha incorretos.'); }
}

function loginAdmin(){
  const id=document.getElementById('adminId').value.trim();
  const senha=document.getElementById('adminSenha').value.trim();
  if(id==='admin' && senha==='1234'){ showPage('adminPage'); loadPendingUsers(); loadAdminData(); } else { alert('❌ Administrador inválido!'); }
}

function createUser(){
  const id=document.getElementById('newId').value.trim();
  const senha=document.getElementById('newSenha').value.trim();
  if(!id||!senha){ alert('Preencha todos os campos!'); return; }
  const pending=JSON.parse(localStorage.getItem(STORAGE_KEYS.PENDING));
  pending.push({id:id,senha:senha});
  localStorage.setItem(STORAGE_KEYS.PENDING,JSON.stringify(pending));
  alert('✅ Solicitação enviada! Aguarde aprovação do administrador.');
  showPage('chooseLoginPage');
}

// ===================== ADMIN =====================
function loadPendingUsers(){
  const pending=JSON.parse(localStorage.getItem(STORAGE_KEYS.PENDING));
  const list=document.getElementById('pendingList');
  list.innerHTML='';
  pending.forEach((u,i)=>{ const li=document.createElement('li'); li.innerHTML=`${u.id} <button onclick="approveUser(${i})">Aprovar</button> <button onclick="rejectUser(${i})">Rejeitar</button>`; list.appendChild(li); });
}

function approveUser(index){
  const pending=JSON.parse(localStorage.getItem(STORAGE_KEYS.PENDING));
  const users=JSON.parse(localStorage.getItem(STORAGE_KEYS.USERS));
  const user=pending[index];
  users[user.id]={senha:user.senha,approved:true};
  localStorage.setItem(STORAGE_KEYS.USERS,JSON.stringify(users));
  pending.splice(index,1);
  localStorage.setItem(STORAGE_KEYS.PENDING,JSON.stringify(pending));
  loadPendingUsers();
  alert(`${user.id} aprovado!`);
}

function rejectUser(index){
  let pending=JSON.parse(localStorage.getItem(STORAGE_KEYS.PENDING));
  pending.splice(index,1);
  localStorage.setItem(STORAGE_KEYS.PENDING,JSON.stringify(pending));
  loadPendingUsers();
