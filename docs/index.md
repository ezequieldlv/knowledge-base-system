---
title: Home
hide:
  - navigation
  - toc
---

<style>
  /* === HOME === */
  
  :root {
    --accent: #d8b4fe;
    --accent-glow: rgba(216, 180, 254, 0.15);
    --bg-page: #050505;
    --card-bg: #161616;
    --border: #333;
    --success: #00E676;
    --text-title: #e0e0e0;
    --md-header-height: 80px; 
  }

  /* 1. NAVBAR */
  .md-header, .md-tabs { 
    background-color: #000000 !important; 
    border-bottom: 1px solid #222; 
    height: var(--md-header-height) !important;
  }
  .md-header__inner { height: 100% !important; align-items: center; }
  .md-header__title { font-weight: 900; letter-spacing: 1px; font-size: 1.2rem; }

  /* 2. LIMPIEZA INTERFAZ */
  .md-typeset h1, .md-content__button { display: none !important; }
  .md-grid { max-width: 1400px !important; margin-top: 0 !important; padding-top: 0 !important; }
  .md-footer, footer { display: none !important; height: 0 !important; overflow: hidden !important; }
  .md-main__inner { padding-bottom: 0 !important; }

  /* 3. FONDO */
  body {
    background-color: var(--bg-page) !important;
    background-image: radial-gradient(circle at 50% 0%, #1a0a2a, #050505 60%) !important;
    background-attachment: fixed !important;
  }

  /* 4. LAYOUT */
  .md-main__inner {
    display: flex; align-items: center; justify-content: center;
    min-height: 85vh; 
  }
  .md-content { width: 100%; }

  .dashboard-grid {
    display: grid;
    grid-template-columns: 240px 1fr 240px;
    gap: 40px;
    align-items: start;
  }

  /* 5. TÍTULOS */
  .dash-title {
    font-family: 'Segoe UI', sans-serif; font-size: 0.85rem; font-weight: 700;
    color: var(--text-title); text-transform: uppercase; letter-spacing: 1.5px;
    margin-bottom: 20px; border-left: 4px solid var(--accent); padding-left: 15px;
    background: linear-gradient(90deg, #1a1a1a, transparent);
    padding-top: 8px; padding-bottom: 8px;
    box-shadow: -5px 0 15px var(--accent-glow);
  }

  /* 6. BOTONES */
  .quick-btn {
    display: flex; align-items: center;
    background: var(--card-bg); border: 1px solid var(--border);
    padding: 16px 20px; border-radius: 6px; margin-bottom: 12px;
    color: #ccc; text-decoration: none !important;
    font-family: 'Segoe UI', sans-serif; font-size: 0.95rem; font-weight: 600;   
    transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
  }
  .quick-btn:hover {
    border-color: var(--accent); color: #fff;
    background: linear-gradient(90deg, rgba(216, 180, 254, 0.1), transparent);
    transform: translateX(5px); box-shadow: 0 4px 20px rgba(0,0,0,0.8);
  }

  /* ALINEACIÓN DE ICONOS */
  .btn-icon, .btn-img {
    width: 32px; height: 32px; 
    margin-right: 15px; 
    display: flex; align-items: center; justify-content: center; 
    flex-shrink: 0;
  }
  .btn-icon { font-size: 1.4rem; opacity: 0.9; transition: 0.2s; }
  .quick-btn:hover .btn-icon { opacity: 1; transform: scale(1.1); filter: drop-shadow(0 0 5px var(--accent)); }

  /* IMÁGENES DENTRO DE BOTONES */
  .btn-img {
    object-fit: contain; 
    border-radius: 4px; 
    filter: drop-shadow(0 0 2px rgba(255, 255, 255, 0.2)); 
    transition: 0.2s;
  }
  .quick-btn:hover .btn-img {
    transform: scale(1.1);
    filter: drop-shadow(0 0 5px var(--accent));
  }

  /* 7. CONSOLA CENTRAL */
  .terminal-card {
    background: #0a0a0a; border: 1px solid var(--border);
    border-radius: 8px; overflow: hidden;
    box-shadow: 0 20px 60px rgba(216, 180, 254, 0.05); position: relative;
  }
  .terminal-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
    box-shadow: 0 0 15px var(--accent);
  }

  .terminal-header {
    background: #0f0f0f; padding: 15px 25px;
    display: flex; justify-content: space-between; align-items: center;
    border-bottom: 1px solid #222;
  }
  .term-title { 
    font-family: 'Segoe UI', sans-serif; font-weight: 700; color: #fff; font-size: 0.9rem; letter-spacing: 1px;
    display: flex; align-items: center;
  }
  .term-title::before { content: '>>'; color: var(--accent); margin-right: 10px; font-weight: 900; }

  .status-badge {
    color: var(--success); font-size: 0.7rem; font-weight: 800;
    display: flex; align-items: center; letter-spacing: 1px;
    border: 1px solid rgba(0, 230, 118, 0.3); padding: 4px 12px; border-radius: 20px;
    background: rgba(0, 230, 118, 0.05);
    box-shadow: 0 0 10px rgba(0, 230, 118, 0.1);
  }
  .status-badge::before {
    content: ''; width: 8px; height: 8px; background: var(--success);
    border-radius: 50%; margin-right: 8px;
    box-shadow: 0 0 8px var(--success); animation: pulse 2s infinite;
  }
  @keyframes pulse { 0% { opacity: 1; transform: scale(1); } 50% { opacity: 0.5; transform: scale(0.9); } 100% { opacity: 1; transform: scale(1); } }

  .terminal-body { padding: 40px; background: #050505; }
  
  .code-block { 
    font-family: 'Consolas', monospace; font-size: 1rem; color: #bbb; line-height: 1.8; 
  }
  .k { color: #d8b4fe; font-weight: bold; }
  .s { color: #a5d6ff; }
  .c { color: #555; font-style: italic; }
  .n { color: #FFD600; }

  .terminal-footer {
    background: #0e0e0e; padding: 12px 25px; font-size: 0.8rem; color: #666;
    border-top: 1px solid #222; display: flex; align-items: center; justify-content: space-between;
  }
  
  @media (max-width: 900px) {
    .dashboard-grid { grid-template-columns: 1fr; gap: 30px; }
  }

  /* === NOTIFICACIÓN CUMPLEAÑOS === */
  .birthday-toast {
    position: fixed;
    top: 20px;
    right: 20px;
    background: rgba(20, 20, 20, 0.95);
    border: 1px solid #FFD700; 
    color: #fff;
    padding: 15px 25px;
    border-radius: 8px;
    z-index: 9999;
    display: flex;
    align-items: center;
    gap: 15px;
    box-shadow: 0 0 20px rgba(255, 215, 0, 0.2);
    transform: translateX(150%); /* Oculto a la derecha */
    transition: transform 0.5s cubic-bezier(0.68, -0.55, 0.27, 1.55);
    backdrop-filter: blur(5px);
  }
  
  .birthday-toast.show {
    transform: translateX(0);
  }

  .b-icon { font-size: 1.5rem; animation: bounce 1s infinite alternate; }
  
  @keyframes bounce { from { transform: translateY(0); } to { transform: translateY(-5px); } }
</style>

<div class="dashboard-grid">

  <div class="col-left">
    <div class="dash-title">EXPLORADOR</div>
    <div style="display: flex; flex-direction: column;">
      <a href="autogestion/" class="quick-btn" target="_blank"><span class="btn-icon">📊</span> Autogestión</a>
      <a href="speechs/" class="quick-btn" target="_blank"><span class="btn-icon">💬</span> Speechs</a>
      <a href="herramientas/" class="quick-btn" target="_blank"><span class="btn-icon">🧰</span> Herramientas</a>
      <a href="wiki-tecnica/" class="quick-btn" target="_blank"><span class="btn-icon">🛠️</span> Wiki Técnica</a>
      <a href="equipo/" class="quick-btn" target="_blank"><span class="btn-icon">👥</span> Equipo</a>
    </div>
  </div>

  <div class="col-center">
    <div class="terminal-card">
      <div class="terminal-header">
        <span class="term-title">Monitor de Servicio</span>
        <span class="status-badge">ONLINE</span>
      </div>
      <div class="terminal-body">
        <div class="code-block">
          <span class="c">// Métricas Operativas - Tiempo Real</span><br><br>
          <span class="k">const</span> <span style="color:#fff">Performance</span> = {<br>
           &nbsp;&nbsp;CIERRE: <span style="color: #FFD600; font-weight: 900;">"77.4%"</span>, <span class="c">// ⚠️ Objetivo Crítico</span><br>
           &nbsp;&nbsp;NPS: <span class="s">"28%"</span>, <span class="c">// Net Promoter Score</span><br>
           &nbsp;&nbsp;FCR: <span class="s">"76.3%"</span>, <span class="c">// First Call Resolution</span><br>
           &nbsp;&nbsp;REL: <span class="s">"80.7%"</span>, <span class="c">// Resolución en Línea</span><br>
           &nbsp;&nbsp;GXH: <span class="s">"4.46"</span> <span class="c">// Gestión x Hora</span><br>
          };<br><br>
          <span style="color:#00E676">console</span>.log(<span class="s">"Objetivos en curso... 🚀"</span>);
        </div>
      </div>
      <div class="terminal-footer" style="display: flex; justify-content: space-between; align-items: center;">
          <div>
            <span style="color: #FFD600; font-weight: bold; margin-right: 5px;">⭐ Tip:</span> 
            <span style="opacity: 0.8;">Presiona 'S' para buscar</span>
          </div>
          <div style="font-family: 'Consolas', monospace; font-size: 0.75rem; opacity: 0.4;">
            Built by <strong style="color: #d8b4fe; font-weight: bold;">Ezequiel De la Vega</strong>
          </div>
      </div>
    </div>
  </div>

  <div class="col-right">
    <div class="dash-title">ACCESOS RÁPIDOS</div>
    <div style="display: flex; flex-direction: column;">
        <a href="https://pulsojwt.netlify.app/" target="_blank" class="quick-btn">
          <img src="assets/iconos/konecta-logo.jpg" class="btn-img" alt="Logo"> 
          Pulso
        </a>    
        <a href="https://docs.google.com/spreadsheets/d/1UIKnxG_YB-HawfutwRdDtUaoKgretH37mmWQjvHsJ78/edit?gid=1544040398#gid=1544040398" target="_blank" class="quick-btn"><span class="btn-icon">📊</span> Métricas</a>
        <a href="https://drive.google.com/file/d/1x0ZsDrLCncWBLngLSdpLuAqUrOAZBTGp/view" target="_blank" class="quick-btn"><span class="btn-icon">📢</span> Masivos eMemo</a>
      </div>
  </div>

</div>

<script src="../assets/db_equipo.js"></script>

<script>
  document.addEventListener("DOMContentLoaded", () => {
    
    // 1. Obtener fecha de hoy
    const hoy = new Date();
    const dia = String(hoy.getDate()).padStart(2, '0');
    const mes = String(hoy.getMonth() + 1).padStart(2, '0');
    const fechaActual = `${mes}-${dia}`; // Usamos formato MM-DD para coincidir con tu DB

    // 2. Buscar coincidencias en la Base de Datos Externa
    if(typeof EQUIPO_DB !== 'undefined') {
        const cumpleañeros = EQUIPO_DB.filter(p => p.cumple === fechaActual);

        // Si hay alguien, lanzamos notificación (toma el primero si hay varios)
        if (cumpleañeros.length > 0) {
            mostrarNotificacion(cumpleañeros[0].nombre);
        }
    }

    function mostrarNotificacion(nombre) {
      const toast = document.createElement('div');
      toast.className = 'birthday-toast';
      toast.innerHTML = `
        <span class="b-icon">🎂</span>
        <div>
          <div style="font-size: 0.8rem; color: #FFD700; text-transform: uppercase; font-weight:bold;">Feliz cumpleaños</div>
          <div style="font-size: 1rem;">¡<strong>${nombre}</strong>! 🎉</div>
        </div>
      `;

      document.body.appendChild(toast);
      setTimeout(() => toast.classList.add('show'), 100);
      setTimeout(() => {
        toast.classList.remove('show');
        setTimeout(() => toast.remove(), 600);
      }, 6000);
    }
  });

  console.log(
    "%c System Core %c Built by Ezequiel De la Vega ",
    "background: #d8b4fe; color: #000; font-weight: bold; padding: 4px; border-radius: 3px 0 0 3px;",
    "background: #222; color: #fff; padding: 4px; border-radius: 0 3px 3px 0;"
  );
  console.log("Legacy Code: Do not touch if it works. 🚀");
</script>