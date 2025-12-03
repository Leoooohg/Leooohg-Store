<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Leooohg | Panel & Login</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap");

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: "Poppins", sans-serif;
    }

    :root {
      --bg-main: #050816;
      --card-bg: #121632;
      --purple: #8b5cf6;
      --blue: #4f46e5;
      --discord: #5865f2;
      --white-soft: #e5e7eb;
    }

    body {
      min-height: 100vh;
      background: radial-gradient(circle at top, #141b3f 0, #040716 45%, #02010a 100%);
      color: var(--white-soft);
      overflow: hidden;
    }

    canvas#stars {
      position: fixed;
      inset: 0;
      z-index: -1;
    }

    .screen {
      position: fixed;
      inset: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
      transition: opacity .3s ease, transform .3s ease;
    }

    .screen.hidden {
      opacity: 0;
      pointer-events: none;
      transform: translateY(10px);
    }

    /* PANEL */
    .panel-wrapper {
      width: 100%;
      max-width: 420px;
    }

    .panel-card {
      background: radial-gradient(circle at top left, #1b2149, #0a0d22);
      border-radius: 26px;
      padding: 32px 26px;
      border: 1px solid rgba(255,255,255,.06);
      box-shadow: 0 24px 60px rgba(5,7,31,.9);
      position: relative;
      overflow: hidden;
    }

    .panel-top-discord {
      position: absolute;
      top: 20px;
      left: 20px;
      width: 48px;
      height: 48px;
      border-radius: 50%;
      background: rgba(15,23,42,.95);
      border: 1px solid #5865f2aa;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 12px 32px #5865f299;
    }

    .panel-avatar-wrap {
      display: flex;
      justify-content: center;
      margin-top: 16px;
    }

    .panel-avatar-ring {
      width: 130px;
      height: 130px;
      border-radius: 50%;
      padding: 4px;
      background: conic-gradient(#a855f7, #3b82f6, #22c55e, #f97316, #a855f7);
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 18px 50px rgba(88,101,242,.8);
    }

    .panel-avatar img {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      object-fit: cover;
    }

    .panel-logo-w {
      text-align: center;
      margin-top: 16px;
      font-size: 2.3rem;
      font-weight: 700;
      background: linear-gradient(135deg, #22d3ee, #a855f7);
      -webkit-background-clip: text;
      color: transparent;
      letter-spacing: .3rem;
    }

    .panel-role {
      text-align: center;
      margin-top: 12px;
      font-size: .9rem;
      color: #9ca3af;
      letter-spacing: .5rem;
    }

    #typing {
      text-align: center;
      margin-top: 6px;
      font-size: .92rem;
      color: #c7d2fe;
      white-space: nowrap;
      overflow: hidden;
      border-right: 2px solid #c7d2fe;
      animation: caret .8s step-end infinite;
    }

    @keyframes caret {
      50% { border-color: transparent; }
    }

    .panel-center-actions {
      margin-top: 22px;
      display: flex;
      justify-content: center;
    }

    .circle-btn {
      width: 54px;
      height: 54px;
      border-radius: 50%;
      border: 1px solid #a855f7bb;
      background: rgba(15,23,42,.85);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.6rem;
      cursor: pointer;
    }

    .panel-music {
      margin-top: 26px;
      background: #0d102c;
      border-radius: 18px;
      padding: 16px;
      display: flex;
      gap: 12px;
      align-items: center;
      border: 1px solid #2b335f;
    }

    .music-icon {
      width: 42px;
      height: 42px;
      background: #5865f2;
      border-radius: 14px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 1.4rem;
      color: white;
    }

    .music-title {
      font-size: .95rem;
      font-weight: 600;
    }

    .music-artist {
      font-size: .75rem;
      color: #9ca3af;
    }

    .panel-cta {
      margin-top: 20px;
      display: flex;
      justify-content: center;
    }

    .panel-cta button {
      padding: 11px 24px;
      border-radius: 999px;
      background: linear-gradient(135deg, #6366f1, #8b5cf6);
      border: none;
      color: white;
      font-weight: 600;
      cursor: pointer;
      font-size: .95rem;
    }

    /* LOGIN */
    .auth-wrapper {
      width: 100%;
      max-width: 420px;
    }

    .auth-card {
      background: #121633ee;
      border-radius: 24px;
      padding: 32px 26px;
      border: 1px solid rgba(255,255,255,.07);
      box-shadow: 0 24px 60px rgba(5,7,31,.9);
      position: relative;
    }

    .auth-avatar-ring {
      width: 90px;
      height: 90px;
      padding: 3px;
      border-radius: 50%;
      background: conic-gradient(#a855f7,#6366f1,#22c55e,#fb923c,#a855f7);
      margin: 0 auto;
    }

    .auth-avatar-ring img {
      width: 100%;
      height: 100%;
      border-radius: 50%;
      object-fit: cover;
    }

    .auth-title {
      margin-top: 18px;
      text-align: center;
      font-size: 1.7rem;
      font-weight: 700;
      color: #c7d2fe;
    }

    .auth-subtitle {
      text-align: center;
      margin-top: 4px;
      font-size: .9rem;
      color: #9ca3af;
    }

    .auth-tabs {
      margin-top: 16px;
      display: flex;
      gap: 16px;
      justify-content: center;
    }

    .auth-tabs span {
      cursor: pointer;
      font-size: .9rem;
      padding-bottom: 2px;
      border-bottom: 2px solid transparent;
    }

    .auth-tabs .active {
      border-bottom-color: #a855f7;
      color: #c7d2fe;
      font-weight: 600;
    }

    .btn-discord {
      width: 100%;
      margin-top: 18px;
      padding: 11px;
      border-radius: 999px;
      background: var(--discord);
      border: none;
      color: white;
      font-size: .95rem;
      font-weight: 600;
      cursor: pointer;
    }

    .auth-separator {
      margin: 20px 0;
      text-align: center;
      color: #6b7280;
      font-size: .8rem;
    }

    .field-input {
      width: 100%;
      padding: 9px 11px;
      border-radius: 12px;
      border: 1px solid #272f5b;
      background: #0f1330;
      color: white;
      margin-bottom: 14px;
    }

    .btn-primary {
      width: 100%;
      padding: 12px;
      border-radius: 999px;
      background: linear-gradient(135deg,#6366f1,#a855f7);
      border: none;
      font-size: .95rem;
      font-weight: 600;
      color: white;
      cursor: pointer;
    }

    .auth-bottom-text {
      text-align: center;
      margin-top: 12px;
      font-size: .8rem;
      color: #9ca3af;
    }

    .auth-bottom-text button {
      background: none;
      border: none;
      color: #818cf8;
      cursor: pointer;
      text-decoration: underline;
    }

    .auth-back {
      margin-top: 18px;
      text-align: center;
    }

    .auth-back button {
      background: none;
      border: none;
      color: #9ca3af;
      cursor: pointer;
      text-decoration: underline;
      font-size: .78rem;
    }
  </style>
</head>
<body>

<canvas id="stars"></canvas>

<!-- PANEL -->
<section id="panel" class="screen">
  <div class="panel-wrapper">
    <div class="panel-card">
      <div class="panel-top-discord">💬</div>

      <div class="panel-avatar-wrap">
        <div class="panel-avatar-ring">
          <div class="panel-avatar">
            <img src="https://wqlcdjfe.space/assets/img/avatar.webp">
          </div>
        </div>
      </div>

      <div class="panel-logo-w">L</div>
      <div class="panel-role">DESARROLLADOR</div>
      <div id="typing"></div>

      <div class="panel-center-actions">
        <button class="circle-btn" onclick="window.open('https://github.com/Leooohg','_blank')">🐱</button>
      </div>

      <div class="panel-music">
        <div class="music-icon">🎧</div>
        <div>
          <div class="music-title">Qué Nos Pasó</div>
          <div class="music-artist">Leooohg Music</div>
        </div>
      </div>

      <div class="panel-cta">
        <button onclick="openAuth()">Acceder</button>
      </div>
    </div>
  </div>
</section>

<!-- LOGIN -->
<section id="auth" class="screen hidden">
  <div class="auth-wrapper">
    <div class="auth-card">

      <div class="auth-avatar-ring">
        <img src="https://wqlcdjfe.space/assets/img/avatar.webp">
      </div>

      <h1 id="authTitle" class="auth-title">Bienvenido</h1>
      <p id="authSubtitle" class="auth-subtitle">Ingresa tus credenciales para continuar</p>

      <div class="auth-tabs">
        <span id="tabLogin" class="active" onclick="switchAuth('login')">Iniciar sesión</span>
        <span id="tabRegister" onclick="switchAuth('register')">Crear cuenta</span>
      </div>

      <button class="btn-discord" id="discordBtn">Continuar con Discord</button>

      <div class="auth-separator">o</div>

      <form id="formLogin">
        <input class="field-input" placeholder="Usuario">
        <input class="field-input" type="password" placeholder="Contraseña">
        <button class="btn-primary">Ingresar</button>

        <div class="auth-bottom-text">
          ¿No tienes cuenta?
          <button type="button" onclick="switchAuth('register')">Crear cuenta</button>
        </div>
      </form>

      <form id="formRegister" style="display:none">
        <input class="field-input" placeholder="Usuario">
        <input class="field-input" type="password" placeholder="Contraseña">
        <input class="field-input" type="password" placeholder="Confirmar Contraseña">
        <button class="btn-primary">Crear Cuenta</button>

        <div class="auth-bottom-text">
          ¿Ya tienes cuenta?
          <button type="button" onclick="switchAuth('login')">Iniciar sesión</button>
        </div>
      </form>

      <div class="auth-back">
        <button onclick="closeAuth()">Volver al panel</button>
      </div>

    </div>
  </div>
</section>

<!-- YOUTUBE AUDIO OCULTO (NO TOCAR) -->
<iframe
  id="ytplayer"
  width="1"
  height="1"
  frameborder="0"
  allow="autoplay"
  style="position:absolute; top:-1000px; left:-1000px;"
  src="https://www.youtube.com/embed/kFJtggrgNJw?autoplay=1&loop=1&playlist=kFJtggrgNJw&controls=0&disablekb=1&modestbranding=1&rel=0"
></iframe>

<script>
  // Stars Background
  const canvas = document.getElementById("stars");
  const ctx = canvas.getContext("2d");
  function resize() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  }
  window.onresize = resize;
  resize();
  const stars = Array.from({ length: 120 }, () => ({
    x: Math.random() * canvas.width,
    y: Math.random() * canvas.height,
    r: Math.random() * 2,
  }));
  function animateStars() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    for (let s of stars) {
      ctx.beginPath();
      ctx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
      ctx.fillStyle = "#a5b4ff";
      ctx.fill();
      s.y += 0.3;
      if (s.y > canvas.height) s.y = -5;
    }
    requestAnimationFrame(animateStars);
  }
  animateStars();

  // Panel -> Login
  const panel = document.getElementById("panel");
  const auth = document.getElementById("auth");

  function openAuth() {
    panel.classList.add("hidden");
    auth.classList.remove("hidden");
  }
  function closeAuth() {
    auth.classList.add("hidden");
    panel.classList.remove("hidden");
  }

  // Login / Registro Switch
  const formLogin = document.getElementById("formLogin");
  const formRegister = document.getElementById("formRegister");
  const tabLogin = document.getElementById("tabLogin");
  const tabRegister = document.getElementById("tabRegister");
  const authTitle = document.getElementById("authTitle");
  const authSubtitle = document.getElementById("authSubtitle");
  const discordBtn = document.getElementById("discordBtn");

  function switchAuth(mode) {
    if (mode === "login") {
      formLogin.style.display = "block";
      formRegister.style.display = "none";
      tabLogin.classList.add("active");
      tabRegister.classList.remove("active");
      authTitle.textContent = "Bienvenido";
      authSubtitle.textContent = "Ingresa tus credenciales para continuar";
      discordBtn.textContent = "Continuar con Discord";
    } else {
      formLogin.style.display = "none";
      formRegister.style.display = "block";
      tabLogin.classList.remove("active");
      tabRegister.classList.add("active");
      authTitle.textContent = "Crear Cuenta";
      authSubtitle.textContent = "Completa los datos para registrarte";
      discordBtn.textContent = "Registrarse con Discord";
    }
  }

  // Typing Effect
  const typing = document.getElementById("typing");
  const text = "Creando experiencias para la comunidad.";
  let idx = 0;
  function typeLoop() {
    typing.textContent = text.slice(0, idx++);
    if (idx > text.length) {
      setTimeout(() => (idx = 0), 1200);
    }
    setTimeout(typeLoop, 60);
  }
  typeLoop();
</script>

</body>
</html>
