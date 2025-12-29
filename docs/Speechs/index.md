---
title: Speechs
edit_uri: ""
hide:
  - navigation
---

<style>
  /* === SPEECHS === */
  
  :root {
    /* Variables de Color */
    --bg-page: #050505;
    --card-bg: #161616;
    --code-bg: #000000; 
    --accent: #d8b4fe;
    --accent-glow: rgba(216, 180, 254, 0.15);
    --accent-strong-glow: rgba(216, 180, 254, 0.4);
    --border: #333;
    
    /* Variables de Estructura */
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

  /* Fondo General */
  body {
    background-color: var(--bg-page) !important;
    background-image: radial-gradient(circle at 50% 0%, #1a0a2a, #050505 50%) !important;
    background-attachment: fixed !important;
  }
  .md-container, .md-main__inner { background: transparent !important; }

  /* 3. TIPOGRAFÍA Y TÍTULOS */
  h1 {
    font-family: 'Segoe UI', Roboto, sans-serif; 
    font-weight: 900; font-size: 2.8rem; letter-spacing: -1px; 
    margin-bottom: 40px !important; padding-bottom: 20px; 
    border-bottom: 4px solid #1a1a1a; text-transform: uppercase; 
    display: flex; align-items: center;
    background: linear-gradient(to right, #fff, #999);
    -webkit-background-clip: text; -webkit-text-fill-color: transparent;
  }
  h1::before { content: '💬'; margin-right: 20px; font-size: 2.4rem; -webkit-text-fill-color: initial; }

  h2 {
    font-family: 'Segoe UI', sans-serif; font-size: 1.2rem; font-weight: 800;
    color: #fff; text-transform: uppercase; letter-spacing: 0.5px;
    margin-top: 60px !important; margin-bottom: 20px;
    border-left: 6px solid var(--accent); background: linear-gradient(90deg, #1a1a1a, transparent);
    padding: 12px 20px; border-radius: 0 4px 4px 0;
    box-shadow: -5px 0 20px var(--accent-glow); display: flex; align-items: center;
  }

  /* 4. TABLA DE CONTENIDOS (DERECHA) */
  .md-sidebar--secondary .md-nav__title {
    visibility: hidden; position: relative; height: 40px; margin-bottom: 15px;
    border-bottom: 2px solid var(--accent); box-shadow: 0 2px 10px var(--accent-glow);
  }
  .md-sidebar--secondary .md-nav__title::before {
    content: "ÍNDICE DE SECCIÓN"; visibility: visible; position: absolute; top: 0; left: 0;
    font-family: 'Segoe UI', sans-serif; text-transform: uppercase; font-weight: 900;
    letter-spacing: 1px; color: var(--accent); font-size: 1rem; line-height: 30px;
    text-shadow: 0 0 8px var(--accent-glow);
  }
  .md-sidebar--secondary .md-nav__link {
    font-family: 'Segoe UI', sans-serif; font-size: 0.95rem; padding: 8px 0; color: #888;
    transition: all 0.2s ease; display: block;
  }
  .md-sidebar--secondary .md-nav__link:hover { color: var(--accent); transform: translateX(5px); }
  .md-sidebar--secondary .md-nav__link--active {
    color: #fff !important; font-weight: 800; border-left: 4px solid var(--accent);
    padding-left: 15px; background: linear-gradient(90deg, var(--accent-glow), transparent);
    text-shadow: 0 0 12px var(--accent-strong-glow);
  }

  /* 5. ACORDEONES (SPEECH STACK) */
  .speech-stack { display: flex; flex-direction: column; gap: 10px; max-width: 100%; }

  details.speech-item {
    background: var(--card-bg); border: 1px solid var(--border);
    border-radius: 6px; overflow: hidden; transition: border-color 0.2s;
  }
  details.speech-item:hover { border-color: #666; }

  summary.speech-trigger {
    padding: 15px 25px; cursor: pointer;
    font-family: 'Segoe UI', sans-serif; font-weight: 700; font-size: 0.95rem;
    color: #e0e0e0; background: #1a1a1a;
    display: flex !important; justify-content: space-between; align-items: center;
    list-style: none; user-select: none; text-transform: uppercase; letter-spacing: 0.5px;
  }
  
  /* Reset de marcadores */
  summary.speech-trigger::-webkit-details-marker { display: none; }
  summary.speech-trigger::marker { content: ""; display: none; }
  summary.speech-trigger::after { content: '+'; font-family: monospace; font-size: 1.4rem; color: #555; }
  
  /* Estado Abierto */
  details[open] summary.speech-trigger { background: #111; border-bottom: 1px solid #222; color: #fff; }
  details[open] summary.speech-trigger::after { content: '-'; color: var(--accent); }

  /* 6. ESTILO DEL TEXTO (GUIONES) */
  details.speech-item pre { margin: 0 !important; border: none !important; width: 100%; }
  
  details.speech-item code {
    background-color: var(--code-bg) !important;
    font-family: 'Consolas', monospace !important; font-size: 0.95rem !important;
    color: #a5d6ff !important; /* Azul técnico */
    padding: 25px !important;
    
    /* Ajuste automático de línea */
    white-space: pre-wrap !important; 
    word-break: break-word !important;
    line-height: 1.6 !important;
    
    display: block; border: none !important;
  }
  
  .md-typeset .speech-item .md-typeset__scrollwrap { margin: 0 !important; }

/* === EXTERMINADOR DEL LÁPIZ AZUL  === */
  summary.speech-trigger::before {
    content: none !important;
    display: none !important;
    background-image: none !important;
    width: 0 !important;
  }

    /*  EXTERMINADOR DE FOOTER */
  .md-footer, .md-footer__inner, .md-copyright, footer, .md-footer-meta, .md-footer-nav { 
    display: none !important; height: 0 !important; overflow: hidden !important; 
    padding: 0 !important; margin: 0 !important; border: none !important;
  }
  .md-content__button, .md-icon--edit, a[href*="edit"] { display: none !important; }

</style>

## 📶 Redes y Conectividad

<div class="speech-stack">

<details class="speech-item">
<summary class="speech-trigger">Optimización de Señal</summary>
<pre><code>Te comento que desde acá realicé una optimización de señal a tus redes para mejorar el alcance y la estabilidad de las redes. Recordá que podrás realizar esta optimización siempre que notes que las redes están lentas o notas micro cortes en las mismas, desde la app de Mi Personal, de la manera más rápida y sencilla, para mejorar el rendimiento de tus redes 📶</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Frecuencia Redes (2.4 vs 5.8)</summary>
<pre><code>Me gustaría explicarte como funcionan estas redes:

->La red 2.4 GHz cuenta con una velocidad limitada, pero es de largo alcance. La red llega hasta 50 MB y su distancia máxima es de 15 metros promedio, esta es muy fácil de congestionar y puede impactar en cortes y lentitud en tu servicio (generalmente con dispositivos de alto tráfico de datos: CEL,TV,PCs)

->La red 5.8 GHz alcanza la mayor velocidad, la contratada, pero esta red tiene un alcance de hasta de 10 metros promedio de rango.

Para que tu dispositivo pueda visualizar esta red, deberá de contar con una placa de red que soporte esta tecnología</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Bandsteering</summary>
<pre><code>Te comento que tenés la configuración del Modem con BandSteering lo cual hace que se designe de manera automática una de las dos señales de wifi 2.4 y 5.8. Esto suele generar que se desconecte temporalmente mientras cambia de red cuando se tiene varios dispositivos conectados al wifi, por lo mismo si te parece podemos separar nuevamente las redes wifi, así veríficas el funcionamiento 😊</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Problema IP Starlink</summary>
<pre><code>En este caso el internet de Starlink está asignando una IP de otro país a los dispositivos, esto ocasiona que la app tenga estos problemas a la hora de cargar contenido ya que está habilitado solo para Argentina

Te recomiendo contactarte con su centro de ayudas en la pagina de starlink.com para verificar si pueden cambiarla o podes tratar de reiniciar el modem para que te brinde una ip argentina</code></pre>
</details>

</div>

## 📺 Flow y Dispositivos

<div class="speech-stack">

<details class="speech-item">
<summary class="speech-trigger">Botón Flow (Optimización Deco)</summary>
<pre><code>Te voy a pedir que mantengas presionado durante 15 segundos el botón que dice "Flow" en el control remoto del deco, hasta que aparezca un cartel en pantalla que diga cerrando aplicaciones, porfa🙏🏼 

Perfecto, lo que hicimos es una optimización del deco, haciendo esto borramos memoria, caché y almacenamiento que se acumula, para que funcione con normalidad. Si te vuelve a suceder podés repetir el procedimiento</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Reset Control Remoto</summary>
<pre><code>Con el TV y el deco prendidos, presiona simultáneamente el botón 1 y 6 hasta que el LED se encienda y quede fija. A continuación, soltar ambos botones.

Después, presioná los botones 9 8 1, uno por uno. El LED parpadeará.

A continuación probá el control remoto.</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Pasos Registro App</summary>
<pre><code>Ingresa al siguiente link para registrarte: https://unifiedsignup.telecom.com.ar/

Ingresá los datos del titular del servicio: Tipo de Documento, DNI y Genero.

Colocá el mail que utilizarás para el ingreso a Flow.

Te enviaremos un código de 6 dígitos para que generes una contraseña.

Validá los datos del titular: completá el campo “Altura” y los 4 últimos dígitos del número de línea.

¡Listo! Ya generaste tu usuario y contraseña, entra a la app o la página de Flow App y disfrutá de todo el contenido.

Bien, vamos a hacer la siguiente prueba.</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Continuidad (Flow App)</summary>
<pre><code>Mientras tanto, queremos ofrecerte una alternativa para que sigas disfrutando de todo lo que te gusta 📺✨

Podés acceder a la Flow App, que está disponible para celulares 📱, tablets 💻 y también en Smart TVs 🖥️, sin costo extra. Ahí vas a encontrar más de 150 canales en vivo, series, pelis y mucho más 🎬🍿

Si querés, te puedo ayudar paso a paso para descargarla y dejarla lista 🙌 Queremos que sigas disfrutando de Flow al máximo, incluso cuando surgen estos imprevistos 💚</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Configuración Smarthome</summary>
<pre><code>📌 Agregar cámara: Te aparecerá la opción para agregar una cámara.

📌 Reiniciar la cámara: Presioná el botón Reset (ubicado en la parte inferior del módulo superior de la lente) hasta que escuches el mensaje: "Listo para iniciar la configuración".

📌 Permitir ubicación: Una vez encendida la cámara, concedé acceso a la ubicación según tu preferencia.

📌 Red WiFi: Conectá la cámara a una red WiFi de 2.4 GHz.

📌 Escaneo de QR: Con la cámara WiFi, escaneá el código QR que aparece en tu celular. Si el escaneo fue exitoso, escucharás: "Código QR registrado, conectando". Al finalizar, escucharás: "Configuración finalizada".

▶ Video de ayuda: Te comparto este video por si necesitás una guía más visual: https://youtu.be/YSSzPgWYItE?si=XHL5DpDTF49Lg2q-</code></pre>
</details>

</div>

## 🛠️ Gestión Técnica y Admin

<div class="speech-stack">

<details class="speech-item">
<summary class="speech-trigger">Validación de Datos</summary>
<pre><code>Te pido que me brindes los siguientes datos para poder ayudarte en tu consulta.

Nombre completo y DNI de la persona titular del servicio.
Domicilio dónde se encuentra instalado el servicio.
Detalle de la consulta o inconveniente que estés presentando.</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Posible Masivo</summary>
<pre><code>Corroborando tu servicio y lo detallado durante nuestra conversación, es necesario que agendemos una visita técnica para tu domicilio 🛠️ Dado que se detecta que otros equipos en la zona se encuentran sin señal, en caso de declararse un inconveniente general, tu orden particular se anulará de forma automática y se tratará la falla directamente en la caja de señal afectada ⚠️

Recordá que desde la aplicación de Mi Personal podés verificar el estado de tu servicio en tiempo real y el estimado de resolución de la incidencia general en caso de que se declare. En su defecto, podés gestionar tu asistencia técnica 📱</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Error Agenda</summary>
<pre><code>Te informo que estamos realizando tareas de mantenimiento en nuestro sistema lo que nos impide agendar correctamente tu visita técnica ahora mismo ⚠️

Mantendremos tus datos de contacto y te la estaremos asignando apenas esta situación esté regularizada 🛠️ Te va a llegar un mensaje de WhatsApp por este mismo chat confirmándola y podrás gestionarla desde la aplicación de Mi Personal Flow 📲

En caso no recibirlo, comunícate nuevamente con nosotros luego de las 18:00 hs. del día de hoy para continuar con tu gestión 🕕</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Nota de Crédito</summary>
<pre><code>📄 El número de gestión correspondiente es: [Número de gestión].

💰 Se generó una nota de crédito por el monto de [Monto], que será aplicada automáticamente en tu próxima factura para compensar el inconveniente.

🙏 Lamentamos sinceramente lo ocurrido y agradecemos mucho tu paciencia y comprensión mientras trabajábamos en la resolución. Nuestro compromiso es brindarte un servicio de calidad, y ya estamos tomando medidas para que esto no vuelva a repetirse.

🤝 Estamos para ayudarte siempre. Si hay algo más en lo que pueda darte una mano, no dudes en decírmelo.</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Sin Sistema</summary>
<pre><code>Te informo que en este momento presentamos un inconveniente sobre nuestro sistema, por tal motivo no estamos pudiendo avanzar con la gestión, te pido si podes comunicarte dentro de las siguientes 24 hs para que podamos ayudarte 🙌 Lamento mucho los inconvenientes ocasionados</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">No quiere realizar chequeos</summary>
<pre><code>Entiendo que prefieras no hacer los chequeos, pero para avanzar es necesario realizar el análisis correspondiente. ✨ Si cambias de opinión, podemos continuarlos y resolver tu consulta. De lo contrario, quedamos atentos a tu próximo contacto, que tengas una linda noche! ☺️</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Formato no soportado</summary>
<pre><code>No puedo ver tu último mensaje. 😢 Si es un audio 🎙, ¿me lo puedes escribir? Y si es una imagen 📷, ¿puedes enviarla en un formato más ligero?

No puedo ver archivos: .docx, audios, videos, comentarios en las fotos, GIF y stickers, pero sí puedo ver emojis, PDF imágenes.

¡Espero tu respuesta!</code></pre>
</details>

</div>

## 📞 Derivaciones y Contactos

<div class="speech-stack">

<details class="speech-item">
<summary class="speech-trigger">Fibertel Lite - Arnet (xDSL)</summary>
<pre><code>Tu servicio de Internet + Telefonía Fija pertenece al segmento de Fibertel Lite - Arnet 📡
Para brindarte asistencia sobre tu servicio, contáctanos telefónicamente 📞 ¡Es el medio exclusivo del servicio!

A continuación, te menciono los números de contacto:

Por consultas técnicas 🛠️
📞 0800 - 888 - 0114 desde cualquier teléfono
☎️ 114 desde línea fija
📲 *114 desde línea Personal

Por consultas administrativas 📋
📞 0800 - 888 - 0112 desde cualquier teléfono
☎️ 112 desde línea fija
📲 *112 desde línea Personal

¡Te esperamos por estos canales para ayudarte! 💚</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">TeleRed</summary>
<pre><code>Te comento que tu servicio pertenece al segmento de TeleRed así que te comparto la línea exclusiva de atención para que puedas canalizar tu consulta:

📞 0800-444-0351 desde cualquier teléfono

¡Te esperamos por este canal para ayudarte! Que tengas un buen día 💚</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Corporativo</summary>
<pre><code>Te comento que las consultas por servicio corporativo se gestionan a través un número telefónico así que te comparto el mismo para que puedas comunicarte:

📞 0800-555-7963 desde cualquier teléfono

¡Te esperamos por este canal para ayudarte! 💚</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Ventas</summary>
<pre><code>Te comparto el número de WhatsApp del sector de ventas

https://api.whatsapp.com/send?phone=5491126222222</code></pre>
</details>

<details class="speech-item">
<summary class="speech-trigger">Personal Pay</summary>
<pre><code>Te comparto el número de WhatsApp del sector de Personal Pay

https://api.whatsapp.com/send/?phone=541165979041</code></pre>
</details>

</div>