<!doctype html>
<html lang="uz">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Simcard.uz — Login</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="wrap">
    <header>
      <h1>Simcard.uz — Smart Hisob Paneli</h1>
      <p class="subtitle">Login qilib davom eting (o‘zbekcha interfeys)</p>
    </header>

    <main id="main">
      <div class="card login-card">
        <h2>Kirish</h2>
        <label>Login (username)</label>
        <input id="username" placeholder="Masalan: Hasanboy.0101">
        <label>Parol</label>
        <input id="password" type="password" placeholder="Parolni kiriting">
        <div class="row">
          <button id="loginBtn">Kirish</button>
          <button id="demoBtn">Demo bilan kirish</button>
        </div>
        <p id="msg" class="msg"></p>
      </div>

      <div id="dashboard" class="hidden">
        <!-- Top bar -->
        <div class="topbar">
          <div>
            <strong id="userDisplay"></strong>
            <span id="roleDisplay"></span>
          </div>
          <div>
            <button id="logoutBtn">Chiqish</button>
          </div>
        </div>

        <div class="grid">
          <div class="card small">
            <h3>Bugungi kirim</h3>
            <div id="todayIncome">0 so'm</div>
          </div>
          <div class="card small">
            <h3>Bugungi chiqim</h3>
            <div id="todayExpense">0 so'm</div>
          </div>
          <div class="card small">
            <h3>Jami balans</h3>
            <div id="balance">0 so'm</div>
          </div>
          <div class="card small">
            <h3>Foyda (oy)</h3>
            <div id="monthProfit">0 so'm</div>
          </div>
        </div>

        <div class="card">
          <h3>Yangi kirim / chiqim qo'shish</h3>
          <div class="form-row">
            <select id="txType">
              <option value="income">Kirim</option>
              <option value="expense">Chiqim</option>
            </select>
            <input id="txAmount" type="number" placeholder="Summa (so'm)">
            <input id="txDate" type="date">
            <select id="txOperator">
              <option>Beeline</option>
              <option>Ucell</option>
              <option>Humans</option>
              <option>Mobiuz</option>
              <option>Boshqa</option>
            </select>
            <input id="txNote" placeholder="Izoh (ixtiyoriy)">
            <button id="addTxBtn">Qo'shish</button>
          </div>
        </div>

        <div class="card">
          <h3>Hisobot va tranzaksiyalar</h3>
          <div class="filters">
            <label>Davr: <input type="month" id="filterMonth"></label>
            <label>Operator: 
              <select id="filterOperator">
                <option value="">Hammasi</option>
                <option>Beeline</option>
                <option>Ucell</option>
                <option>Humans</option>
                <option>Mobiuz</option>
                <option>Boshqa</option>
              </select>
            </label>
            <button id="applyFilter">Filtrlash</button>
            <button id="exportCsv">CSV export</button>
          </div>
          <div id="txList"></div>
        </div>

        <div id="adminSection" class="card hidden">
          <h3>Admin boshqaruv</h3>
          <div class="form-row">
            <input id="newUserName" placeholder="Username">
            <select id="newUserRole">
              <option value="admin">Admin</option>
              <option value="seller">Sotuvchi</option>
            </select>
            <button id="addUserBtn">Foydalanuvchi qo'shish</button>
          </div>
          <p class="note">Yangi foydalanuvchi uchun parol avtomatik: username + 77</p>
          <div id="userTable"></div>
        </div>

      </div>
    </main>

    <footer>
      <small>Simcard.uz — demo. (Mahalliy saqlash: brauzer localStorage)</small>
    </footer>
  </div>

<script src="script.js"></script>
</body>
</html>