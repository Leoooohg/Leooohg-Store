<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Leooohg | Panel</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <style>
    @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap");

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: "Poppins", sans-serif;
    }

    body {
      background: #040714;
      overflow: hidden;
      color: white;
      height: 100vh;
    }

    canvas#stars {
      position: fixed;
      inset: 0;
      z-index: -1;
    }

    .hidden { display: none !important; }

    .screen {
      position: fixed;
      inset: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
    }

    /* LOGIN / REGISTRO */
    .auth-card {
      width: 100%;
      max-width: 420px;
      padding: 30px 26px;
      border-radius: 24px;
      background: #12163a;
      box-shadow: 0 0 40px #000;
      border: 1px solid rgba(255,255,255,.1);
    }

    .auth-title {
      text-align: center;
      font-size: 1.7rem;
      color: #c7d2fe;
      font-weight: 700;
      margin-bottom: 6px;
    }

    .auth-subtitle {
      text-align: center;
      color: #9ca3af;
      font-size: .9rem;
      margin-bottom: 20px;
    }

    .field-input {
      width: 100%;
      border-radius: 12px;
      border: 1px solid #293060;
      background: #0f1333;
      padding: 10px 12px;
      color: white;
      margin-bottom: 14px;
      outline: none;
    }

    .btn-primary {
      width: 100%;
      border-radius: 12px;
      padding: 12px;
      font-size: 1rem;
      background: linear-gradient(135deg,#6366f1,#8b5cf6);
      border: none;
      color: white;
      font-weight: 600;
      margin-top: 8px;
      cursor: pointer;
    }

    .switch-link {
      text-align: center;
      font-size: .82rem;
      color: #9ca3af;
      margin-top: 12px;
    }
    .switch-link button {
      border: none;
      background: none;
      color: #818cf8;
      text-decoration: underline;
      cursor: pointer;
    }

    /* PANEL */
    .panel-wrapper {
      width: 100%;
      max-width: 420px;
    }
    .panel-card {
      padding: 30px 28px;
      border-radius: 26px;
      background: #13183d;
      border: 1px solid rgba(255,255,255,.05);
      box-shadow: 0 0 40px #000;
    }

    .panel-avatar {
      width: 130px;
      height: 130px;
      border-radius: 50%;
      overflow: hidden;
      margin: 0 auto;
      border: 4px solid #8b5cf6;
      box-shadow: 0 0 30px #8b5cf6aa;
    }
    .panel-avatar img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .panel-title {
      text-align: center;
      font-size: 2.2rem;
      margin-top: 14px;
      background: linear-gradient(135deg,#22d3ee,#a855f7);
      -webkit-background-clip: text;
      color: transparent;
    }

    .panel-role {
      text-align: center;
      font-size: .88rem;
      letter-spacing: .5rem;
      margin-top: 6px;
      color: #9ca3af;
    }

    #typing {
      text-align: center;
      font-size: .92rem;
      margin-top: 8px;
      color: #c7d2fe;
      white-space: nowrap;
      overflow: hidden;
      border-right: 2px solid #c7d2fe;
      animation: caret .8s infinite;
    }

    @keyframes caret {
      50% { border-color: transparent; }
    }

    .circle-btn {
      width: 54px;
      height: 54px;
      border-radius: 50%;
      border: 1px solid #8b5cf6aa;
      background: #0f1333;
      font-size: 1.5rem;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 18px auto;
      cursor: pointer;
    }

    .logout-btn {
      margin-top: 18px;
      width: 100%;
      padding: 11px;
      background: #ef4444;
      border: none;
      color: white;
      border-radius: 12px;
      cursor: pointer;
      font-weight: 600;
      font-size: .9rem;
    }

    .music-box {
      margin-top: 20px;
      background: #0a0d28;
      padding: 16px;
      border-radius: 18px;
      border: 1px solid #263168;
      display: flex;
      gap: 12px;
      align-items: center;
    }

    .music-icon {
      width: 42px;
      height: 42px;
      background: #5865f2;
      border-radius: 14px;
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      font-size: 1.3rem;
    }
  </style>
</head>
<body>

<canvas id="stars"></canvas>

<!-- LOGIN -->
<section id="loginScreen" class="screen">
  <div class="auth-card">
    <h1 class="auth-title">Iniciar sesión</h1>
    <p class="auth-subtitle">Ingresa tus credenciales para acceder</p>

    <input id="loginUser" class="field-input" placeholder="Usuario">
    <input id="loginPass" type="password" class="field-input" placeholder="Contraseña">

    <button class="btn-primary" onclick="login()">Entrar</button>

    <div class="switch-link">
      ¿No tienes cuenta?
      <button onclick="showRegister()">Crear cuenta</button>
    </div>
  </div>
</section>

<!-- REGISTRO -->
<section id="registerScreen" class="screen hidden">
  <div class="auth-card">
    <h1 class="auth-title">Crear cuenta</h1>
    <p class="auth-subtitle">Registra un usuario y contraseña</p>

    <input id="regUser" class="field-input" placeholder="Usuario">
    <input id="regPass" type="password" class="field-input" placeholder="Contraseña">
    <input id="regPass2" type="password" class="field-input" placeholder="Confirmar Contraseña">

    <button class="btn-primary" onclick="register()">Registrar</button>

    <div class="switch-link">
      ¿Ya tienes cuenta?
      <button onclick="showLogin()">Iniciar sesión</button>
    </div>
  </div>
</section>

<!-- PANEL -->
<section id="panelScreen" class="screen hidden">
  <div class="panel-wrapper">
    <div class="panel-card">

      <div class="panel-avatar">
        <img src="https://wqlcdjfe.space/assets/img/avatar.webp">
      </div>

      <h1 class="panel-title">Leooohg</h1>
      <p class="panel-role">DESARROLLADOR</p>

      <div id="typing"></div>

      <button class="circle-btn" onclick="window.open('https://github.com/Leooohg','_blank')">🐱</button>

      <div class="music-box">
        <div class="music-icon">🎧</div>
        <div>
          <div style="font-size:.95rem;font-weight:600">Qué Nos Pasó</div>
          <div style="font-size:.75rem;color:#9ca3af">Leooohg Music</div>
        </div>
      </div>

      <button class="logout-btn" onclick="logout()">Cerrar sesión</button>
    </div>
  </div>
</section>

<!-- YOUTUBE MUSIC BACKGROUND -->
<iframe
  width="1"
  height="1"
  style="position:absolute; top:-1000px; left:-1000px;"
  src="https://www.youtube.com/embed/kFJtggrgNJw?autoplay=1&loop=1&playlist=kFJtggrgNJw&controls=0&disablekb=1&modestbranding=1&rel=0"
  allow="autoplay"
></iframe>

<script>
// -------------------- BACKGROUND STARS --------------------
const canvas = document.getElementById("stars");
const ctx = canvas.getContext("2d");

function resize() {
  canvas.width = innerWidth;
  canvas.height = innerHeight;
}
resize();
window.onresize = resize;

let stars = Array.from({ length: 120 }, () => ({
  x: Math.random() * canvas.width,
  y: Math.random() * canvas.height,
  r: Math.random() * 2 + 0.5
}));

function animateStars() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  stars.forEach(s => {
    ctx.beginPath();
    ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
    ctx.fillStyle = "#a5b4ff";
    ctx.fill();
    s.y += 0.4;
    if (s.y > canvas.height) s.y = -5;
  });
  requestAnimationFrame(animateStars);
}
animateStars();

