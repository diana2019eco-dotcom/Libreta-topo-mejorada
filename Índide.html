<!DOCTYPE html>
<html lang="es">
<link rel="manifest" href="manifest.json">
<script>
  if ('serviceWorker' in navigator) {
    navigator.serviceWorker.register('sw.js');
  }
</script>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <title>Estación Total · NPL-332</title>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&family=DM+Sans:wght@400;500;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: #0d1117;
            --surface: #161b22;
            --surface2: #21262d;
            --surface3: #30363d;
            --border: #30363d;
            --border2: #484f58;
            --teal: #00e5cc;
            --teal-dim: #00b8a4;
            --teal-bg: rgba(0,229,204,0.08);
            --teal-bg2: rgba(0,229,204,0.14);
            --amber: #f0a500;
            --amber-bg: rgba(240,165,0,0.1);
            --red: #f85149;
            --red-bg: rgba(248,81,73,0.1);
            --blue: #58a6ff;
            --blue-bg: rgba(88,166,255,0.1);
            --purple: #bc8cff;
            --purple-bg: rgba(188,140,255,0.1);
            --green: #3fb950;
            --green-bg: rgba(63,185,80,0.1);
            --text: #e6edf3;
            --text2: #8b949e;
            --text3: #484f58;
            --mono: 'JetBrains Mono', monospace;
            --sans: 'DM Sans', sans-serif;
            --radius: 10px;
        }

        * {
            box-sizing: border-box; margin: 0; padding: 0;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: var(--sans);
            background: var(--bg);
            color: var(--text);
            min-height: 100vh;
            /* Safe area para iPhone X / notch / Dynamic Island */
            padding: max(12px, env(safe-area-inset-top))
                     max(12px, env(safe-area-inset-right))
                     max(12px, env(safe-area-inset-bottom))
                     max(12px, env(safe-area-inset-left));
            overflow-x: hidden;
            /* Mejor scroll en iOS */
            -webkit-overflow-scrolling: touch;
        }

        /* HEADER */
        .app-header {
            display: flex; align-items: center; justify-content: space-between;
            padding: 12px 16px; margin-bottom: 14px;
            background: var(--surface); border: 1px solid var(--border);
            border-radius: 14px;
        }
        .app-title { display: flex; align-items: center; gap: 10px; }
        .app-title-icon {
            width: 36px; height: 36px; background: var(--teal-bg2);
            border: 1px solid var(--teal); border-radius: 8px;
            display: flex; align-items: center; justify-content: center;
            font-size: 18px;
        }
        .app-title h1 { font-size: 1.05em; font-weight: 800; color: var(--text); letter-spacing: -0.3px; }
        .app-title span { font-size: 0.75em; color: var(--text2); font-family: var(--mono); }

        /* UNIT SWITCHER */
        .unit-switcher {
            display: flex; gap: 4px; background: var(--bg);
            border: 1px solid var(--border); border-radius: 8px; padding: 3px;
        }
        .unit-btn {
            padding: 5px 10px; font-size: 0.78em; font-weight: 700;
            border: none; border-radius: 6px; cursor: pointer;
            font-family: var(--mono); transition: all 0.2s;
            background: transparent; color: var(--text2);
            min-height: 36px;
            touch-action: manipulation;
            -webkit-appearance: none;
        }
        .unit-btn.active {
            background: var(--teal); color: #000;
        }

        /* TABS */
        .tabs {
            display: grid; grid-template-columns: repeat(6, 1fr); gap: 4px;
            margin-bottom: 14px; background: var(--surface);
            padding: 5px; border-radius: 12px; border: 1px solid var(--border);
        }
        .tab-btn {
            padding: 10px 6px; font-weight: 700; font-size: 0.75em;
            border: none; border-radius: 7px; background: transparent;
            color: var(--text2); cursor: pointer; transition: all 0.2s;
            font-family: var(--sans); letter-spacing: 0.2px;
            min-height: 44px;
            touch-action: manipulation;
            -webkit-appearance: none;
        }
        .tab-btn.active { background: var(--surface2); color: var(--teal); border: 1px solid var(--border2); }
        .tab-content { display: none; }
        .tab-content.active { display: block; }

        /* CARDS */
        .card {
            background: var(--surface); border: 1px solid var(--border);
            border-radius: 14px; padding: 16px; margin-bottom: 12px;
        }
        .card-title {
            font-size: 0.9em; font-weight: 700; color: var(--text);
            margin-bottom: 14px; padding-bottom: 10px;
            border-bottom: 1px solid var(--border);
            display: flex; align-items: center; gap: 8px;
        }
        .card-title .badge {
            font-size: 0.72em; padding: 2px 7px; border-radius: 20px;
            font-family: var(--mono); font-weight: 600;
        }

        /* LAYOUTS */
        .row { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
        .row3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; }
        .row4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: 8px; }

        /* LABELS & INPUTS */
        label {
            display: block; font-size: 0.75em; font-weight: 700;
            color: var(--text2); margin-bottom: 5px; letter-spacing: 0.3px;
            text-transform: uppercase;
        }

        input, select {
            width: 100%; padding: 10px 12px;
            background: var(--bg); border: 1.5px solid var(--border);
            border-radius: var(--radius); color: var(--text);
            font-family: var(--mono); font-size: 16px; font-weight: 600;
            transition: all 0.2s;
            /* iOS: evita el zoom automático al hacer foco y normaliza apariencia */
            -webkit-appearance: none;
            -moz-appearance: none;
            appearance: none;
        }
        /* Restaurar flecha en select */
        select {
            background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='8' viewBox='0 0 12 8'%3E%3Cpath d='M1 1l5 5 5-5' stroke='%238b949e' stroke-width='1.5' fill='none' stroke-linecap='round'/%3E%3C/svg%3E");
            background-repeat: no-repeat;
            background-position: right 12px center;
            padding-right: 32px;
        }
        input:focus, select:focus {
            border-color: var(--teal); outline: none;
            box-shadow: 0 0 0 3px rgba(0,229,204,0.1);
        }
        select option { background: var(--surface2); }

        /* DMS INPUT GROUP */
        .dms-group { display: flex; gap: 4px; align-items: center; }
        .dms-group input {
            text-align: center;
            padding: 10px 4px;
            min-width: 52px;
            flex: 1;
        }
        .dms-sep { color: var(--teal); font-weight: 700; font-family: var(--mono); font-size: 0.9em; flex-shrink: 0; }
        .dms-result {
            font-family: var(--mono); font-size: 0.8em; color: var(--teal);
            margin-top: 4px; padding: 4px 8px;
            background: var(--teal-bg); border-radius: 6px; text-align: center;
        }

        /* BUTTONS */
        .btn {
            width: 100%; padding: 11px; font-size: 0.9em; font-weight: 700;
            border: none; border-radius: var(--radius); cursor: pointer;
            font-family: var(--sans); letter-spacing: 0.3px;
            transition: all 0.18s; margin-top: 6px;
            min-height: 44px; /* iOS: área mínima de toque */
            -webkit-appearance: none;
            touch-action: manipulation; /* elimina el delay de 300ms en iOS */
        }
        .btn:active { transform: scale(0.97); }
        .btn-teal { background: var(--teal); color: #000; }
        .btn-teal:hover { background: var(--teal-dim); }
        .btn-amber { background: var(--amber); color: #000; }
        .btn-blue { background: var(--blue); color: #000; }
        .btn-red { background: var(--red); color: white; }
        .btn-purple { background: var(--purple); color: #000; }
        .btn-green { background: var(--green); color: #000; }
        .btn-ghost {
            background: var(--surface2); color: var(--text);
            border: 1px solid var(--border2);
        }
        .btn-ghost:hover { border-color: var(--teal); color: var(--teal); }
        .btn-sm { padding: 6px 10px; font-size: 0.78em; margin-top: 0; width: auto; }

        /* RESULT BOXES */
        .result-box {
            padding: 12px; border-radius: var(--radius); margin-top: 10px;
            font-family: var(--mono); font-size: 0.85em; display: none; line-height: 1.6;
        }
        .result-teal { background: var(--teal-bg2); border: 1px solid var(--teal); color: var(--teal); }
        .result-amber { background: var(--amber-bg); border: 1px solid var(--amber); color: var(--amber); }
        .result-blue { background: var(--blue-bg); border: 1px solid var(--blue); color: var(--blue); }
        .result-red { background: var(--red-bg); border: 1px solid var(--red); color: var(--red); }
        .result-purple { background: var(--purple-bg); border: 1px solid var(--purple); color: var(--purple); }
        .result-green { background: var(--green-bg); border: 1px solid var(--green); color: var(--green); }

        /* STATUS BAR */
        .status-bar {
            display: flex; align-items: center; gap: 8px;
            padding: 10px 14px; border-radius: 10px; margin-bottom: 14px;
            font-size: 0.82em; font-family: var(--mono);
            background: var(--surface); border: 1px solid var(--border);
        }
        .status-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; }
        .status-dot.active { background: var(--green); box-shadow: 0 0 8px var(--green); }
        .status-dot.inactive { background: var(--red); }

        /* WORKSPACE (bottom panels) */
        .workspace { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-top: 14px; }
        .panel {
            background: var(--surface); border: 1px solid var(--border);
            border-radius: 14px; padding: 14px;
        }
        .panel-title { font-size: 0.82em; font-weight: 700; color: var(--text2); margin-bottom: 10px; text-transform: uppercase; letter-spacing: 0.5px; }
        .panel-lista { height: 340px; overflow-y: auto; -webkit-overflow-scrolling: touch; }
        .panel-lista::-webkit-scrollbar { width: 4px; }
        .panel-lista::-webkit-scrollbar-track { background: transparent; }
        .panel-lista::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 2px; }

        /* POINT ITEMS */
        .item-punto {
            background: var(--surface2); padding: 10px 12px; border-radius: 8px;
            border: 1px solid var(--border); font-size: 0.8em; position: relative;
            margin-bottom: 6px; transition: border-color 0.2s;
        }
        .item-punto:hover { border-color: var(--border2); }
        .item-punto-base { border-color: var(--teal); background: var(--teal-bg); }
        .item-punto .pt-name { font-family: var(--mono); font-weight: 700; color: var(--teal); font-size: 0.95em; }
        .item-punto .pt-code { font-size: 0.75em; padding: 1px 5px; border-radius: 4px; font-family: var(--mono); font-weight: 700; }
        .item-punto .pt-coords { color: var(--text2); margin-top: 3px; font-family: var(--mono); font-size: 0.9em; }
        .item-punto .pt-replanteo { color: var(--amber); margin-top: 2px; font-family: var(--mono); font-size: 0.85em; }
        .btn-del { position: absolute; top: 8px; right: 8px; background: var(--red-bg); color: var(--red); border: none; border-radius: 5px; padding: 3px 7px; font-size: 0.75em; font-weight: 700; cursor: pointer; font-family: var(--mono); }
        .btn-del:hover { background: var(--red); color: white; }

        /* CANVAS */
        .canvas-wrap {
            position: relative; margin-top: 6px; border-radius: 10px;
            overflow: hidden; border: 1px solid var(--border); background: #010409;
        }
        canvas {
            background: #010409;
            width: 100%; height: 280px; display: block;
            touch-action: none; /* nosotros gestionamos pan/zoom a mano */
            cursor: grab;
        }
        canvas.dragging { cursor: grabbing; }
        .zoom-controls {
            position: absolute; top: 8px; right: 8px;
            display: flex; flex-direction: column; gap: 4px; z-index: 5;
        }
        .zoom-btn {
            width: 30px; height: 30px; border-radius: 7px;
            background: rgba(22,27,34,0.9); border: 1px solid var(--border2);
            color: var(--teal); font-weight: 800; font-size: 1em;
            display: flex; align-items: center; justify-content: center;
            cursor: pointer; touch-action: manipulation; -webkit-appearance: none;
        }
        .zoom-btn:active { background: var(--teal-bg2); }
        .zoom-level {
            position: absolute; bottom: 8px; left: 8px;
            font-family: var(--mono); font-size: 0.7em; color: var(--text2);
            background: rgba(22,27,34,0.85); border: 1px solid var(--border);
            padding: 2px 7px; border-radius: 6px; z-index: 5; pointer-events: none;
        }
        .layer-controls { display: flex; gap: 12px; font-size: 0.78em; font-weight: 700; color: var(--text2); margin-top: 8px; flex-wrap: wrap; }
        .layer-controls label { margin: 0; display: flex; align-items: center; gap: 4px; text-transform: none; font-size: 1em; cursor: pointer; }
        .layer-controls input[type=checkbox] { width: auto; }

        /* CONVERTER TAB */
        .conv-grid { display: grid; grid-template-columns: 1fr auto 1fr; align-items: start; gap: 16px; }
        .conv-arrow { display: flex; align-items: center; justify-content: center; height: 44px; padding-top: 24px; font-size: 1.4em; color: var(--teal); }

        /* SEPARATOR */
        .sep { height: 1px; background: var(--border); margin: 14px 0; }

        /* ACTION ROW */
        .action-row { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 8px; margin-top: 10px; }

        /* SECTION LABEL */
        .section-label {
            font-size: 0.7em; font-weight: 700; text-transform: uppercase;
            letter-spacing: 1px; color: var(--text3); margin: 14px 0 8px 0;
        }

        /* HIGHLIGHT */
        b.hl { color: var(--teal); }
        b.hl-amber { color: var(--amber); }

        /* TOOLTIP chip */
        .chip {
            display: inline-block; padding: 2px 7px; border-radius: 4px;
            font-size: 0.72em; font-family: var(--mono); font-weight: 700;
            vertical-align: middle;
        }
        .chip-marco { background: rgba(248,81,73,0.2); color: var(--red); }
        .chip-inter { background: var(--amber-bg); color: var(--amber); }
        .chip-ref { background: var(--purple-bg); color: var(--purple); }
        .chip-est { background: var(--blue-bg); color: var(--blue); }

        /* Info note */
        .note {
            background: var(--amber-bg); border: 1px solid var(--amber);
            border-radius: 8px; padding: 10px 12px; font-size: 0.8em;
            color: var(--amber); margin-top: 10px; line-height: 1.5;
        }
        .note-teal {
            background: var(--teal-bg); border: 1px solid var(--teal);
            color: #9ff0e8;
        }

        @media (max-width: 600px) {
            .tabs { grid-template-columns: repeat(3, 1fr); }
            .workspace { grid-template-columns: 1fr; }
            .row4 { grid-template-columns: 1fr 1fr; }
            .action-row { grid-template-columns: 1fr; }
            /* Conversor: apila en móvil */
            .conv-grid { grid-template-columns: 1fr; }
            .conv-arrow { display: none; }
            /* DMS group más manejable */
            .dms-group input { font-size: 15px; } /* Permitido aquí pues no hay focus zoom en este tamaño de grupo */
            /* Cabecera: apila título y unidades si no caben */
            .app-header { flex-wrap: wrap; gap: 8px; }
        }

        /* iPhone SE y muy pequeños */
        @media (max-width: 380px) {
            .tabs { grid-template-columns: repeat(3, 1fr); }
            .row3 { grid-template-columns: 1fr 1fr; }
        }
    </style>
</head>
<body>

<!-- HEADER -->
<div class="app-header">
    <div class="app-title">
        <div class="app-title-icon">📐</div>
        <div>
            <h1>Estación Total</h1>
            <span>Nikon NPL-332 · Campo Digital</span>
        </div>
    </div>
    <div class="unit-switcher">
        <button class="unit-btn active" onclick="setUnidad('dms')" id="ubtn-dms">° ′ ″</button>
        <button class="unit-btn" onclick="setUnidad('deg')" id="ubtn-deg">Dec°</button>
        <button class="unit-btn" onclick="setUnidad('gon')" id="ubtn-gon">gon</button>
    </div>
</div>

<!-- STATUS BAR -->
<div class="status-bar" id="statusBar">
    <div class="status-dot inactive" id="statusDot"></div>
    <span id="statusText">Sin estación — Configura el estacionamiento primero.</span>
</div>

<!-- TABS -->
<div class="tabs">
    <button class="tab-btn active" onclick="tab('t-estacion',this)">🛰 Estación</button>
    <button class="tab-btn" onclick="tab('t-datos',this)">📥 Puntos</button>
    <button class="tab-btn" onclick="tab('t-rectas',this)">📏 Rectas</button>
    <button class="tab-btn" onclick="tab('t-areas',this)">🗺 Áreas</button>
    <button class="tab-btn" onclick="tab('t-conv',this)">🔄 Convertir</button>
    <button class="tab-btn" onclick="tab('t-gps',this)">🛰️ GPS+ET</button>
</div>

<!-- ═══════════════════════════════════════════
     PESTAÑA 1: ESTACIONAMIENTO
════════════════════════════════════════════ -->
<div id="t-estacion" class="tab-content active">
    <div class="card">
        <div class="card-title">📍 Configuración del Estacionamiento</div>

        <div style="margin-bottom:12px">
            <label>Método</label>
            <select id="metodoEstacion" onchange="conmutarCampos()">
                <option value="origen">Base Nueva (0,0,0 o Coordenadas GPS)</option>
                <option value="anterior">Estación en Punto Conocido</option>
            </select>
        </div>

        <!-- MODO BASE NUEVA -->
        <div id="bloque-origen">
            <div class="row3">
                <div><label>X · Este (m)</label><input type="number" id="baseX" value="0.000" step="0.001"></div>
                <div><label>Y · Norte (m)</label><input type="number" id="baseY" value="0.000" step="0.001"></div>
                <div><label>Z · Cota (m)</label><input type="number" id="baseZ" value="0.000" step="0.001"></div>
            </div>
        </div>

        <!-- MODO PUNTO CONOCIDO -->
        <div id="bloque-anterior" style="display:none">
            <div class="row">
                <div><label>Nº Punto Ocupado (ET)</label><input type="text" id="puntoOcupado" placeholder="Ej: 3"></div>
                <div><label>Nº Punto Referenciado</label><input type="text" id="puntoReferenciado" placeholder="Ej: 1"></div>
            </div>
            <div class="sep"></div>
            <div class="row">
                <div>
                    <label>Lectura Hz ET → Ref (<span class="unit-label-ang"></span>)</label>
                    <div id="inputHz-estacion"></div>
                </div>
                <div><label>Dist. Medida (m) — Opcional</label><input type="number" id="distanciaControl" placeholder="Para verificar" step="0.001"></div>
            </div>
        </div>

        <div class="sep"></div>
        <div class="row">
            <div><label>Alt. Instrumento HI (m)</label><input type="number" id="altAparato" value="1.500" step="0.001"></div>
            <div>
                <label>Azimut Inicial (<span class="unit-label-ang"></span>)</label>
                <div id="inputAzimut-estacion"></div>
            </div>
        </div>

        <button class="btn btn-teal" style="margin-top:14px" onclick="fijarEstacion()">📍 Validar Estacionamiento</button>
    </div>
</div>

<!-- ═══════════════════════════════════════════
     PESTAÑA 2: PUNTOS
════════════════════════════════════════════ -->
<div id="t-datos" class="tab-content">
    <div class="card" style="border-left: 3px solid var(--green);">
        <div class="card-title">
            📥 Entrada desde Estación Total
            <span class="badge" style="background:var(--green-bg);color:var(--green)">MEDIR</span>
        </div>

        <div class="row">
            <div><label>Nº Punto</label><input type="text" id="punto" value="1"></div>
            <div><label>Alt. Prisma AP (m)</label><input type="number" id="altPrisma" value="1.500" step="0.001"></div>
        </div>

        <div class="sep"></div>
        <div class="note note-teal">
            💡 <b>Nikon NPL-332</b> muestra los ángulos en <b>grados°minutos'segundos"</b> (DMS).<br>
            Selecciona <b>° ′ ″</b> arriba para introducirlos directamente sin convertir.
        </div>
        <div class="sep"></div>

        <div class="row" style="margin-top:4px">
            <div>
                <label>Ángulo Horizontal Hz (<span class="unit-label-ang"></span>)</label>
                <div id="inputHz-datos"></div>
            </div>
            <div>
                <label>Ángulo Vertical V (<span class="unit-label-ang"></span>)</label>
                <div id="inputV-datos"></div>
            </div>
        </div>

        <div class="row" style="margin-top:10px">
            <div><label>Distancia Inclinada Di (m)</label><input type="number" id="dist" placeholder="0.000" step="0.001" inputmode="decimal"></div>
            <div>
                <label>Código de Campo</label>
                <select id="codigoPunto">
                    <option value="Marco">Marco (Lindero)</option>
                    <option value="Intersección">Intersección</option>
                    <option value="Ref.">Ref. (Referencia)</option>
                    <option value="Estación">Estación</option>
                </select>
            </div>
        </div>

        <button class="btn btn-teal" style="margin-top:14px" onclick="registrarPunto()">💾 Calcular y Anotar Punto</button>
    </div>
</div>

<!-- ═══════════════════════════════════════════
     PESTAÑA 3: RECTAS
════════════════════════════════════════════ -->
<div id="t-rectas" class="tab-content">
    <div class="card" style="border-left: 3px solid var(--purple);">
        <div class="card-title">📏 Herramientas de Rectas y Tramos</div>
        <div class="row">
            <div><label>Punto Inicial A</label><input type="text" id="rectaP1" placeholder="Ej: 1"></div>
            <div><label>Punto Final B</label><input type="text" id="rectaP2" placeholder="Ej: 2"></div>
        </div>
        <div class="row" style="margin-top:10px">
            <div>
                <label>Opción A — Cada X metros</label>
                <div style="display:flex;gap:6px;margin-top:4px">
                    <input type="number" id="distFija" placeholder="Metros" step="0.01">
                    <button class="btn btn-purple btn-sm" onclick="generarCadaX()">Generar</button>
                </div>
            </div>
            <div>
                <label>Opción B — Dividir en N partes</label>
                <div style="display:flex;gap:6px;margin-top:4px">
                    <input type="number" id="numPartes" placeholder="Partes" step="1">
                    <button class="btn btn-purple btn-sm" onclick="dividirEnN()">Dividir</button>
                </div>
            </div>
        </div>

        <div class="sep"></div>
        <div class="section-label">Opción C — Prolongar alineación</div>
        <div class="row3">
            <div><label>Punto Base</label><input type="text" id="proPBase" placeholder="Ej: 1"></div>
            <div><label>Punto Dirección</label><input type="text" id="proPDir" placeholder="Ej: 2"></div>
            <div>
                <label>Sentido</label>
                <select id="proSentido">
                    <option value="adelante">Hacia Adelante</option>
                    <option value="atras">Hacia Atrás</option>
                </select>
            </div>
        </div>
        <div style="display:flex;gap:8px;margin-top:8px">
            <input type="number" id="proDistancia" placeholder="Distancia en metros" step="0.01" style="flex:1">
            <button class="btn btn-purple btn-sm" onclick="prolongar()">Proyectar</button>
        </div>
        <div id="res-recta" class="result-box result-purple"></div>
    </div>

    <div class="card" style="border-left: 3px solid var(--red);">
        <div class="card-title">✖️ Intersección de 2 Líneas</div>
        <div class="row4">
            <div><label>L1 Inicio</label><input type="text" id="intA" placeholder="P1"></div>
            <div><label>L1 Fin</label><input type="text" id="intB" placeholder="P2"></div>
            <div><label>L2 Inicio</label><input type="text" id="intC" placeholder="P3"></div>
            <div><label>L2 Fin</label><input type="text" id="intD" placeholder="P4"></div>
        </div>
        <button class="btn btn-red" onclick="interseccion()">Calcular Punto de Cruce</button>
        <div id="res-int" class="result-box result-red"></div>
    </div>
</div>

<!-- ═══════════════════════════════════════════
     PESTAÑA 4: ÁREAS
════════════════════════════════════════════ -->
<div id="t-areas" class="tab-content">
    <div class="card" style="border-left: 3px solid var(--amber);">
        <div class="card-title">🗺 Cálculo de Superficie de Polígono</div>
        <label>Secuencia ordenada de vértices (separados por coma)</label>
        <input type="text" id="secuenciaPuntos" placeholder="Ej: 1, 2, 3, 4" style="margin-top:6px">
        <div class="note" style="margin-top:10px">
            El polígono se cerrará automáticamente. Introduce los puntos en el orden en que los tomaste (sentido horario o antihorario).
        </div>
        <button class="btn btn-amber" onclick="calcularArea()">📐 Calcular Superficie y Perímetro</button>
        <div id="res-area" class="result-box result-amber"></div>
    </div>
</div>

<!-- ═══════════════════════════════════════════
     PESTAÑA 5: CONVERSOR DE ÁNGULOS
════════════════════════════════════════════ -->
<div id="t-conv" class="tab-content">
    <div class="card">
        <div class="card-title">🔄 Conversor de Unidades Angulares</div>

        <div class="section-label">Entrada DMS (Grados° Minutos′ Segundos″) → Decimal / Gon</div>
        <div class="row3" style="margin-top:6px">
            <div><label>Grados (°)</label><input type="number" id="cv-d" placeholder="332" onchange="convertirDMSaDeg()"></div>
            <div><label>Minutos (′)</label><input type="number" id="cv-m" placeholder="23" min="0" max="59" onchange="convertirDMSaDeg()"></div>
            <div><label>Segundos (″)</label><input type="number" id="cv-s" placeholder="47" min="0" max="59" step="0.1" onchange="convertirDMSaDeg()"></div>
        </div>
        <div id="res-dms-conv" class="result-box result-teal" style="display:block; margin-top:8px">
            Introduce los valores y se convertirán automáticamente.
        </div>

        <div class="sep"></div>

        <div class="section-label">Entrada Decimal (°) → DMS / Gon</div>
        <div style="margin-top:6px">
            <label>Ángulo decimal (°)</label>
            <input type="number" id="cv-dec" placeholder="332.3964" step="0.0001" onchange="convertirDecADMS()">
        </div>
        <div id="res-dec-conv" class="result-box result-teal" style="display:block; margin-top:8px">
            Introduce un ángulo decimal y se convertirá.
        </div>

        <div class="sep"></div>

        <div class="section-label">Entrada Gon (g) → DMS / Decimal</div>
        <div style="margin-top:6px">
            <label>Ángulo en Gon (g)</label>
            <input type="number" id="cv-gon" placeholder="369.3386" step="0.0001" onchange="convertirGonADeg()">
        </div>
        <div id="res-gon-conv" class="result-box result-teal" style="display:block; margin-top:8px">
            Introduce un valor en gon y se convertirá.
        </div>
    </div>

    <div class="card">
        <div class="card-title">📖 Referencia rápida — Ángulos NPL-332</div>
        <div style="font-size:0.82em;color:var(--text2);line-height:2;font-family:var(--mono)">
            <div><b style="color:var(--teal)">AH  332°23'47"</b> → Ángulo Horizontal (lectura del limbo)</div>
            <div><b style="color:var(--teal)">AV   90°00'00"</b> → Ángulo Vertical (90° = horizontal exacto)</div>
            <div><b style="color:var(--teal)">AV  &lt; 90°</b> → Telescopio mirando hacia arriba</div>
            <div><b style="color:var(--teal)">AV  &gt; 90°</b> → Telescopio mirando hacia abajo</div>
            <div style="margin-top:8px"><b style="color:var(--amber)">Conversión DMS → Decimal:</b></div>
            <div>332°23'47" = 332 + 23/60 + 47/3600 = <b style="color:var(--amber)">332.3964°</b></div>
            <div style="margin-top:8px"><b style="color:var(--purple)">Conversión Decimal → Gon:</b></div>
            <div>332.3964° × (400/360) = <b style="color:var(--purple)">369.3293 gon</b></div>
        </div>
    </div>
</div>

<!-- ═══════════════════════════════════════════
     PESTAÑA 6: GPS + ESTACIÓN TOTAL (SIN GEORREFERENCIAR)
════════════════════════════════════════════ -->
<div id="t-gps" class="tab-content">
    <div class="card" style="border-left: 3px solid var(--blue);">
        <div class="card-title">
            🛰️ Calibración GPS + Estación Total
            <span class="badge" style="background:var(--blue-bg);color:var(--blue)">ORIENTAR</span>
        </div>
        <div class="note note-teal">
            💡 Mide con la estación total <b>2 o 3 puntos</b> (Hz, V, Di) y toma sus coordenadas reales con el GPS (UTM huso 29N). Cuantos más puntos y más separados entre sí, más fiable será la orientación. La app calcula la posición real de la estación y su azimut, muestra el error de cierre de cada punto para que puedas juzgar la calidad, y a partir de ahí puedes replantear cualquier coordenada UTM sin volver a usar el GPS.<br><br>
            ⚠️ No toques el círculo horizontal (el 0 de referencia) entre estos puntos y el replanteo posterior — tiene que ser la misma puesta en estación.<br>
            ⚠️ Un GPS de mano típico tiene ±3-5 m de error. Con puntos muy próximos entre sí ese error se traduce en un azimut muy torcido: separa los puntos lo máximo posible (idealmente &gt;30-50 m entre ellos).
        </div>

        <div class="sep"></div>
        <label>Alt. Instrumento HI (m)</label>
        <input type="number" id="gpsAltInst" value="1.500" step="0.001">

        <div class="sep"></div>
        <div class="section-label">📍 Punto GPS 1</div>
        <div class="row">
            <div><label>Nombre (opcional, para guardarlo)</label><input type="text" id="gps1-nombre" placeholder="Ej: GPS1"></div>
            <div><label>Alt. Prisma AP (m)</label><input type="number" id="gps1-ap" value="1.500" step="0.001"></div>
        </div>
        <div class="row" style="margin-top:8px">
            <div><label>Hz (<span class="unit-label-ang"></span>)</label><div id="inputHz-gps1"></div></div>
            <div><label>V (<span class="unit-label-ang"></span>)</label><div id="inputV-gps1"></div></div>
        </div>
        <div style="margin-top:8px"><label>Distancia Inclinada Di (m)</label><input type="number" id="gps1-di" step="0.001" placeholder="0.000"></div>
        <div class="row3" style="margin-top:8px">
            <div><label>X UTM (m)</label><input type="number" id="gps1-x" step="0.001" placeholder="Este"></div>
            <div><label>Y UTM (m)</label><input type="number" id="gps1-y" step="0.001" placeholder="Norte"></div>
            <div><label>Z (m)</label><input type="number" id="gps1-z" step="0.001" placeholder="Cota"></div>
        </div>

        <div class="sep"></div>
        <div class="section-label">📍 Punto GPS 2</div>
        <div class="row">
            <div><label>Nombre (opcional, para guardarlo)</label><input type="text" id="gps2-nombre" placeholder="Ej: GPS2"></div>
            <div><label>Alt. Prisma AP (m)</label><input type="number" id="gps2-ap" value="1.500" step="0.001"></div>
        </div>
        <div class="row" style="margin-top:8px">
            <div><label>Hz (<span class="unit-label-ang"></span>)</label><div id="inputHz-gps2"></div></div>
            <div><label>V (<span class="unit-label-ang"></span>)</label><div id="inputV-gps2"></div></div>
        </div>
        <div style="margin-top:8px"><label>Distancia Inclinada Di (m)</label><input type="number" id="gps2-di" step="0.001" placeholder="0.000"></div>
        <div class="row3" style="margin-top:8px">
            <div><label>X UTM (m)</label><input type="number" id="gps2-x" step="0.001" placeholder="Este"></div>
            <div><label>Y UTM (m)</label><input type="number" id="gps2-y" step="0.001" placeholder="Norte"></div>
            <div><label>Z (m)</label><input type="number" id="gps2-z" step="0.001" placeholder="Cota"></div>
        </div>

        <div class="sep"></div>
        <div class="section-label">
            📍 Punto GPS 3 <span style="color:var(--text2);text-transform:none;font-weight:600">(opcional, recomendado para verificar)</span>
            <label style="display:inline-flex;align-items:center;gap:5px;margin-left:8px;text-transform:none;font-weight:600;color:var(--text2)">
                <input type="checkbox" id="chkGps3" onchange="toggleGps3()" style="width:auto"> Añadir
            </label>
        </div>
        <div id="bloque-gps3" style="display:none">
            <div class="row">
                <div><label>Nombre (opcional, para guardarlo)</label><input type="text" id="gps3-nombre" placeholder="Ej: GPS3"></div>
                <div><label>Alt. Prisma AP (m)</label><input type="number" id="gps3-ap" value="1.500" step="0.001"></div>
            </div>
            <div class="row" style="margin-top:8px">
                <div><label>Hz (<span class="unit-label-ang"></span>)</label><div id="inputHz-gps3"></div></div>
                <div><label>V (<span class="unit-label-ang"></span>)</label><div id="inputV-gps3"></div></div>
            </div>
            <div style="margin-top:8px"><label>Distancia Inclinada Di (m)</label><input type="number" id="gps3-di" step="0.001" placeholder="0.000"></div>
            <div class="row3" style="margin-top:8px">
                <div><label>X UTM (m)</label><input type="number" id="gps3-x" step="0.001" placeholder="Este"></div>
                <div><label>Y UTM (m)</label><input type="number" id="gps3-y" step="0.001" placeholder="Norte"></div>
                <div><label>Z (m)</label><input type="number" id="gps3-z" step="0.001" placeholder="Cota"></div>
            </div>
        </div>

        <button class="btn btn-blue" style="margin-top:14px" onclick="calcularOrientacionGPS()">📐 Calcular Orientación</button>
        <div id="res-gps-orient" class="result-box result-blue"></div>
        <button class="btn btn-teal" id="btnAplicarGPS" style="display:none" onclick="aplicarEstacionGPS()">✅ Aplicar como Estación Activa</button>
    </div>

    <div class="card" style="border-left: 3px solid var(--green);">
        <div class="card-title">
            🎯 Replantear por Coordenada GPS
            <span class="badge" style="background:var(--green-bg);color:var(--green)">SIN GPS EN CAMPO</span>
        </div>
        <div class="note">Con la estación ya orientada (arriba ⤴), introduce la coordenada UTM real del punto que quieres materializar y obtén el giro (Hz) y la distancia (Dh) para llevarlos directamente a la estación total.</div>

        <div class="row" style="margin-top:10px">
            <div><label>Nombre del Punto</label><input type="text" id="gpsRepNombre" placeholder="Ej: Vertice_5"></div>
            <div>
                <label>Código</label>
                <select id="gpsRepCodigo">
                    <option value="Marco">Marco (Lindero)</option>
                    <option value="Intersección">Intersección</option>
                    <option value="Ref.">Ref. (Referencia)</option>
                </select>
            </div>
        </div>
        <div class="row" style="margin-top:8px">
            <div><label>X UTM (m)</label><input type="number" id="gpsRepX" step="0.001" placeholder="Este"></div>
            <div><label>Y UTM (m)</label><input type="number" id="gpsRepY" step="0.001" placeholder="Norte"></div>
        </div>
        <div style="margin-top:8px"><label>Z (m) — opcional</label><input type="number" id="gpsRepZ" step="0.001" placeholder="Cota"></div>

        <button class="btn btn-green" style="margin-top:14px" onclick="replantearPorGPS()">🎯 Calcular Hz / Dh</button>
        <div id="res-gps-replanteo" class="result-box result-green"></div>
    </div>
</div>

<!-- ═══════════════════════════════════════════
     BOTONES GLOBALES
════════════════════════════════════════════ -->
<div class="action-row" style="margin-top:12px">
    <button class="btn btn-blue" onclick="descargarCSV()">💾 Exportar CSV</button>
    <button class="btn btn-ghost" onclick="descargarDXF()">📐 Exportar DXF</button>
    <button class="btn btn-red" style="opacity:0.7" onclick="borrarTodo()">🗑 Reset</button>
</div>

<!-- ═══════════════════════════════════════════
     WORKSPACE INFERIOR
════════════════════════════════════════════ -->
<div class="workspace">
    <div class="panel">
        <div class="panel-title">📋 Registro de Puntos</div>
        <div id="listaPuntos" class="panel-lista puntos-container"></div>
    </div>
    <div class="panel">
        <div class="panel-title">🗺 Croquis</div>
        <div class="canvas-wrap">
            <canvas id="mapaCanvas" width="300" height="280"></canvas>
            <div class="zoom-controls">
                <button class="zoom-btn" onclick="zoomCanvas(1.3)">+</button>
                <button class="zoom-btn" onclick="zoomCanvas(1/1.3)">−</button>
                <button class="zoom-btn" onclick="resetZoomCanvas()" title="Centrar">⤾</button>
            </div>
            <div class="zoom-level" id="zoomLevel">100%</div>
        </div>
        <div class="layer-controls">
            <label><input type="checkbox" id="chkLineas" checked onchange="dibujar()"> Linderos</label>
            <label><input type="checkbox" id="chkTextos" checked onchange="dibujar()"> Nombres</label>
            <button class="btn btn-ghost btn-sm" onclick="resetZoomCanvas()">↺ Centrar</button>
        </div>
    </div>
</div>

<script>
// ══════════════════════════════════════════════════════
//  ESTADO GLOBAL
// ══════════════════════════════════════════════════════
let puntos = {};
let Estacion = { x: 0, y: 0, z: 0, altInst: 1.5, azimut: 0, id: "0", activa: false };
let unidad = 'dms'; // 'dms' | 'deg' | 'gon'
let cntCruces = 1, cntProlongaciones = 1;
let gpsCalib = null; // resultado pendiente de calcularOrientacionGPS(), a la espera de aplicarEstacionGPS()

// ══════════════════════════════════════════════════════
//  SISTEMA DE UNIDADES
// ══════════════════════════════════════════════════════
function setUnidad(u) {
    unidad = u;
    ['dms','deg','gon'].forEach(id => {
        document.getElementById('ubtn-'+id).classList.toggle('active', id === u);
    });
    renderAngInputs();
    document.querySelectorAll('.unit-label-ang').forEach(el => {
        el.textContent = u === 'dms' ? '° ′ ″' : u === 'gon' ? 'gon' : '°';
    });
}

// Convierte el valor en la unidad actual a grados decimales internos
function toDecimalDeg(rawOrObj) {
    if (unidad === 'dms') {
        const g = parseFloat(rawOrObj.g) || 0;
        const m = parseFloat(rawOrObj.m) || 0;
        const s = parseFloat(rawOrObj.s) || 0;
        return g + m/60 + s/3600;
    } else if (unidad === 'gon') {
        return (parseFloat(rawOrObj) || 0) * (360/400);
    } else {
        return parseFloat(rawOrObj) || 0;
    }
}

function degToDisplay(deg) {
    if (unidad === 'dms') return decToDMS(deg);
    if (unidad === 'gon') return (deg * 400/360).toFixed(4) + ' gon';
    return deg.toFixed(4) + '°';
}

function decToDMS(deg) {
    const d = Math.floor(Math.abs(deg));
    const m = Math.floor((Math.abs(deg) - d) * 60);
    const s = ((Math.abs(deg) - d) * 60 - m) * 60;
    const sign = deg < 0 ? '-' : '';
    return `${sign}${d}° ${m}′ ${s.toFixed(1)}″`;
}

// ══════════════════════════════════════════════════════
//  RENDERIZADO DE INPUTS DE ÁNGULO
// ══════════════════════════════════════════════════════
const angInputDefs = [
    { id: 'inputHz-estacion', key: 'est-hz', label: 'Hz Estación', default: { g:0,m:0,s:0, dec:0, gon:0 } },
    { id: 'inputAzimut-estacion', key: 'est-az', label: 'Azimut', default: { g:0,m:0,s:0, dec:0, gon:0 } },
    { id: 'inputHz-datos', key: 'dat-hz', label: 'Hz', default: { g:0,m:0,s:0, dec:0, gon:0 } },
    { id: 'inputV-datos', key: 'dat-v', label: 'V', default: { g:90,m:0,s:0, dec:90, gon:100 } },
    { id: 'inputHz-gps1', key: 'gps1-hz', label: 'Hz P1', default: { g:0,m:0,s:0, dec:0, gon:0 } },
    { id: 'inputV-gps1', key: 'gps1-v', label: 'V P1', default: { g:90,m:0,s:0, dec:90, gon:100 } },
    { id: 'inputHz-gps2', key: 'gps2-hz', label: 'Hz P2', default: { g:0,m:0,s:0, dec:0, gon:0 } },
    { id: 'inputV-gps2', key: 'gps2-v', label: 'V P2', default: { g:90,m:0,s:0, dec:90, gon:100 } },
    { id: 'inputHz-gps3', key: 'gps3-hz', label: 'Hz P3', default: { g:0,m:0,s:0, dec:0, gon:0 } },
    { id: 'inputV-gps3', key: 'gps3-v', label: 'V P3', default: { g:90,m:0,s:0, dec:90, gon:100 } },
];

function renderAngInputs() {
    angInputDefs.forEach(def => {
        const el = document.getElementById(def.id);
        if (!el) return;
        if (unidad === 'dms') {
            el.innerHTML = `
                <div class="dms-group">
                    <input type="number" id="${def.key}-g" placeholder="°" value="${def.default.g}" min="0" max="359" inputmode="decimal" oninput="updateDMSResult('${def.key}')">
                    <span class="dms-sep">°</span>
                    <input type="number" id="${def.key}-m" placeholder="′" value="${def.default.m}" min="0" max="59" inputmode="decimal" oninput="updateDMSResult('${def.key}')">
                    <span class="dms-sep">′</span>
                    <input type="number" id="${def.key}-s" placeholder="″" value="${def.default.s}" min="0" max="59.9" step="0.1" inputmode="decimal" oninput="updateDMSResult('${def.key}')">
                    <span class="dms-sep">″</span>
                </div>
                <div class="dms-result" id="${def.key}-res">= ${def.default.dec.toFixed(4)}°&nbsp;&nbsp;|&nbsp;&nbsp;${(def.default.dec*400/360).toFixed(4)} gon</div>`;
        } else if (unidad === 'gon') {
            el.innerHTML = `<input type="number" id="${def.key}-gon" value="${def.default.gon}" step="0.0001" placeholder="gon" inputmode="decimal">`;
        } else {
            el.innerHTML = `<input type="number" id="${def.key}-dec" value="${def.default.dec}" step="0.0001" placeholder="°" inputmode="decimal">`;
        }
    });
}

function updateDMSResult(key) {
    const g = parseFloat(document.getElementById(key+'-g')?.value) || 0;
    const m = parseFloat(document.getElementById(key+'-m')?.value) || 0;
    const s = parseFloat(document.getElementById(key+'-s')?.value) || 0;
    const dec = g + m/60 + s/3600;
    const gon = dec * 400/360;
    const el = document.getElementById(key+'-res');
    if (el) el.textContent = `= ${dec.toFixed(4)}°  |  ${gon.toFixed(4)} gon`;
}

function getAngValue(key) {
    if (unidad === 'dms') {
        return toDecimalDeg({
            g: document.getElementById(key+'-g')?.value || 0,
            m: document.getElementById(key+'-m')?.value || 0,
            s: document.getElementById(key+'-s')?.value || 0
        });
    } else if (unidad === 'gon') {
        return toDecimalDeg(document.getElementById(key+'-gon')?.value || 0);
    } else {
        return toDecimalDeg(document.getElementById(key+'-dec')?.value || 0);
    }
}

// ══════════════════════════════════════════════════════
//  TABS
// ══════════════════════════════════════════════════════
function tab(id, btn) {
    document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    btn.classList.add('active');
    if (id === 't-datos' || id === 't-estacion') dibujar();
}

function conmutarCampos() {
    const m = document.getElementById('metodoEstacion').value;
    document.getElementById('bloque-origen').style.display = m === 'origen' ? 'block' : 'none';
    document.getElementById('bloque-anterior').style.display = m === 'anterior' ? 'block' : 'none';
}

function toggleGps3() {
    document.getElementById('bloque-gps3').style.display = document.getElementById('chkGps3').checked ? 'block' : 'none';
}

// ══════════════════════════════════════════════════════
//  ESTACIONAMIENTO
// ══════════════════════════════════════════════════════
function fijarEstacion() {
    const metodo = document.getElementById('metodoEstacion').value;
    Estacion.altInst = parseFloat(document.getElementById('altAparato').value) || 0;

    if (metodo === 'origen') {
        Estacion.x = parseFloat(document.getElementById('baseX').value) || 0;
        Estacion.y = parseFloat(document.getElementById('baseY').value) || 0;
        Estacion.z = parseFloat(document.getElementById('baseZ').value) || 0;
        Estacion.azimut = getAngValue('est-az');
        Estacion.id = "0";
        puntos["0"] = { x: Estacion.x, y: Estacion.y, z: Estacion.z,
            hzReplanteo: "0.0000", dhReplanteo: "0.000", codigo: "Estación", orden: Date.now() };
    } else {
        const pOc = document.getElementById('puntoOcupado').value.trim();
        const pRef = document.getElementById('puntoReferenciado').value.trim();
        const lectHz = getAngValue('est-hz');
        const distCtrl = parseFloat(document.getElementById('distanciaControl').value);

        if (!puntos[pOc] || !puntos[pRef]) { alert("Los puntos indicados no existen en el registro."); return; }

        const dx = puntos[pRef].x - puntos[pOc].x;
        const dy = puntos[pRef].y - puntos[pOc].y;
        const distTeo = Math.sqrt(dx*dx + dy*dy);

        if (!isNaN(distCtrl) && Math.abs(distTeo - distCtrl) > 0.03) {
            if (!confirm(`⚠️ La distancia medida varía ${Math.abs(distTeo-distCtrl).toFixed(3)} m de la teórica (${distTeo.toFixed(3)} m). ¿Continuar?`)) return;
        }

        let azimutReal = Math.atan2(dx, dy) * (180/Math.PI);
        if (azimutReal < 0) azimutReal += 360;
        let azimutCalculado = azimutReal - lectHz;
        if (azimutCalculado < 0) azimutCalculado += 360;

        Estacion.x = puntos[pOc].x; Estacion.y = puntos[pOc].y; Estacion.z = puntos[pOc].z;
        Estacion.azimut = azimutCalculado; Estacion.id = pOc;
        puntos[pOc].codigo = "Estación";
    }

    Estacion.activa = true;
    guardar(); actualizarStatus(); actualizarLista();
    alert("✅ Estación configurada. Pasa a la pestaña 'Puntos' para medir.");
}

function actualizarStatus() {
    const dot = document.getElementById('statusDot');
    const txt = document.getElementById('statusText');
    if (Estacion.activa) {
        dot.className = 'status-dot active';
        const az = degToDisplay(Estacion.azimut);
        txt.innerHTML = `<b>Estación activa</b> · Pt ${Estacion.id} | X:${Estacion.x.toFixed(3)} Y:${Estacion.y.toFixed(3)} Z:${Estacion.z.toFixed(3)} | HI:${Estacion.altInst.toFixed(3)}m | Az:${az}`;
    } else {
        dot.className = 'status-dot inactive';
        txt.textContent = 'Sin estación — Configura el estacionamiento primero.';
    }
}

// ══════════════════════════════════════════════════════
//  REGISTRAR PUNTO
// ══════════════════════════════════════════════════════
function registrarPunto() {
    if (!Estacion.activa) { alert("Primero valida la estación."); return; }
    const pt = document.getElementById('punto').value.trim();
    const hz_deg = getAngValue('dat-hz');
    const v_deg = getAngValue('dat-v');
    const di = parseFloat(document.getElementById('dist').value);
    const ap = parseFloat(document.getElementById('altPrisma').value);
    const cod = document.getElementById('codigoPunto').value;

    if (!pt || isNaN(hz_deg) || isNaN(v_deg) || isNaN(di) || isNaN(ap)) { alert("Completa todos los datos."); return; }

    const anguloFinal = (hz_deg + Estacion.azimut) % 360;
    const hzRad = anguloFinal * (Math.PI/180);
    const vRad = v_deg * (Math.PI/180);

    const dh = di * Math.sin(vRad);
    const x = Estacion.x + dh * Math.sin(hzRad);
    const y = Estacion.y + dh * Math.cos(hzRad);
    const z = Estacion.z + Estacion.altInst + (di * Math.cos(vRad)) - ap;

    puntos[pt] = { x, y, z,
        hzReplanteo: hz_deg.toFixed(4),
        dhReplanteo: dh.toFixed(3),
        codigo: cod, orden: Date.now() };

    guardar(); actualizarLista();
    if (!isNaN(pt)) document.getElementById('punto').value = parseInt(pt)+1;
    document.getElementById('dist').value = '';
    document.getElementById('codigoPunto').value = 'Marco';
    // Limpiar Hz
    if (unidad === 'dms') {
        ['dat-hz-g','dat-hz-m','dat-hz-s'].forEach(id => { const el = document.getElementById(id); if(el) el.value=''; });
        const r = document.getElementById('dat-hz-res'); if(r) r.textContent = '= 0.0000°  |  0.0000 gon';
    } else if (unidad === 'gon') {
        const el = document.getElementById('dat-hz-gon'); if(el) el.value='';
    } else {
        const el = document.getElementById('dat-hz-dec'); if(el) el.value='';
    }
    document.getElementById('dist').focus();
}

// ══════════════════════════════════════════════════════
//  CALCULAR REPLANTEO
// ══════════════════════════════════════════════════════
function calcularReplanteo(x, y) {
    const dx = x - Estacion.x, dy = y - Estacion.y;
    const dh = Math.sqrt(dx*dx + dy*dy);
    let ang = Math.atan2(dx, dy) * (180/Math.PI);
    let hz = ang - Estacion.azimut;
    if (hz < 0) hz += 360;
    return { hz: (hz % 360).toFixed(4), dh: dh.toFixed(3) };
}

// ══════════════════════════════════════════════════════
//  GPS + ESTACIÓN TOTAL (calibración sin georreferenciar)
//  Ajuste por mínimos cuadrados (rotación + traslación) con
//  2 o 3 puntos de apoyo, más error de cierre por punto.
// ══════════════════════════════════════════════════════
function leerPuntoGPS(n) {
    const hz = getAngValue(`gps${n}-hz`), v = getAngValue(`gps${n}-v`);
    const di = parseFloat(document.getElementById(`gps${n}-di`).value);
    const ap = parseFloat(document.getElementById(`gps${n}-ap`).value);
    const x = parseFloat(document.getElementById(`gps${n}-x`).value);
    const y = parseFloat(document.getElementById(`gps${n}-y`).value);
    const z = parseFloat(document.getElementById(`gps${n}-z`).value);
    const nombre = document.getElementById(`gps${n}-nombre`).value.trim();
    if ([hz,v,di,ap,x,y,z].some(val => isNaN(val))) return null;
    return { n, hz, v, di, ap, x, y, z, nombre };
}

function calcularOrientacionGPS() {
    const altInst = parseFloat(document.getElementById('gpsAltInst').value);
    if (isNaN(altInst)) { alert("Indica la altura de instrumento."); return; }

    const p1 = leerPuntoGPS(1);
    const p2 = leerPuntoGPS(2);
    if (!p1 || !p2) { alert("Completa todos los datos de los puntos GPS 1 y 2 (lecturas de estación y coordenadas) y la altura de instrumento."); return; }

    const usarP3 = document.getElementById('chkGps3').checked;
    let p3 = null;
    if (usarP3) {
        p3 = leerPuntoGPS(3);
        if (!p3) { alert("Has activado el Punto GPS 3 pero le faltan datos. Complétalo o desmárcalo."); return; }
    }
    const pts = p3 ? [p1,p2,p3] : [p1,p2];

    // Aviso si algún par de puntos está demasiado próximo (el error del GPS de mano
    // se traduce directamente en error de azimut cuando la base es corta)
    for (let i=0; i<pts.length; i++) {
        for (let j=i+1; j<pts.length; j++) {
            const dsep = Math.hypot(pts[j].x-pts[i].x, pts[j].y-pts[i].y);
            if (dsep < 15) {
                if (!confirm(`⚠️ Los puntos GPS ${pts[i].n} y ${pts[j].n} están a solo ${dsep.toFixed(1)} m. Con la precisión típica de un GPS de mano (±3-5 m) esto puede torcer bastante el azimut calculado. ¿Continuar de todas formas?`)) return;
            }
        }
    }

    // Coordenadas horizontales "locales" de cada punto vistas desde la estación,
    // usando la lectura Hz en bruto como si fuera el acimut (aún sin corregir).
    pts.forEach(p => {
        const hzr = p.hz*Math.PI/180, vr = p.v*Math.PI/180;
        p.dh = p.di*Math.sin(vr);
        p.lx = p.dh*Math.sin(hzr);
        p.ly = p.dh*Math.cos(hzr);
        p.hzr = hzr; p.vr = vr;
    });

    // Ángulo de rotación (theta) que alinea el sistema local (bruto) con el
    // sistema real (UTM). Con 2 puntos se toma directamente de su vector;
    // con 3 puntos se promedia (vectorialmente) sobre todos los pares para
    // suavizar el ruido del GPS.
    let sumSin = 0, sumCos = 0, nPares = 0;
    for (let i=0; i<pts.length; i++) {
        for (let j=i+1; j<pts.length; j++) {
            const dxL = pts[j].lx-pts[i].lx, dyL = pts[j].ly-pts[i].ly;
            const dxR = pts[j].x-pts[i].x,  dyR = pts[j].y-pts[i].y;
            const baseL = Math.hypot(dxL,dyL);
            if (baseL < 0.05) continue; // par degenerado, se ignora
            let azL = Math.atan2(dxL,dyL); 
            let azR = Math.atan2(dxR,dyR);
            const dTheta = azR - azL;
            // peso proporcional a la longitud de la base (bases cortas pesan menos)
            const w = Math.hypot(dxR,dyR);
            sumSin += Math.sin(dTheta)*w;
            sumCos += Math.cos(dTheta)*w;
            nPares++;
        }
    }
    if (nPares === 0) { alert("Los puntos GPS coinciden entre sí (distancia ~0). No se puede calcular una orientación."); return; }
    let theta = Math.atan2(sumSin, sumCos) * 180/Math.PI;
    theta = ((theta % 360) + 360) % 360;
    const thetaR = theta*Math.PI/180;

    // Posición de la estación deducida desde cada punto, y promedio
    let sx=0, sy=0, sz=0;
    pts.forEach(p => {
        p.xe = p.x - p.dh*Math.sin(p.hzr+thetaR);
        p.ye = p.y - p.dh*Math.cos(p.hzr+thetaR);
        p.ze = p.z - altInst - p.di*Math.cos(p.vr) + p.ap;
        sx += p.xe; sy += p.ye; sz += p.ze;
    });
    const xe = sx/pts.length, ye = sy/pts.length, ze = sz/pts.length;

    // Error de cierre por punto: cuánto se aparta la posición de estación
    // deducida desde ESE punto respecto a la posición media -> mide fiabilidad
    let errMax = 0;
    const lineas = pts.map(p => {
        const err = Math.hypot(p.xe-xe, p.ye-ye);
        errMax = Math.max(errMax, err);
        return `  · Pt${p.n}${p.nombre?(' ('+p.nombre+')'):''} → error cierre ${err.toFixed(3)} m`;
    });

    gpsCalib = {
        x: xe, y: ye, z: ze, azimut: theta, altInst,
        puntos: pts.map(p => ({ nombre: p.nombre, x: p.x, y: p.y, z: p.z }))
    };

    let calidad = '✅ Buena';
    if (errMax > 0.10) calidad = '⚠️ Regular';
    if (errMax > 0.30) calidad = '❌ Mala — revisa lecturas o separa más los puntos';

    showRes('res-gps-orient',
        `✅ Orientación calculada (${pts.length} puntos)\nEstación (real) → X:${xe.toFixed(3)}  Y:${ye.toFixed(3)}  Z:${ze.toFixed(3)}\nAzimut de la estación: ${degToDisplay(theta)}\n\nCalidad del ajuste: ${calidad} (error máx. ${errMax.toFixed(3)} m)\n${lineas.join('\n')}\n\nPulsa "Aplicar como Estación Activa" para usarla en toda la app.`);

    document.getElementById('btnAplicarGPS').style.display = 'block';
}

function aplicarEstacionGPS() {
    if (!gpsCalib) return;

    Estacion.x = gpsCalib.x; Estacion.y = gpsCalib.y; Estacion.z = gpsCalib.z;
    Estacion.azimut = gpsCalib.azimut; Estacion.altInst = gpsCalib.altInst;
    Estacion.id = "GPS"; Estacion.activa = true;

    // Registrar en el listado los puntos GPS a los que se les haya puesto nombre
    gpsCalib.puntos.forEach((p, idx) => {
        if (p.nombre) {
            const rep = calcularReplanteo(p.x, p.y);
            puntos[p.nombre] = { x:p.x, y:p.y, z:p.z, hzReplanteo:rep.hz, dhReplanteo:rep.dh, codigo:"Ref.", orden:Date.now()+idx };
        }
    });

    document.getElementById('altAparato').value = Estacion.altInst.toFixed(3);

    guardar(); actualizarStatus(); actualizarLista();
    alert("✅ Estación aplicada en coordenadas UTM reales. Ya puedes usar 'Puntos', 'Rectas' y 'Áreas' con coordenadas reales, o el bloque de abajo para replantear directamente por GPS.");
}

function replantearPorGPS() {
    if (!Estacion.activa) { alert("Primero calcula y aplica la orientación GPS (o valida un estacionamiento) arriba."); return; }

    const nombre = document.getElementById('gpsRepNombre').value.trim();
    const codigo = document.getElementById('gpsRepCodigo').value;
    const x = parseFloat(document.getElementById('gpsRepX').value);
    const y = parseFloat(document.getElementById('gpsRepY').value);
    const zRaw = document.getElementById('gpsRepZ').value;
    const z = zRaw === '' ? 0 : (parseFloat(zRaw) || 0);

    if (!nombre || isNaN(x) || isNaN(y)) { alert("Completa el nombre y las coordenadas X, Y."); return; }
    if (puntos[nombre] && !confirm(`Ya existe un punto "${nombre}". ¿Sobrescribirlo?`)) return;

    const rep = calcularReplanteo(x,y);
    puntos[nombre] = { x, y, z, hzReplanteo: rep.hz, dhReplanteo: rep.dh, codigo, orden: Date.now() };

    guardar(); actualizarLista();
    showRes('res-gps-replanteo', `🎯 ${nombre}\nGira Hz a ${degToDisplay(parseFloat(rep.hz))}\nMide Dh = ${rep.dh} m`);
}

// ══════════════════════════════════════════════════════
//  RECTAS
// ══════════════════════════════════════════════════════
function getPtsAB() {
    const p1 = document.getElementById('rectaP1').value.trim();
    const p2 = document.getElementById('rectaP2').value.trim();
    if (!puntos[p1] || !puntos[p2]) { alert("Puntos inválidos o no existen."); return null; }
    return { A: puntos[p1], B: puntos[p2], idA: p1, idB: p2 };
}

function generarCadaX() {
    const d = getPtsAB(); if (!d) return;
    const dist = parseFloat(document.getElementById('distFija').value);
    if (isNaN(dist) || dist <= 0) return;
    const dx = d.B.x-d.A.x, dy = d.B.y-d.A.y, dz = d.B.z-d.A.z;
    const total = Math.sqrt(dx*dx+dy*dy+dz*dz);
    const n = Math.floor(total/dist);
    for (let i=1; i<=n; i++) {
        const t = (dist*i)/total;
        const xi=d.A.x+dx*t, yi=d.A.y+dy*t, zi=d.A.z+dz*t;
        const rep = calcularReplanteo(xi,yi);
        puntos[`${d.idA}-${d.idB}_c${i}`] = {x:xi,y:yi,z:zi,hzReplanteo:rep.hz,dhReplanteo:rep.dh,codigo:"Intersección",orden:Date.now()};
    }
    guardar(); actualizarLista();
    showRes('res-recta', `✅ ${n} puntos generados cada ${dist}m entre ${d.idA} y ${d.idB}.`);
}

function dividirEnN() {
    const d = getPtsAB(); if (!d) return;
    const n = parseInt(document.getElementById('numPartes').value);
    if (isNaN(n) || n <= 1) return;
    const dx=d.B.x-d.A.x, dy=d.B.y-d.A.y, dz=d.B.z-d.A.z;
    for (let i=1; i<n; i++) {
        const t=i/n;
        const xi=d.A.x+dx*t, yi=d.A.y+dy*t, zi=d.A.z+dz*t;
        const rep=calcularReplanteo(xi,yi);
        puntos[`${d.idA}-${d.idB}_d${i}`] = {x:xi,y:yi,z:zi,hzReplanteo:rep.hz,dhReplanteo:rep.dh,codigo:"Intersección",orden:Date.now()};
    }
    guardar(); actualizarLista();
    showRes('res-recta', `✅ Segmento dividido en ${n} partes iguales.`);
}

function prolongar() {
    const idBase = document.getElementById('proPBase').value.trim();
    const idDir = document.getElementById('proPDir').value.trim();
    const dist = parseFloat(document.getElementById('proDistancia').value);
    const sentido = document.getElementById('proSentido').value;
    if (!puntos[idBase] || !puntos[idDir] || isNaN(dist)) { alert("Verifica los datos."); return; }
    const dx = puntos[idDir].x-puntos[idBase].x, dy = puntos[idDir].y-puntos[idBase].y;
    const segDist = Math.sqrt(dx*dx+dy*dy);
    if (segDist < 0.001) return;
    let vx = dx/segDist, vy = dy/segDist;
    if (sentido === 'atras') { vx=-vx; vy=-vy; }
    const xi = puntos[idBase].x + vx*dist, yi = puntos[idBase].y + vy*dist;
    const rep = calcularReplanteo(xi,yi);
    const nombre = `Pro_${cntProlongaciones}_${idBase}`;
    puntos[nombre] = {x:xi,y:yi,z:puntos[idBase].z,hzReplanteo:rep.hz,dhReplanteo:rep.dh,codigo:"Intersección",orden:Date.now()};
    cntProlongaciones++; guardar(); actualizarLista();
    showRes('res-recta', `🎯 ${nombre} → X:${xi.toFixed(3)} Y:${yi.toFixed(3)}\nGira a ${degToDisplay(parseFloat(rep.hz))} · Mide ${rep.dh} m`);
}

function interseccion() {
    const ids = ['intA','intB','intC','intD'].map(id => document.getElementById(id).value.trim());
    if (ids.some(id => !puntos[id])) { alert("Algún punto no existe."); return; }
    const [A,B,C,D] = ids.map(id => puntos[id]);
    const den = (A.x-B.x)*(C.y-D.y) - (A.y-B.y)*(C.x-D.x);
    if (Math.abs(den) < 0.00001) { alert("Las líneas son paralelas."); return; }
    const xi = ((A.x*B.y-A.y*B.x)*(C.x-D.x) - (A.x-B.x)*(C.x*D.y-C.y*D.x)) / den;
    const yi = ((A.x*B.y-A.y*B.x)*(C.y-D.y) - (A.y-B.y)*(C.x*D.y-C.y*D.x)) / den;
    const rep = calcularReplanteo(xi,yi);
    const nombre = `Cruce_${cntCruces}`;
    puntos[nombre] = {x:xi,y:yi,z:(A.z+B.z+C.z+D.z)/4,hzReplanteo:rep.hz,dhReplanteo:rep.dh,codigo:"Intersección",orden:Date.now()};
    cntCruces++; guardar(); actualizarLista();
    showRes('res-int', `🎯 ${nombre} → X:${xi.toFixed(3)} Y:${yi.toFixed(3)}\nGira a ${degToDisplay(parseFloat(rep.hz))} · Mide ${rep.dh} m`);
}

// ══════════════════════════════════════════════════════
//  ÁREAS
// ══════════════════════════════════════════════════════
function calcularArea() {
    const ids = document.getElementById('secuenciaPuntos').value.split(',').map(s=>s.trim());
    const verts = ids.map(id => puntos[id]).filter(Boolean);
    if (verts.length < 3) { alert("Mínimo 3 puntos válidos."); return; }
    let s1=0, s2=0, per=0;
    for (let i=0; i<verts.length; i++) {
        const j=(i+1)%verts.length;
        s1 += verts[i].x*verts[j].y; s2 += verts[i].y*verts[j].x;
        per += Math.sqrt((verts[j].x-verts[i].x)**2 + (verts[j].y-verts[i].y)**2);
    }
    const area = Math.abs(s1-s2)/2;
    showRes('res-area', `📐 Superficie: ${area.toFixed(2)} m²  (${(area/10000).toFixed(4)} ha)\n🏃 Perímetro: ${per.toFixed(2)} m`);
}

// ══════════════════════════════════════════════════════
//  CONVERSOR
// ══════════════════════════════════════════════════════
function convertirDMSaDeg() {
    const d = parseFloat(document.getElementById('cv-d').value)||0;
    const m = parseFloat(document.getElementById('cv-m').value)||0;
    const s = parseFloat(document.getElementById('cv-s').value)||0;
    const dec = d + m/60 + s/3600;
    const gon = dec * 400/360;
    const el = document.getElementById('res-dms-conv');
    el.style.display='block';
    el.innerHTML = `${d}° ${m}′ ${s}″<br><b>= ${dec.toFixed(6)}°</b>  (decimal)<br><b>= ${gon.toFixed(6)} gon</b>  (centesimal)`;
}

function convertirDecADMS() {
    const dec = parseFloat(document.getElementById('cv-dec').value)||0;
    const d = Math.floor(Math.abs(dec));
    const m = Math.floor((Math.abs(dec)-d)*60);
    const s = ((Math.abs(dec)-d)*60-m)*60;
    const gon = dec*400/360;
    const el = document.getElementById('res-dec-conv');
    el.style.display='block';
    el.innerHTML = `${dec.toFixed(6)}°<br><b>= ${d}° ${m}′ ${s.toFixed(4)}″</b>  (DMS)<br><b>= ${gon.toFixed(6)} gon</b>  (centesimal)`;
}

function convertirGonADeg() {
    const gon = parseFloat(document.getElementById('cv-gon').value)||0;
    const dec = gon * 360/400;
    const d = Math.floor(Math.abs(dec));
    const m = Math.floor((Math.abs(dec)-d)*60);
    const s = ((Math.abs(dec)-d)*60-m)*60;
    const el = document.getElementById('res-gon-conv');
    el.style.display='block';
    el.innerHTML = `${gon.toFixed(6)} gon<br><b>= ${dec.toFixed(6)}°</b>  (decimal)<br><b>= ${d}° ${m}′ ${s.toFixed(4)}″</b>  (DMS)`;
}

// ══════════════════════════════════════════════════════
//  UI HELPERS
// ══════════════════════════════════════════════════════
function showRes(id, txt) {
    const el = document.getElementById(id);
    el.style.display = 'block';
    el.innerHTML = txt.replace(/\n/g,'<br>');
}

// ══════════════════════════════════════════════════════
//  LISTADO DE PUNTOS
// ══════════════════════════════════════════════════════
const codColors = { 'Marco':'chip-marco','Intersección':'chip-inter','Ref.':'chip-ref','Estación':'chip-est' };

function actualizarLista() {
    const c = document.getElementById('listaPuntos');
    c.innerHTML = '';
    const keys = Object.keys(puntos).sort((a,b) => isNaN(a)||isNaN(b) ? a.localeCompare(b) : parseInt(a)-parseInt(b));
    keys.forEach(id => {
        const p = puntos[id];
        const isBase = (id === "0" || id === Estacion.id);
        const div = document.createElement('div');
        div.className = 'item-punto' + (isBase ? ' item-punto-base' : '');
        const cc = codColors[p.codigo] || 'chip-marco';
        div.innerHTML = `
            <button class="btn-del" onclick="borrarPunto('${id}')">✕</button>
            <span class="pt-name">Pt ${id}</span> <span class="chip ${cc}">${p.codigo||'Marco'}</span>
            <div class="pt-coords">X ${p.x.toFixed(3)} · Y ${p.y.toFixed(3)} · Z ${p.z.toFixed(3)}</div>
            <div class="pt-replanteo">↻ Hz ${p.hzReplanteo}° · Dh ${p.dhReplanteo} m</div>`;
        c.appendChild(div);
    });
    if (keys.length > 0) {
        let max = 0;
        for (const id in puntos) { if (!isNaN(id)) max = Math.max(max, parseInt(id)); }
        document.getElementById('punto').value = max+1;
    }
    dibujar();
}

function borrarPunto(id) {
    if (confirm(`¿Borrar el punto ${id}?`)) { delete puntos[id]; guardar(); actualizarLista(); }
}

// ══════════════════════════════════════════════════════
//  CROQUIS CANVAS — con zoom y desplazamiento (pan)
// ══════════════════════════════════════════════════════
let vista = { zoom: 1, panX: 0, panY: 0 }; // panX/panY en píxeles de pantalla

function zoomCanvas(factor) {
    vista.zoom = Math.min(20, Math.max(0.2, vista.zoom * factor));
    actualizarZoomLabel();
    dibujar();
}

function resetZoomCanvas() {
    vista.zoom = 1; vista.panX = 0; vista.panY = 0;
    actualizarZoomLabel();
    dibujar();
}

function actualizarZoomLabel() {
    const el = document.getElementById('zoomLevel');
    if (el) el.textContent = Math.round(vista.zoom*100) + '%';
}

function dibujar() {
    const canvas = document.getElementById('mapaCanvas');
    const ctx = canvas.getContext('2d');

    // Soporte Retina / HiDPI para iPhone
    const dpr = window.devicePixelRatio || 1;
    const rect = canvas.getBoundingClientRect();
    const displayW = rect.width || canvas.offsetWidth || 300;
    const displayH = rect.height || canvas.offsetHeight || 280;
    if (canvas.width !== Math.round(displayW * dpr) || canvas.height !== Math.round(displayH * dpr)) {
        canvas.width = Math.round(displayW * dpr);
        canvas.height = Math.round(displayH * dpr);
    }
    ctx.setTransform(dpr,0,0,dpr,0,0);
    const W = displayW, H = displayH;

    ctx.clearRect(0,0,W,H);
    const keys = Object.keys(puntos);
    if (keys.length === 0) return;

    let minX=Infinity,maxX=-Infinity,minY=Infinity,maxY=-Infinity;
    keys.forEach(id => {
        const p=puntos[id]; minX=Math.min(minX,p.x); maxX=Math.max(maxX,p.x);
        minY=Math.min(minY,p.y); maxY=Math.max(maxY,p.y);
    });
    const rng = Math.max(maxX-minX, maxY-minY, 1);
    const baseScale = (W-48)/rng;
    const scale = baseScale * vista.zoom;
    const ox = (W/2) - scale*(minX+maxX)/2 + vista.panX;
    const oy = (H/2) - scale*(minY+maxY)/2 - vista.panY;
    const cx = p => ox + p.x*scale;
    const cy = p => H - (oy + p.y*scale);

    // Grid lines
    ctx.strokeStyle = '#1a2332'; ctx.lineWidth = 1;
    for (let i=0; i<W; i+=30) { ctx.beginPath(); ctx.moveTo(i,0); ctx.lineTo(i,H); ctx.stroke(); }
    for (let i=0; i<H; i+=30) { ctx.beginPath(); ctx.moveTo(0,i); ctx.lineTo(W,i); ctx.stroke(); }

    const verLineas = document.getElementById('chkLineas').checked;
    const verTextos = document.getElementById('chkTextos').checked;

    if (verLineas) {
        const marcos = keys.filter(id=>puntos[id].codigo==='Marco').sort((a,b)=>puntos[a].orden-puntos[b].orden);
        if (marcos.length > 1) {
            ctx.beginPath(); ctx.strokeStyle='#00e5cc'; ctx.lineWidth=1.5; ctx.setLineDash([]);
            marcos.forEach((id,i) => { const p=puntos[id]; i===0?ctx.moveTo(cx(p),cy(p)):ctx.lineTo(cx(p),cy(p)); });
            ctx.stroke();
        }
    }

    keys.forEach(id => {
        const p=puntos[id]; const cod=p.codigo||'Marco';
        const x=cx(p), y=cy(p);
        if (x < -20 || x > W+20 || y < -20 || y > H+20) {
            // fuera de la vista actual: nada que dibujar (evita coste innecesario con mucho zoom)
        }
        ctx.beginPath();
        const r = Math.min(7, Math.max(2.5, 4*Math.sqrt(vista.zoom)));
        if (cod==='Estación') {
            ctx.strokeStyle='#58a6ff'; ctx.lineWidth=2;
            ctx.moveTo(x,y-r*1.75); ctx.lineTo(x-r*1.5,y+r*1.25); ctx.lineTo(x+r*1.5,y+r*1.25); ctx.closePath(); ctx.stroke();
        } else if (cod==='Marco') {
            ctx.fillStyle='#ef4444'; ctx.arc(x,y,r,0,Math.PI*2); ctx.fill();
        } else if (cod==='Ref.') {
            ctx.strokeStyle='#bc8cff'; ctx.lineWidth=1.8;
            ctx.moveTo(x-r*1.25,y); ctx.lineTo(x+r*1.25,y); ctx.moveTo(x,y-r*1.25); ctx.lineTo(x,y+r*1.25); ctx.stroke();
        } else {
            ctx.strokeStyle='#f0a500'; ctx.lineWidth=1.5;
            ctx.moveTo(x-r,y-r); ctx.lineTo(x+r,y+r); ctx.moveTo(x+r,y-r); ctx.lineTo(x-r,y+r); ctx.stroke();
        }
        if (verTextos) {
            ctx.fillStyle='#8b949e'; ctx.font=`bold ${Math.min(13,Math.max(9,9*Math.sqrt(vista.zoom)))}px JetBrains Mono, monospace`;
            ctx.fillText(id, x+r+2, y-2);
        }
    });
}

// ── Interacción táctil / ratón: pan y pinch-zoom sobre el croquis ──────
(function initCanvasInteraction() {
    const canvas = document.getElementById('mapaCanvas');
    if (!canvas) return;

    let dragging = false;
    let lastX = 0, lastY = 0;
    let pinchStartDist = 0, pinchStartZoom = 1;

    function dist(t1, t2) { return Math.hypot(t2.clientX-t1.clientX, t2.clientY-t1.clientY); }

    // Ratón (desktop / trackpad)
    canvas.addEventListener('mousedown', e => {
        dragging = true; lastX = e.clientX; lastY = e.clientY;
        canvas.classList.add('dragging');
    });
    window.addEventListener('mousemove', e => {
        if (!dragging) return;
        vista.panX += (e.clientX - lastX);
        vista.panY -= (e.clientY - lastY);
        lastX = e.clientX; lastY = e.clientY;
        dibujar();
    });
    window.addEventListener('mouseup', () => { dragging = false; canvas.classList.remove('dragging'); });

    canvas.addEventListener('wheel', e => {
        e.preventDefault();
        const factor = e.deltaY < 0 ? 1.12 : 1/1.12;
        vista.zoom = Math.min(20, Math.max(0.2, vista.zoom * factor));
        actualizarZoomLabel();
        dibujar();
    }, { passive:false });

    // Táctil (iPhone / Android): un dedo = pan, dos dedos = pinch zoom
    canvas.addEventListener('touchstart', e => {
        if (e.touches.length === 1) {
            dragging = true; lastX = e.touches[0].clientX; lastY = e.touches[0].clientY;
        } else if (e.touches.length === 2) {
            dragging = false;
            pinchStartDist = dist(e.touches[0], e.touches[1]);
            pinchStartZoom = vista.zoom;
        }
    }, { passive:true });

    canvas.addEventListener('touchmove', e => {
        if (e.touches.length === 1 && dragging) {
            e.preventDefault();
            const t = e.touches[0];
            vista.panX += (t.clientX - lastX);
            vista.panY -= (t.clientY - lastY);
            lastX = t.clientX; lastY = t.clientY;
            dibujar();
        } else if (e.touches.length === 2) {
            e.preventDefault();
            const d = dist(e.touches[0], e.touches[1]);
            if (pinchStartDist > 0) {
                vista.zoom = Math.min(20, Math.max(0.2, pinchStartZoom * (d/pinchStartDist)));
                actualizarZoomLabel();
                dibujar();
            }
        }
    }, { passive:false });

    canvas.addEventListener('touchend', () => { dragging = false; pinchStartDist = 0; });
})();

// ══════════════════════════════════════════════════════
//  PERSISTENCIA
// ══════════════════════════════════════════════════════
function guardar() {
    try {
        localStorage.setItem('topo_puntos', JSON.stringify(puntos));
        localStorage.setItem('topo_estacion', JSON.stringify(Estacion));
        localStorage.setItem('topo_cruces', cntCruces);
        localStorage.setItem('topo_prol', cntProlongaciones);
    } catch(e) {
        // Safari privado bloquea localStorage — los datos se mantienen en memoria
    }
}

function borrarTodo() {
    if (confirm('¿Borrar todo el proyecto?')) { localStorage.clear(); location.reload(); }
}

// ══════════════════════════════════════════════════════
//  EXPORTACIÓN  (compatible con iOS Safari)
// ══════════════════════════════════════════════════════
// ── Modal de exportación (compatible iOS Safari) ──────────────
function mostrarModalExport(titulo, contenido, nombreArchivo) {
    // Eliminar modal previo si existe
    const prev = document.getElementById('exportModal');
    if (prev) prev.remove();

    const modal = document.createElement('div');
    modal.id = 'exportModal';
    modal.style.cssText = `
        position:fixed; inset:0; background:rgba(0,0,0,0.85); z-index:9999;
        display:flex; flex-direction:column; align-items:center; justify-content:flex-start;
        padding: max(20px, env(safe-area-inset-top)) 16px max(20px, env(safe-area-inset-bottom));
        overflow-y:auto; -webkit-overflow-scrolling:touch;
    `;

    modal.innerHTML = `
        <div style="width:100%;max-width:600px;background:#161b22;border:1px solid #30363d;border-radius:14px;overflow:hidden;">
            <div style="display:flex;align-items:center;justify-content:space-between;padding:14px 16px;border-bottom:1px solid #30363d;background:#21262d;">
                <div>
                    <div style="font-weight:800;font-size:1em;color:#e6edf3;">${titulo}</div>
                    <div style="font-size:0.75em;color:#8b949e;font-family:monospace;">${nombreArchivo}</div>
                </div>
                <button onclick="document.getElementById('exportModal').remove()"
                    style="background:#f85149;border:none;color:white;border-radius:7px;padding:6px 12px;font-weight:700;font-size:0.85em;cursor:pointer;min-height:36px;">✕ Cerrar</button>
            </div>
            <div style="padding:12px 16px;background:#21262d;border-bottom:1px solid #30363d;display:flex;gap:8px;flex-wrap:wrap;">
                <button id="btnCopiarExport"
                    style="background:#00e5cc;color:#000;border:none;border-radius:8px;padding:10px 18px;font-weight:800;font-size:0.9em;cursor:pointer;min-height:44px;flex:1;">
                    📋 Copiar todo
                </button>
                <button onclick="compartirTexto('${nombreArchivo}', document.getElementById('exportTextarea').value)"
                    style="background:#58a6ff;color:#000;border:none;border-radius:8px;padding:10px 18px;font-weight:800;font-size:0.9em;cursor:pointer;min-height:44px;flex:1;">
                    ↑ Compartir / Guardar
                </button>
            </div>
            <div style="padding:4px 0 0 0;background:#0d1117;">
                <textarea id="exportTextarea" readonly
                    style="width:100%;min-height:320px;background:#0d1117;color:#00e5cc;
                    font-family:'JetBrains Mono',monospace;font-size:12px;line-height:1.5;
                    border:none;outline:none;padding:14px 16px;resize:none;
                    -webkit-user-select:text;user-select:text;
                    -webkit-overflow-scrolling:touch;"
                >${contenido}</textarea>
            </div>
            <div style="padding:10px 16px 14px;background:#0d1117;">
                <div style="font-size:0.75em;color:#8b949e;line-height:1.5;">
                    💡 <b>En iPhone:</b> Pulsa <b>"Compartir / Guardar"</b> para enviarlo a Archivos, Mail o AirDrop.<br>
                    O pulsa <b>"Copiar todo"</b> y pégalo en Notes o en tu PC.
                </div>
            </div>
        </div>
    `;

    document.body.appendChild(modal);

    // Botón copiar
    document.getElementById('btnCopiarExport').addEventListener('click', function() {
        const ta = document.getElementById('exportTextarea');
        ta.select();
        try {
            if (navigator.clipboard && navigator.clipboard.writeText) {
                navigator.clipboard.writeText(ta.value).then(() => {
                    this.textContent = '✅ ¡Copiado!';
                    setTimeout(() => { this.textContent = '📋 Copiar todo'; }, 2000);
                });
            } else {
                document.execCommand('copy');
                this.textContent = '✅ ¡Copiado!';
                setTimeout(() => { this.textContent = '📋 Copiar todo'; }, 2000);
            }
        } catch(e) {
            ta.focus(); ta.setSelectionRange(0, ta.value.length);
            alert('Selecciona el texto y cópialo manualmente (⌘C / largo tap → Copiar)');
        }
    });
}

function compartirTexto(nombre, texto) {
    if (navigator.share) {
        const blob = new Blob([texto], {type: 'text/plain'});
        const file = new File([blob], nombre, {type: 'text/plain'});
        navigator.share({ files: [file], title: nombre })
            .catch(e => {
                // fallback: compartir solo texto
                navigator.share({ title: nombre, text: texto }).catch(() => {});
            });
    } else {
        alert('Compartir no está disponible. Usa "Copiar todo".');
    }
}

function descargarCSV() {
    if (Object.keys(puntos).length===0) { alert("No hay datos."); return; }
    let csv = "PUNTO;X_ESTE;Y_NORTE;Z_COTA;HZ_REPLANTEO_DEG;DH_REPLANTEO_M;CODIGO\n";
    for (const id in puntos) {
        const p=puntos[id];
        csv += `${id};${p.x.toFixed(4).replace('.',',')};${p.y.toFixed(4).replace('.',',')};${p.z.toFixed(4).replace('.',',')};${p.hzReplanteo};${p.dhReplanteo};${p.codigo||'Marco'}\n`;
    }
    mostrarModalExport('Exportar CSV', csv, 'levantamiento.csv');
}

function descargarDXF() {
    if (Object.keys(puntos).length===0) { alert("No hay datos."); return; }
    let dxf="0\nSECTION\n2\nENTITIES\n";
    const marcos=Object.keys(puntos).filter(id=>puntos[id].codigo==='Marco').sort((a,b)=>puntos[a].orden-puntos[b].orden);
    if (marcos.length>1) {
        for (let i=0;i<marcos.length-1;i++) {
            const p1=puntos[marcos[i]], p2=puntos[marcos[i+1]];
            dxf+=`0\nLINE\n8\nLINDEROS\n10\n${p1.x}\n20\n${p1.y}\n30\n${p1.z}\n11\n${p2.x}\n21\n${p2.y}\n31\n${p2.z}\n`;
        }
    }
    for (const id in puntos) {
        const p=puntos[id];
        const capa = p.codigo==='Estación'?'ESTACIONES':p.codigo==='Marco'?'MARCOS':'AUXILIARES';
        dxf+=`0\nPOINT\n8\n${capa}\n10\n${p.x}\n20\n${p.y}\n30\n${p.z}\n`;
        dxf+=`0\nTEXT\n8\nTEXTOS\n10\n${p.x+0.2}\n20\n${p.y+0.2}\n30\n${p.z}\n40\n0.3\n1\n${id}\n`;
    }
    dxf+="0\nENDSEC\n0\nEOF\n";
    mostrarModalExport('Exportar DXF', dxf, 'plano.dxf');
}

// ══════════════════════════════════════════════════════
//  INIT
// ══════════════════════════════════════════════════════
window.onload = function() {
    // Render inputs with DMS mode by default
    renderAngInputs();

    // Restore from storage (con try-catch para Safari privado)
    try {
        const sp = localStorage.getItem('topo_puntos');
        const se = localStorage.getItem('topo_estacion');
        if (sp) puntos = JSON.parse(sp);
        if (se) Estacion = JSON.parse(se);
        cntCruces = parseInt(localStorage.getItem('topo_cruces'))||1;
        cntProlongaciones = parseInt(localStorage.getItem('topo_prol'))||1;
    } catch(e) {
        // Safari privado — arranca sin datos guardados
    }

    if (Estacion.activa) {
        document.getElementById('baseX').value = Estacion.x;
        document.getElementById('baseY').value = Estacion.y;
        document.getElementById('baseZ').value = Estacion.z;
        document.getElementById('altAparato').value = Estacion.altInst;
    }

    actualizarStatus(); actualizarLista();

    // Live auto-convert in converter tab
    document.getElementById('cv-d').addEventListener('input', convertirDMSaDeg);
    document.getElementById('cv-m').addEventListener('input', convertirDMSaDeg);
    document.getElementById('cv-s').addEventListener('input', convertirDMSaDeg);
    document.getElementById('cv-dec').addEventListener('input', convertirDecADMS);
    document.getElementById('cv-gon').addEventListener('input', convertirGonADeg);
};
</script>
</body>
</html>
