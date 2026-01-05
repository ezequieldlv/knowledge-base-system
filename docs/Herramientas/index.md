---
title: Herramientas
edit_uri: ""
hide:
  - navigation
  - toc
---

<style>
  /* === HERRAMIENTAS === */
  
  :root {
    --bg-page: #050505;
    --card-bg: #161616;
    --accent: #d8b4fe;
    --accent-glow: rgba(216, 180, 254, 0.15);
    --border: #333;
    --success: #00E676;
    --text-primary: #e0e0e0;
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

  /* 2. FONDO */
  body {
    background-color: var(--bg-page) !important;
    background-image: radial-gradient(circle at 50% 0%, #1a0a2a, #050505 50%) !important;
    background-attachment: fixed !important;
  }
  .md-container, .md-main__inner { background: transparent !important; }

  /* 3. TÍTULOS */
  h1 {
    font-family: 'Segoe UI', Roboto, sans-serif; font-weight: 900; font-size: 2.8rem; letter-spacing: -1px; 
    margin-bottom: 40px !important; padding-bottom: 20px; border-bottom: 4px solid #1a1a1a; text-transform: uppercase; 
    display: flex; align-items: center;
    background: linear-gradient(to right, #fff, #999);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
  }
  h1::before { 
    content: '🧰'; 
    margin-right: 20px; 
    font-size: 2.4rem; 
    -webkit-text-fill-color: initial; 
    transform: translateY(-5px); 
  }

  h2 {
    font-family: 'Segoe UI', sans-serif; font-size: 1.2rem; font-weight: 800;
    color: #fff; text-transform: uppercase; letter-spacing: 0.5px;
    margin-top: 60px !important; margin-bottom: 25px;
    border-left: 6px solid var(--accent); background: linear-gradient(90deg, #1a1a1a, transparent);
    padding: 12px 20px; border-radius: 0 4px 4px 0;
    box-shadow: -5px 0 20px var(--accent-glow); display: flex; align-items: center;
  }

  /* 4. GRID & CARDS */
  .tools-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 20px;
  }

  .tool-card {
    display: flex; align-items: center;
    background-color: var(--card-bg); border: 1px solid var(--border);
    border-radius: 6px; padding: 20px 25px; 
    text-decoration: none !important; transition: all 0.2s ease; position: relative; overflow: hidden;
    min-height: 90px; height: auto; cursor: pointer;
  }

  .tool-card:hover {
    border-color: var(--accent);
    background: linear-gradient(90deg, rgba(216, 180, 254, 0.08), transparent);
    transform: translateY(-3px); box-shadow: 0 5px 25px rgba(0,0,0,0.7);
  }
  
  .tool-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: var(--accent); opacity: 0; transition: 0.2s;
  }
  .tool-card:hover::before { opacity: 1; box-shadow: 0 0 10px var(--accent); }

  /* CONFIGURACIÓN DE ICONOS E IMÁGENES  */
  .tool-icon {
    width: 55px; 
    display: flex; justify-content: center; align-items: center;
    margin-right: 20px; flex-shrink: 0;
    font-size: 2.2rem; 
    opacity: 0.9; transition: 0.2s;
  }
  
  /* CORRECCIÓN DE TAMAÑO DE IMAGEN */
  .tool-icon img {
    width: 45px; height: 45px;
    object-fit: contain;
    filter: drop-shadow(0 0 2px rgba(255,255,255,0.2));
  }
  
  .tool-card:hover .tool-icon { transform: scale(1.1); opacity: 1; }

  .tool-info { display: flex; flex-direction: column; justify-content: center; flex: 1; min-width: 0; }

  .tool-header { display: flex; justify-content: space-between; align-items: flex-start; width: 100%; }

  .tool-title {
    font-family: 'Segoe UI', sans-serif; font-weight: 700; font-size: 1.1rem; color: #fff;
    white-space: normal; line-height: 1.3; margin-bottom: 4px; max-width: 90%;
  }
  
  .tool-desc {
    font-family: 'Consolas', monospace; font-size: 0.85rem; font-weight: 500; color: #888; 
    white-space: normal; line-height: 1.4;
  }

  .status-dot {
    width: 8px; height: 8px; background-color: #333; border-radius: 50%;
    transition: 0.3s; border: 1px solid #444; flex-shrink: 0; margin-top: 6px; 
  }
  .tool-card:hover .status-dot {
    background-color: var(--success); border-color: var(--success); box-shadow: 0 0 8px var(--success);
  } 
  
  /*  EXTERMINADOR DE FOOTER */
  .md-footer, .md-footer__inner, .md-copyright, footer, .md-footer-meta, .md-footer-nav { 
    display: none !important; height: 0 !important; overflow: hidden !important; 
    padding: 0 !important; margin: 0 !important; border: none !important;
  }
  .md-content__button, .md-icon--edit, a[href*="edit"] { display: none !important; }

  /* === TOAST NOTIFICATION === */
  #clipboard-toast {
    visibility: hidden; min-width: 250px; margin-left: -125px;
    background-color: #333; color: #fff; text-align: center;
    border-radius: 4px; padding: 16px; position: fixed; z-index: 100;
    left: 50%; bottom: 30px; font-size: 17px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.5); border: 1px solid var(--accent);
  }
  #clipboard-toast.show { visibility: visible; animation: fadein 0.5s, fadeout 0.5s 2.5s; }
  
  @keyframes fadein { from {bottom: 0; opacity: 0;} to {bottom: 30px; opacity: 1;} }
  @keyframes fadeout { from {bottom: 30px; opacity: 1;} to {bottom: 0; opacity: 0;} }

</style>

# Herramientas

<div id="clipboard-toast">Link copiado al portapapeles ✅</div>