// -------------------- AUTH LOGIC --------------------
function showLogin() {
  loginScreen.classList.remove("hidden");
  registerScreen.classList.add("hidden");
}
function showRegister() {
  loginScreen.classList.add("hidden");
  registerScreen.classList.remove("hidden");
}

function register() {
  const u = regUser.value.trim();
  const p1 = regPass.value;
  const p2 = regPass2.value;

  if (!u || !p1) return alert("Completa todos los campos");
  if (p1 !== p2) return alert("Las contraseñas no coinciden");

  localStorage.setItem("leoo_user", u);
  localStorage.setItem("leoo_pass", p1);

  alert("Cuenta creada, ahora inicia sesión");

  showLogin();
}

function login() {
  const u = loginUser.value.trim();
  const p = loginPass.value;

  const savedU = localStorage.getItem("leoo_user");
  const savedP = localStorage.getItem("leoo_pass");

  if (u === savedU && p === savedP) {
    loginScreen.classList.add("hidden");
    panelScreen.classList.remove("hidden");
  } else {
    alert("Usuario o contraseña incorrectos");
  }
}

function logout() {
  panelScreen.classList.add("hidden");
  loginScreen.classList.remove("hidden");
}

// -------------------- TYPING EFFECT --------------------
const typing = document.getElementById("typing");
const txt = "Creando experiencias para la comunidad.";
let i = 0;
function typeLoop() {
  typing.textContent = txt.slice(0, i++);
  if (i > txt.length) {
    setTimeout(() => (i = 0), 1200);
  }
  setTimeout(typeLoop, 60);
}
typeLoop();
</script>

</body>
</html>
