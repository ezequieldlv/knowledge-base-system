---
title: Cumpleaños
hide:
  - navigation
  - toc
---

<style>
  /* === EQUIPO === */
  
  :root {
    --bg-page: #050505;
    --card-bg: #111;
    --accent: #d8b4fe;
    --border: #333;
    --gold: #FFD600; /* Color para el cumpleañero */
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

  /* CONFIG BASE */
  .md-header, .md-tabs { background-color: #000000 !important; border-bottom: 1px solid #222; height: var(--md-header-height) !important; }
  .md-header__inner { height: 100% !important; align-items: center; }
  .md-content__button, .md-icon--edit, a[href*="edit"] { display: none !important; }
  .md-footer, footer { display: none !important; }
  
  /* EXTERMINADOR DE LÁPIZ */
  summary.wiki-trigger::before, summary.speech-trigger::before { content: none !important; }

  body {
    background-color: var(--bg-page) !important;
    background-image: radial-gradient(circle at 50% 0%, #1a0a2a, #050505 50%) !important;
    background-attachment: fixed !important;
  }
  .md-container, .md-main__inner { background: transparent !important; }

  /* TÍTULO */
  h1 {
    font-family: 'Segoe UI', Roboto, sans-serif; font-weight: 900; font-size: 2.5rem;
    letter-spacing: -1px; margin-bottom: 40px !important; padding-bottom: 20px;
    border-bottom: 4px solid #1a1a1a; text-transform: uppercase;
    display: flex; align-items: center;
    background: linear-gradient(to right, #fff, #999);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
  }
  h1::before { content: '🎂'; margin-right: 20px; font-size: 2.2rem; -webkit-text-fill-color: initial; }

  /* GRID */
  .roster-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 20px;
  }

  /* TARJETA DE AGENTE */
  .agent-card {
    background: var(--card-bg); 
    border: 1px solid var(--border);
    border-top: 3px solid #333; 
    border-radius: 6px; padding: 20px;
    display: flex; align-items: center;
    transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
    position: relative; overflow: hidden;
  }

  /* Hover Normal */
  .agent-card:hover {
    border-color: var(--accent); 
    border-top-color: var(--accent);
    transform: translateY(-5px);
    background: #161616;
    box-shadow: 0 10px 30px rgba(0,0,0,0.5);
  }

  /* === MODO FIESTA (Se activa con JS si es el cumple) === */
  .is-birthday {
    border-color: var(--gold) !important;
    border-top-color: var(--gold) !important;
    background: linear-gradient(135deg, rgba(255, 214, 0, 0.05), #111) !important;
    box-shadow: 0 0 20px rgba(255, 214, 0, 0.2) !important;
    animation: pulse-gold 2s infinite;
  }
  
  /* Icono del cumpleañero */
  .is-birthday .agent-icon {
    border-color: var(--gold) !important;
    color: var(--gold) !important;
    box-shadow: 0 0 15px rgba(255, 214, 0, 0.3);
  }

  .is-birthday .agent-data { color: var(--gold) !important; }

  @keyframes pulse-gold {
    0% { box-shadow: 0 0 0 0 rgba(255, 214, 0, 0.4); }
    70% { box-shadow: 0 0 0 10px rgba(255, 214, 0, 0); }
    100% { box-shadow: 0 0 0 0 rgba(255, 214, 0, 0); }
  }

  /* AVATAR */
  .agent-icon {
    width: 55px; height: 55px; background: #1a1a1a; border-radius: 50%;
    display: flex; justify-content: center; align-items: center;
    font-size: 1.2rem; margin-right: 18px; border: 1px solid #333;
    color: #888; overflow: hidden; flex-shrink: 0;
    transition: 0.3s;
  }
  .agent-card:hover .agent-icon { border-color: var(--accent); color: #fff; }
  .agent-icon img { width: 100%; height: 100%; object-fit: cover; }

  /* DATOS */
  .agent-info { display: flex; flex-direction: column; justify-content: center; }
  
  .agent-name { 
    font-family: 'Segoe UI', sans-serif; font-weight: 700; color: #fff; font-size: 1.05rem; 
  }
  
  .agent-data { 
    font-family: 'Consolas', monospace; font-size: 0.85rem; color: #888; margin-top: 5px; 
    display: flex; align-items: center; font-weight: 500; transition: 0.3s;
  }
  .agent-card:hover .agent-data { color: var(--accent); }
  
  .agent-role {
    font-size: 0.7rem; color: #555; margin-top: 3px; text-transform: uppercase; letter-spacing: 1px; font-weight: 700;
  }
  
  .role-boss { color: #FFD600 !important; opacity: 0.8; } 

</style>

# Cumpleaños

<div class="roster-grid" id="grid-equipo"></div>

<script src="../assets/db_equipo.js"></script> 

<script>
  document.addEventListener("DOMContentLoaded", function() {
    const contenedor = document.getElementById('grid-equipo');
    
    // Obtener fecha de hoy
    const today = new Date();
    const mm = String(today.getMonth() + 1).padStart(2, '0');
    const dd = String(today.getDate()).padStart(2, '0');
    const todayString = `${mm}-${dd}`;

    // Generar tarjetas dinámicamente
    // Usamos la variable EQUIPO_DB que viene del archivo externo
    if(typeof EQUIPO_DB !== 'undefined') {
        
        EQUIPO_DB.forEach(persona => {
            const esCumple = persona.cumple === todayString;
            const claseJefe = persona.esJefe ? 'role-boss' : '';
            const textoFecha = esCumple ? '🎂 ¡ES HOY! 🎉' : `📅 ${persona.diaTexto}`;
            const claseCumple = esCumple ? 'is-birthday' : '';

            const contenidoAvatar = persona.foto 
              ? `<img src="${persona.foto}" alt="${persona.nombre}" style="width:100%; height:100%; object-fit:cover;">` 
              : `<span>${persona.id}</span>`;

            const htmlCard = `
              <div class="agent-card ${claseCumple}">
                <div class="agent-icon">${contenidoAvatar}</div>
                
                <div class="agent-info">
                  <span class="agent-name">${persona.nombre}</span>
                  <span class="agent-data">${textoFecha}</span>
                  <span class="agent-role ${claseJefe}">${persona.rol}</span>
                </div>
              </div>
            `;

            // Si es cumpleañero, lo ponemos al principio de la lista
            if (esCumple) {
                contenedor.insertAdjacentHTML('afterbegin', htmlCard);
            } else {
                contenedor.insertAdjacentHTML('beforeend', htmlCard);
            }
        });
    }
  });
</script>