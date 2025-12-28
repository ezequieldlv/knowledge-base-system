---
title: Autogestión
edit_uri: ""
hide:
  - navigation
  - toc
---

<style>
  /* === AUTOGESTIÓN: FINAL GOLD VERSION (320px) === */
  
  :root {
    --bg-page: #050505;
    --card-bg: #161616;
    --accent: #d8b4fe;
    --accent-glow: rgba(216, 180, 254, 0.15);
    --border: #333;
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
  
  /* 2. EXTERMINADOR DE FOOTER */
  .md-footer, .md-footer__inner, .md-copyright, footer, .md-footer-meta, .md-footer-nav { 
    display: none !important; height: 0 !important; overflow: hidden !important; 
    padding: 0 !important; margin: 0 !important; border: none !important;
  }
  .md-content__button, .md-icon--edit, a[href*="edit"] { display: none !important; }

  /* 3. FONDO */
  body {
    background-color: var(--bg-page) !important;
    background-image: radial-gradient(circle at 50% 0%, #1a0a2a, #050505 50%) !important;
    background-attachment: fixed !important;
  }
  .md-container, .md-main__inner { background: transparent !important; }

  /* 4. TÍTULOS */
  h1 {
    font-family: 'Segoe UI', Roboto, sans-serif; font-weight: 900; font-size: 2.8rem;
    letter-spacing: -1px; margin-bottom: 40px !important; padding-bottom: 20px;
    border-bottom: 4px solid #1a1a1a; text-transform: uppercase;
    display: flex; align-items: center;
    background: linear-gradient(to right, #fff, #999);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
  }
  h1::before { content: '📱'; margin-right: 20px; font-size: 2.4rem; -webkit-text-fill-color: initial; }

  h2 {
    font-family: 'Segoe UI', sans-serif; font-size: 1.2rem; font-weight: 800;
    color: #fff; text-transform: uppercase; letter-spacing: 0.5px;
    margin-top: 60px !important; margin-bottom: 25px;
    border-left: 6px solid var(--accent); background: linear-gradient(90deg, #1a1a1a, transparent);
    padding: 12px 20px; border-radius: 0 4px 4px 0;
    box-shadow: -5px 0 20px var(--accent-glow); display: flex; align-items: center;
  }

  /* 5. SPLIT CARD SYSTEM (HEIGHT 320px - EL PUNTO PERFECTO) */
  .split-card {
    display: flex;
    background: var(--card-bg);
    border: 1px solid var(--border);
    border-radius: 8px;
    margin-bottom: 30px;
    overflow: hidden;
    
    /* Aumento estratégico para que entren los textos largos */
    height: 320px; 
    
    box-shadow: 0 10px 30px rgba(0,0,0,0.5);
    transition: transform 0.2s, border-color 0.2s;
  }
  .split-card:hover { border-color: #555; transform: translateY(-2px); }

  /* IZQUIERDA: VISUAL */
  .sc-visual {
    flex: 0 0 35%;
    background: #050505; 
    position: relative;
    border-right: 1px solid #333;
    display: flex; justify-content: center; align-items: center;     
    padding: 15px; 
    overflow: hidden;
  }
  
  .sc-visual img {
    max-width: 100%;
    max-height: 100%; 
    width: auto; height: auto;
    object-fit: contain; 
    border-radius: 6px; 
    box-shadow: 0 5px 15px rgba(0,0,0,0.5); 
    transition: transform 0.3s ease;
  }
  .sc-visual:hover img { transform: scale(1.05); }

  /* Botón Descargar */
  .dl-btn {
    position: absolute; bottom: 10px; right: 10px;
    background: rgba(0,0,0,0.8); backdrop-filter: blur(2px); color: #fff;
    padding: 6px 12px; border-radius: 4px; font-size: 0.75rem; font-weight: 600;
    text-decoration: none !important; border: 1px solid #333;
    opacity: 0; transition: 0.2s; display: flex; align-items: center; gap: 5px; z-index: 2;
  }
  .sc-visual:hover .dl-btn { opacity: 1; }
  .dl-btn:hover { background: var(--accent); color: #000; border-color: var(--accent); }

  /* CENTRO: DIVIDER */
  .sc-divider {
    width: 4px;
    background: linear-gradient(to bottom, var(--card-bg), var(--accent), var(--card-bg));
    box-shadow: 0 0 10px var(--accent-glow); opacity: 0.7;
  }

  /* DERECHA: CONTENIDO OPTIMIZADO */
  .sc-content {
    flex: 1; 
    padding: 15px 20px; /* Padding ajustado */
    display: flex; flex-direction: column; 
    min-width: 0;
    overflow-y: auto;
  }

  /* Scrollbar Fino y Sutil */
  .sc-content::-webkit-scrollbar { width: 4px; }
  .sc-content::-webkit-scrollbar-track { background: #111; }
  .sc-content::-webkit-scrollbar-thumb { background: #444; border-radius: 10px; }
  .sc-content::-webkit-scrollbar-thumb:hover { background: var(--accent); }
  
  .sc-title {
    font-family: 'Segoe UI', sans-serif; font-weight: 700; color: #fff; margin-bottom: 8px;
    font-size: 1.05rem; display: flex; align-items: center; flex-shrink: 0;
  }
  
  .sc-label {
    font-size: 0.65rem; text-transform: uppercase; color: var(--accent);
    font-weight: 700; letter-spacing: 1px; margin-bottom: 4px; flex-shrink: 0;
  }

  /* === TEXTO DEL SPEECH === */
  .sc-content pre { 
    margin: 0 !important; 
    background: transparent !important; 
    border: none !important;            
    padding: 0 !important;              
    white-space: pre-wrap !important; 
    word-break: break-word !important;
  }
  
  .sc-content code { 
    font-family: 'Consolas', monospace !important; 
    font-size: 0.82rem !important;  
    line-height: 1.4 !important;   
    color: #ddd !important;
  }

  /* RESPONSIVE */
  @media (max-width: 850px) {
    .split-card { flex-direction: column; height: auto; } 
    .sc-visual { flex: auto; width: 100%; border-right: none; border-bottom: 1px solid #333; padding: 20px; height: 200px; }
    .sc-divider { width: 100%; height: 2px; background: var(--accent); }
    .sc-content { width: 100%; height: auto; max-height: 350px; }
  }

</style>

# Autogestión

<h2>📡 WiFi & Conectividad</h2>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/administrar-red.png" alt="Cambio Clave">
    <a href="../assets/autogestion/administrar-red.png" download="Administrar_Red.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Cambio de contraseña (Wi-Fi)</div>
    <div class="sc-label">Speech Sugerido</div>
    ~~~text
    Te recuerdo que cualquier cosa también podés modificar la contraseña y nombre de tu red por la App Mi Personal Flow 📲.

    Acá te dejo una imagen con el paso a paso para que puedas realizarlo 🙌. 
    ~~~
  </div>
</div>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/mantenimiento-red.jpeg" alt="Mantenimiento Red">
    <a href="../assets/autogestion/mantenimiento-red.jpeg" download="Mantenimiento-red.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Realizar Mantenimiento</div>
    <div class="sc-label">Speech Sugerido</div>
~~~text
Te cuento que si volvés a tener inconvenientes con tu Wi-Fi 📶, podés probar optimizar la red directamente desde la App Mi Personal 📲.

Tenés que buscar la opción llamada "Realizar mantenimiento" 🛠️.

Esta función actualiza los radios y frecuencias de tu equipo automáticamente 📡. Es ideal para "limpiar" la señal y solucionar problemas de lentitud o cortes al instante 🚀.
~~~
  </div>
</div>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/DISPOSITIVOS-CONECTADOS.png" alt="Dispositivos">
    <a href="../assets/autogestion/DISPOSITIVOS-CONECTADOS.png" download="Dispositivos_Conectados.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Dispositivos conectados a Wi-Fi</div>
    <div class="sc-label">Speech Sugerido</div>
    ~~~text
    📱 Desde la App Mi Personal Flow, ingresando a la sección Mi Wi-Fi, vas a encontrar la opción "Dispositivos conectados".

    👀 Allí vas a poder ver en tiempo real quiénes están conectados a tus redes Wi-Fi, para que puedas controlar y gestionar los accesos fácilmente. 
    ~~~
  </div>
</div>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/CONTINUIDAD-GB.png" alt="Backup">
    <a href="../assets/autogestion/CONTINUIDAD-GB.png" download="Continuidad_GB.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Wifi Backup</div>
    <div class="sc-label">Speech Sugerido</div>
  ~~~text
  Estuve analizando tu servicio para verificar lo que ocurre🧐 te comento que en este momento detectamos una falla general en tu zona y por ello, ya nos encontramos trabajando para poder devolverte el servicio a la brevedad, los trabajos suelen durar 24 hs aunque puede que se resuelva antes de ese tiempo! 

  Desde ya, te solicito disculpas por las molestias ocasionadas🙏 y te recordamos que desde nuestra App Mi Personal Flow podes seguir online activando los GB de continuidad🤗 Ingresas en la opción "hogar ver/servicios" donde podrás verificar afectación en zona, seguimiento y activación del pack para seguir navegando! Se tratan de 50GB  de uno libre sin costo adicional para que puedas activar en todas las lineas que tengas bajo la misma titularidad del servicio hogar, tendrán una duración de 24 horas❤
  ~~~
  </div>
</div>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/WIFI-ZONE.png" alt="Wifi Zone">
    <a href="../assets/autogestion/WIFI-ZONE.png" download="Wifi_Zone.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Personal Wifi Zone</div>
    <div class="sc-label">Speech Sugerido</div>
    ~~~text
    ¡Para que no pierdas conexión, te comento que contamos con la opción de que uses la red Personal Wifi Zone!

    Te dejo los pasos para acceder:

        Ingresá desde tu dispositivo a las redes wifi disponibles.
        Seleccioná la red Personal Wifi Zone.
        Ingresá tus datos de cliente (son los mismos que usas para entrar a Flow o a Mi Personal) y completá la cuenta de seguridad.
        Hacé clic en ingresar y ¡listo!

    Si necesitas registrarte o recuperar tu clave, podés hacerlo acá: https://regbf.telecom.com.ar/

    ✅ Dato importante: Podés conectar hasta 3 dispositivos de manera simultánea.
    ~~~
  </div>
</div>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/EXTENSORES.png" alt="Extensores">
    <a href="../assets/autogestion/EXTENSORES.png" download="Extensores.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Extensores Wi-Fi</div>
    <div class="sc-label">Speech Sugerido</div>
~~~text
📱 Desde la app Mi Personal Flow, podés conseguir extensores de señal para que el WiFi 📶 llegue mejor a todos los rincones de tu casa.

Mirá la imagen que te dejamos con el paso a paso... ¡y listo, a disfrutar sin cortes! 😊 
~~~
  </div>
</div>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/Ubicacion-recomendada.png" alt="Ubicacion">
    <a href="../assets/autogestion/Ubicacion-recomendada.png" download="Ubicacion_Recomendada.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Ubicación recomendada (Módem)</div>
    <div class="sc-label">Speech Sugerido</div>
    ~~~text
    Acá te muestro una foto donde se detalla lo recomendable 😊

    📶 Ubicá el módem vertical, a +1 m del piso, fuera de muebles.

    ⚠️ No debe haber dispositivos cerca que puedan generar interferencias en la señal Wi-Fi (microondas, teléfonos inalámbricos, espejos u otros electrodomésticos).

    🌐 Usá 2.4 GHz para alcance (50-60 Mbps) o 5 GHz para velocidad (menor alcance)
    ~~~
  </div>
</div>

<h2>⚙️ Gestión de Cuenta</h2>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/reagenda.png" alt="Agenda">
    <a href="../assets/autogestion/reagenda.png" download="Reagenda.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Modificación de agenda</div>
    <div class="sc-label">Speech Sugerido</div>
~~~text
📆 ¿Sabías que podés consultar, reagendar o cancelar tu visita técnica sin llamar ni esperar?
📲 ¡Todo desde la aplicación de Mi Personal Flow!
🔧 Sólo tenés que acceder a Soporte Técnico ➡️ Visita Técnica y desde ahí podés gestionar tu cita en segundos ⏱️
🖼️ Te adjunto una imagen explicativa para que lo veas más claro 🔗 Y si todavía no te has registrado, podés hacerlo desde acá: https://regbf.telecom.com.ar
~~~
  </div>
</div>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/DESENLISTAR-DISPOSITIVOS.png" alt="Desenlistar">
    <a href="../assets/autogestion/DESENLISTAR-DISPOSITIVOS.png" download="Desenlistar_Dispositivos.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Desenlistar dispositivos</div>
    <div class="sc-label">Speech Sugerido</div>
    ~~~text
    Recordá que vas a poder hacer este tipo de modificaciones en tu cuenta siempre que lo necesites, desde nuestra app Flow.

    Te dejo el paso a paso:

    ➡️ Ingresando en tu perfil
    ➡️ Configuración de la cuenta
    ➡️ Allí mismo te saldrá la columna "Mis dispositivos" donde podrás visualizar los dispositivos conectados a la cuenta y eliminarlos si así lo deseas. 
    ~~~
  </div>
</div>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/GESTIONAR-SUSCRIPCIONES.png" alt="Suscripciones">
    <a href="../assets/autogestion/GESTIONAR-SUSCRIPCIONES.png" download="Gestionar_Suscripciones.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Gestionar suscripciones</div>
    <div class="sc-label">Speech Sugerido</div>
  ~~~text
  ✨ Te recordamos que podés gestionar tus contenidos premium de manera rápida y sencilla desde nuestra app 📲. Solo tenés que ingresar a la sección de "Mi Cuenta" 👤 para activar, modificar o cancelar tus suscripciones cuando lo necesites, sin demoras ni llamadas ☎️.

  🛋️ Es simple, cómodo y está disponible estés donde estés 🌍. Si aún no tenés la app, podés descargarla desde tu tienda de aplicaciones. 
  ~~~
  </div>
</div>

<div class="split-card">
  <div class="sc-visual">
    <img src="../assets/autogestion/CODIGOTV.png" alt="Vincular TV">
    <a href="../assets/autogestion/CODIGOTV.png" download="Codigo_TV.png" class="dl-btn">⬇️ Descargar</a>
  </div>
  <div class="sc-divider"></div>
  <div class="sc-content">
    <div class="sc-title">Código de vinculación con TV</div>
    <div class="sc-label">Speech Sugerido</div>
    ~~~text
    📱➡️📺 Con tu celu podés iniciar sesión en Flow en la TV en pocos pasos.

    Mirá la imagen que te dejamos con el paso a paso y listo, ¡a disfrutar! 
    ~~~
  </div>
</div>