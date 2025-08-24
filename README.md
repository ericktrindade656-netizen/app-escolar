// ===================== CRIA ELEMENTOS HTML =====================
document.body.innerHTML = `
<header>📚 App Escolar Interativo</header>

<div id="chooseLoginPage" class="container">
  <h2>👋 Bem-vindo</h2>
  <button class="btn" onclick="showPage('userLoginPage')">Login Estudante</button>
  <button class="btn" onclick="showPage('adminLoginPage')">Login Administrador</button>
  <button class="btn" onclick="showPage('registerPage')">Criar Nova Conta</button>
</div>

<div id="userLoginPage" class="container hidden">
  <h2>🔐 Login Estudante</h2>
  <input type="text" id="userId" placeholder="Digite seu ID">
  <input type="password" id="userSenha" placeholder="Digite sua senha">
  <button class="btn" onclick="loginUser()">Entrar</button>
  <button class="btn back" onclick="showPage('chooseLoginPage')">Voltar</button>
</div>

<div id="adminLoginPage" class="container hidden">
  <h2>⚙️ Login Administrador</h2>
  <input type="text" id="adminId" placeholder="ID do administrador">
  <input type="password" id="adminSenha" placeholder="Senha do administrador">
  <button class="btn" onclick="loginAdmin()">Entrar</button>
  <button class="btn back" onclick="showPage('chooseLoginPage')">Voltar</button>
</div>

<div id="registerPage" class="container hidden">
  <h2>📝 Criar Conta</h2>
  <input type="text" id="newId" placeholder="Escolha um ID">
  <input type="password" id="newSenha" placeholder="Escolha uma senha">
  <button class="btn" onclick="createUser()">Enviar Solicitação</button>
  <button class="btn back" onclick="showPage('chooseLoginPage')">Voltar</button>
</div>

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
`;

// ===================== AQUI VEM TODO O JS DO APP =====================
// Cole aqui o conteúdo do script.js que eu te passei anteriormente
// incluindo STORAGE_KEYS, DEFAULT_MENU, funções loginUser, loginAdmin, createUser,
// approveUser, rejectUser, loadUserData, loadAdminData, saveMenuAdmin, updateClock etc.

// Exemplo:
const STORAGE_KEYS = { USERS:'appUsers', PENDING:'pendingUsers', MENU:'weeklyMenu' };
const DAYS=['segunda','terca','quarta','quinta','sexta'];
const DEFAULT_MENU={
  segunda:{cafe:'Pão e leite', merenda:'Banana', almoco:'Arroz, feijão e frango', cafeTarde:'Bolo e suco', esporte:'Futsal'},
  terca:{cafe:'Biscoito e suco', merenda:'Maçã', almoco:'Macarrão e frango', cafeTarde:'Pão doce', esporte:'Basquete'},
  quarta:{cafe:'Cuscuz com ovo', merenda:'Melancia', almoco:'Arroz, peixe', cafeTarde:'Bolacha', esporte:'Queimada'},
  quinta:{cafe:'Tapioca', merenda:'Pera', almoco:'Arroz, feijão e peixe', cafeTarde:'Bolo de cenoura', esporte:'Vôlei'},
  sexta:{cafe:'Pão com queijo', merenda:'Laranja', almoco:'Feijoada', cafeTarde:'Biscoito', esporte:'Futebol'}
};

if(!localStorage.getItem(STORAGE_KEYS.USERS)) localStorage.setItem(STORAGE_KEYS.USERS,JSON.stringify({}));
if(!localStorage.getItem(STORAGE_KEYS.PENDING)) localStorage.setItem(STORAGE_KEYS.PENDING,JSON.stringify([]));
if(!localStorage.getItem(STORAGE_KEYS.MENU)) localStorage.setItem(STORAGE_KEYS.MENU,JSON.stringify(DEFAULT_MENU));

// (Continue copiando todo o JS das funções aqui, exatamente igual ao script.js anterior)
