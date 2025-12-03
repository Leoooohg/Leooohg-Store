<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Leooohg | Panel + Login</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: system-ui, sans-serif;
    }

    body {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: radial-gradient(circle at top, #101827, #020617);
      color: #e5e7eb;
    }

    .hidden {
      display: none !important;
    }

    /* --- ESTILOS GENERALES DE TARJETAS --- */
    .wrapper {
      width: 100%;
      max-width: 900px;
      padding: 20px;
    }

    .card {
      background: rgba(15, 23, 42, 0.95);
      border-radius: 18px;
      padding: 26px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.45);
      border: 1px solid rgba(148,163,184,0.35);
      backdrop-filter: blur(10px);
    }

    /* PANEL */
    #panel {
      display: grid;
      grid-template-columns: minmax(0,1.3fr) minmax(0,1fr);
      gap: 18px;
    }

    @media (max-width: 720px) {
      #panel {
        grid-template-columns: 1fr;
      }
    }

    .user-header {
      display: flex;
      justify-content: space-between;
      margin-bottom: 10px;
    }

    .logout-btn {
      padding: 6px 12px;
      font-size: 0.75rem;
      border-radius: 999px;
      border: 1px solid #4f46e5;
      background: rgba(15,23,42,0.8);
      cursor: pointer;
      color: #fff;
    }

    /* Avatar */
    .avatar-wrap {
      display: flex;
      align-items: center;
      gap: 14px;
      margin-bottom: 14px;
    }

    .avatar {
      width: 70px;
      height: 70px;
      border-radius: 999px;
      overflow: hidden;
      border: 2px solid #60a5fa;
    }

    .avatar img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .socials {
      margin: 12px 0;
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .social-link {
      padding: 6px 10px;
      font-size: 0.8rem;
      border-radius: 999px;
      text-decoration: none;
      color: #fff;
      background: rgba(15,23,42,0.8);
      border: 1px solid #4f46e5;
      display: flex;
      gap: 6px;
    }

    .logo-big {
      width: 110px;
      height: 110px;
      border-radius: 30px;
      margin: auto;
      background: conic-gradient(#4f46e5,#06b6d4,#22c55e,#f97316,#4f46e5);
      padding: 4px;
    }

    .logo-inner {
      width: 100%;
      height: 100%;
      border-radius: 26px;
      background: #0f172a;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 2rem;
      font-weight: bold;
    }

    .btn-main {
      margin-top: 16px;
      width: 100%;
      padding: 12px;
      border-radius: 999px;
      border: none;
      background: linear-gradient(135deg,#4f46e5,#06b6d4);
      color: #fff;
      font-weight: bold;
      cursor: pointer;
    }

    /* LOGIN / REGISTER */
    #loginScreen {
      max-width: 420px;
      width: 100%;
    }

    .tabs {
      display: flex;
      background: rgba(15,23,42,0.8);
      border-radius: 999px;
      padding: 4px;
      border: 1px solid rgba(148,163,184,0.3);
      margin-bottom: 20px;
    }

    .tab {
      flex: 1;
      text-align: center;
      padding: 8px 0;
      color: #9ca3af;
      cursor: pointer;
      border-radius: 999px;
    }

    .tab.active {
      background: linear-gradient(135deg,#4f46e5,#06b6d4);
      color: #fff;
      font-weight: 600;
    }

    .form {
      animation: fadeIn 0.2s ease-out;
    }

    .btn-discord {
      width: 100%;
      padding: 10px;
      margin-bottom: 14px;
      border-radius: 12px;
      font-weight: 600;
      background: #5865f2;
      color: #fff;
      border: none;
      cursor: pointer;
    }

    .input {
      width: 100%;
      padding: 8px 10px;
      border-radius: 10px;
      border: 1px solid #475569;
      background: #0f172a;
      color: #fff;
      margin-bottom: 12px;
    }

    .btn-primary {
      width: 100%;
      padding: 10px;
      border-radius: 12px;
      border: none;
      background: linear-gradient(135deg,#4f46e5,#06b6d4);
      color: #fff;
      font-weight: 600;
      cursor: pointer;
    }

    .back-btn {
      margin-top: 14px;
      width: 100%;
      padding: 10px;
      border-radius: 12px;
      background: #334155;
      color: #fff;
      border: none;
      cursor: pointer;
    }

    @keyframes fadeIn {
      from {opacity:0; transform:translateY(6px)}
      to {opacity:1; transform:translateY(0)}
    }
  </style>
</head>
<body>

  <!-- ================= PANEL PRINCIPAL ================= -->
  <div id="panel" class="wrapper">
    <div class="card">
      <div class="user-header">
        <span>Usuario</span>
        <button class="logout-btn">Cerrar sesión</button>
      </div>

      <div class="avatar-wrap">
        <div class="avatar">
          <img src="https://avatars.githubusercontent.com/u/9919?s=200&v=4">
        </div>

        <div>
          <h2>Leooohg</h2>
          <p>Panel de usuario</p>
        </div>
      </div>

      <div class="socials">
        <a class="social-link" href="#"><span>💬</span>Discord</a>
        <a class="social-link" href="#"><span>▶️</span>YouTube</a>
        <a class="social-link" href="#"><span>📸</span>Instagram</a>
        <a class="social-link" href="#"><span>🛠️</span>Panel</a>
      </div>

      <div class="card" style="margin-top: 12px;">
        <p style="font-size: .8rem; color:#9ca3af">Reproduciendo</p>
        <h3>Track - Leooohg</h3>
      </div>
    </div>

    <div class="card" style="text-align: center;">
      <div class="logo-big">
        <div class="logo-inner">L</div>
      </div>

      <h1 style="margin-top: 16px;">Leooohg</h1>
      <p>Desarrollador</p>

      <button class="btn-main" onclick="goLogin()">Acceder</button>
    </div>
  </div>


  <!-- ================= LOGIN / REGISTER ================= -->
  <div id="loginScreen" class="wrapper hidden">
    <div class="card">
      <div style="font-size: 1.4rem; font-weight: bold; margin-bottom: 6px;">Bienvenido</div>
      <p style="color:#9ca3af; margin-bottom: 16px;">Ingresa tus credenciales</p>

      <div class="tabs">
        <div class="tab active" onclick="showForm('loginForm')">Iniciar sesión</div>
        <div class="tab" onclick="showForm('registerForm')">Crear cuenta</div>
      </div>

      <!-- LOGIN -->
      <div id="loginForm" class="form">
        <button class="btn-discord">Continuar con Discord</button>

        <input class="input" placeholder="Usuario">
        <input class="input" type="password" placeholder="Contraseña">

        <button class="btn-primary">Ingresar</button>
      </div>

      <!-- REGISTER -->
      <div id="registerForm" class="form hidden">
        <button class="btn-discord">Registrarse con Discord</button>

        <input class="input" placeholder="Usuario">
        <input class="input" type="password" placeholder="Contraseña">
        <input class="input" type="password" placeholder="Confirmar">

        <button class="btn-primary">Crear cuenta</button>
      </div>

      <button class="back-btn" onclick="goPanel()">Volver</button>
    </div>
  </div>


  <script>
    function goLogin(){
      document.getElementById("panel").classList.add("hidden");
      document.getElementById("loginScreen").classList.remove("hidden");
    }

    function goPanel(){
      document.getElementById("loginScreen").classList.add("hidden");
      document.getElementById("panel").classList.remove("hidden");
    }

    function showForm(formId){
      document.getElementById("loginForm").classList.add("hidden");
      document.getElementById("registerForm").classList.add("hidden");

      document.getElementById(formId).classList.remove("hidden");

      document.querySelectorAll(".tab").forEach(t=>t.classList.remove("active"));
      if(formId==="loginForm") document.querySelectorAll(".tab")[0].classList.add("active");
      else document.querySelectorAll(".tab")[1].classList.add("active");
    }
  </script>

</body>
</html>