<h2>📚 Recursos y Ayuda</h2>

<div class="tools-grid">

  <a href="https://basedeconocimientos.custhelp.com/app/home" target="_blank" class="tool-card">
    <div class="tool-icon">📖</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">BC</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Base de Conocimientos</span>
    </div>
  </a>

  <a href="https://mail.google.com/mail/u/0/#inbox" target="_blank" class="tool-card">
    <div class="tool-icon">
       <img src="../assets/iconos/google-chat-icon.png" alt="Chat" onerror="this.style.display='none';this.parentNode.innerHTML='💬'">
    </div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">Chat / Mail</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Comunicación Interna</span>
    </div>
  </a>

  <a href="https://basedeconocimientos.custhelp.com/euf/assets/CV/Documentos/CBS/Planillas%20CBS/planillas_cbs.html" target="_blank" class="tool-card">
    <div class="tool-icon">📋</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">Planillas CBS</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Plantillas Escalamiento</span>
    </div>
  </a>

</div>

<h2>💻 Sistemas de Gestión</h2>

<div class="tools-grid">

  <a href="https://human-agent-tecob2c.ysocial.net/agent/#/" target="_blank" class="tool-card">
    <div class="tool-icon">⚡</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">Yoizen</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Plataforma de Atención</span>
    </div>
  </a>

  <a href="https://telecomcrm.lightning.force.com/lightning/page/home" target="_blank" class="tool-card">
    <div class="tool-icon">☁️</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">FAN</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">CRM</span>
    </div>
  </a>

  <a href="https://frontocs.personal.corp/#/signin" class="tool-card copy-link">
    <div class="tool-icon">📲</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">SNAP</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Verificar GB</span>
    </div>
  </a>

  <a href="https://itickets.telecom.com.ar/" target="_blank" class="tool-card">
    <div class="tool-icon">🎫</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">iTicket</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Gestión de Tickets</span>
    </div>
  </a>

  <a href="http://srvapfabricdes2:8080/portal-consulta-usuario-dbs/" class="tool-card copy-link">
    <div class="tool-icon">🆔</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">IDP</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Consulta Usuario DBS</span>
    </div>
  </a>

  <a href="https://ccip/" class="tool-card copy-link">
    <div class="tool-icon">💻</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">CCIP</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Gestión FTTH</span>
    </div>
  </a>

  <a href="https://human-agent-tecob2c.ysocial.net/Default.aspx" class="tool-card copy-link">
    <div class="tool-icon">🪄</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">Yoizen +</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Plataforma de lideres</span>
    </div>
  </a>

</div>

<h2>📡 Diagnóstico y Red</h2>

<div class="tools-grid">

  <a href="https://codiplus.telecom.com.ar/pddu/diagnostico" class="tool-card copy-link">
    <div class="tool-icon">🩺</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">CODI+</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Diagnóstico Unificado</span>
    </div>
  </a>

  <a href="https://codi.telecom.com.ar" class="tool-card copy-link">
    <div class="tool-icon">📟</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">Codi</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Asistencia Open</span>
    </div>
  </a>

  <a href="http://10.9.44.132/symphonica/v2_9/#/" target="_blank" class="tool-card">
    <div class="tool-icon">🎼</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">Symphonica</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Orquestador de Red</span>
    </div>
  </a>

  <a href="https://itracker.telecom.com.ar/" target="_blank" class="tool-card">
    <div class="tool-icon">📍</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">iTracker</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Seguimiento Técnico</span>
    </div>
  </a>

  <a href="https://solucionesdigitales.telecom.com.ar/apps/guia_migra_internet/" class="tool-card copy-link">
    <div class="tool-icon">🛠️</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">CATEC</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Guía Migración</span>
    </div>
  </a>

  <a href="https://macvendors.com/" target="_blank" class="tool-card">
    <div class="tool-icon">🔍</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">Mac Vendor</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Identificar Dispositivo</span>
    </div>
  </a>

</div>

<h2>📢 Reportes y Nodos</h2>

<div class="tools-grid">

  <a href="https://docs.google.com/forms/d/e/1FAIpQLSeTCksCOp7xjP0NUULzu3TSesRAP6pQgT0M8n_4zaMfX4LJ9Q/viewform" target="_blank" class="tool-card">
    <div class="tool-icon">📝</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">Reportar Nodo</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Carga de Incidente</span>
    </div>
  </a>

  <a href="https://tinyurl.com/nodos-reportados" target="_blank" class="tool-card">
    <div class="tool-icon">📊</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">Ver Nodos Reportados</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Visualizar Reportes</span>
    </div>
  </a>

  <a href="https://docs.google.com/forms/d/e/1FAIpQLSe4efFoodXKEA6k5tnlgwG0_VHhs2EwG5VOPkNt55MmwgkUXQ/viewform" target="_blank" class="tool-card">
    <div class="tool-icon">⚠️</div>
    <div class="tool-info">
      <div class="tool-header">
        <span class="tool-title">Reportar TLP/APEX</span>
        <div class="status-dot"></div>
      </div>
      <span class="tool-desc">Casos Especiales</span>
    </div>
  </a>

</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    const copyLinks = document.querySelectorAll('.copy-link');

    copyLinks.forEach(link => {
      link.addEventListener('click', function(e) {
        e.preventDefault();
        const url = this.href;
        navigator.clipboard.writeText(url).then(() => {
          showToast();
        }).catch(err => {
          console.error('Error al copiar: ', err);
        });
      });
    });

    function showToast() {
      const x = document.getElementById("clipboard-toast");
      x.className = "show";
      setTimeout(function(){ x.className = x.className.replace("show", ""); }, 3000);
    }
  });
</script>