<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Estación Virtual Premium</title>
    <style>
        :root {
            --bg-main: #f1f5f9;
            --surface: #ffffff;
            --text-main: #0f172a;
            --text-muted: #64748b;
            --primary: #0ea5e9;
            --primary-hover: #0284c7;
            --success: #10b981;
            --success-hover: #059669;
            --danger: #ef4444;
            --danger-hover: #dc2626;
            --warning: #f59e0b;
            --purple: #6366f1;
            --slate-dark: #1e293b;
            --border: #e2e8f0;
        }
        body { 
            font-family: 'Aptos', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif; 
            margin: 0; padding: 16px; background-color: var(--bg-main); color: var(--text-main); 
            -webkit-font-smoothing: antialiased;
        }
        h2 { text-align: center; margin: 10px 0 24px 0; font-size: 1.7em; font-weight: 800; letter-spacing: -0.5px; color: var(--slate-dark); }
        h3 { margin: 0 0 16px 0; font-size: 1.2em; font-weight: 700; color: var(--slate-dark); padding-bottom: 8px; border-bottom: 1px solid var(--border); }
        .tabs { display: flex; gap: 4px; margin-bottom: 20px; background: #e2e8f0; padding: 5px; border-radius: 12px; }
        .tab-btn { 
            flex: 1; padding: 12px 8px; font-weight: 700; font-size: 0.85em; border: none; 
            border-radius: 8px; background: transparent; color: var(--text-muted); cursor: pointer; 
            text-transform: uppercase; letter-spacing: 0.5px; transition: all 0.25s ease;
        }
        .tab-btn.active { background: var(--surface); color: var(--slate-dark); box-shadow: 0 4px 10px rgba(15,23,42,0.08); }
        .tab-content { display: none; } .tab-content.active { display: block; }
        .card { 
            background: var(--surface); padding: 20px; border-radius: 16px; 
            box-shadow: 0 4px 18px rgba(15,23,42,0.04); margin-bottom: 16px; 
            border: 1px solid var(--border);
        }
        .row { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; } 
        .triple { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; } 
        .quad { display: grid; grid-template-columns: repeat(4, 1fr); gap: 8px; }
        label { display: block; font-weight: 600; margin-bottom: 6px; font-size: 0.85em; color: var(--text-muted); }
        input, select { 
            width: 100%; padding: 12px; border: 1.5px solid var(--border); border-radius: 10px; 
            box-sizing: border-box; font-size: 1.1em; font-weight: 700; color: var(--slate-dark);
            background-color: #f8fafc; transition: all 0.2s ease;
        }
        input:focus, select:focus { border-color: var(--primary); outline: none; background-color: var(--surface); box-shadow: 0 0 0 4px rgba(14,165,233,0.15); }
        button { 
            width: 100%; padding: 14px; font-size: 1em; font-weight: 700; border: none; 
            border-radius: 10px; cursor: pointer; color: white; margin-top: 6px; 
            text-transform: uppercase; letter-spacing: 0.5px; transition: all 0.2s ease;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
        }
        button:active { transform: scale(0.98); }
        .btn-dark { background-color: var(--slate-dark); } .btn-dark:hover { background-color: #0f172a; }
        .btn-green { background-color: var(--success); } .btn-green:hover { background-color: var(--success-hover); }
        .btn-blue { background-color: var(--primary); } .btn-blue:hover { background-color: var(--primary-hover); }
        .btn-purple { background-color: var(--purple); } .btn-red { background-color: var(--danger); } .btn-orange { background-color: var(--warning); }
        .result-box { background: #f8fafc; border: 2px dashed var(--border); padding: 12px; text-align: center; border-radius: 10px; font-size: 1em; font-weight: 700; margin-top: 12px; display: none; }
        .workspace { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-top: 20px; }
        .panel-lista { background: var(--surface); border-radius: 16px; padding: 16px; height: 380px; overflow-y: auto; border: 1px solid var(--border); box-shadow: 0 4px 18px rgba(15,23,42,0.04); }
        .puntos-container { display: flex; flex-direction: column; gap: 8px; }
        .item-punto { 
            background: #f8fafc; padding: 12px 12px 10px 12px; border-radius: 10px; 
            border: 1px solid var(--border); font-size: 0.88em; position: relative;
            padding-right: 100px;
        }
        .item-punto-base { background: #e0f2fe; border-color: #bae6fd; }
        .item-punto-acciones { position: absolute; top: 8px; right: 8px; display: flex; gap: 5px; }
        .btn-accion-p { background: #e2e8f0; color: var(--slate-dark); border: none; border-radius: 6px; padding: 4px 8px; font-size: 0.78em; font-weight: 700; cursor: pointer; transition: background 0.2s; white-space: nowrap; }
        .btn-borrar-p { background: #fee2e2; color: var(--danger); }
        .btn-borrar-p:hover { background: #fca5a5; color: white; }
        .btn-editar-p { background: #dbeafe; color: var(--primary); }
        .btn-editar-p:hover { background: #93c5fd; color: white; }
        .badge { display: inline-block; padding: 2px 8px; border-radius: 999px; font-size: 0.75em; font-weight: 700; margin-left: 6px; }
        .badge-estacion { background: #cffafe; color: #0e7490; }
        .badge-marco { background: #fef3c7; color: #b45309; }
        .badge-interseccion { background: #ede9fe; color: #5b21b6; }
        .badge-ref { background: #f0fdf4; color: #15803d; }
        .pt-coords { color: var(--slate-dark); margin: 4px 0 2px 0; font-family: 'Courier New', monospace; font-size: 0.92em; }
        .pt-angles { color: #b7950b; font-family: 'Courier New', monospace; font-size: 0.88em; }
        .panel-mapa { background: var(--surface); border-radius: 16px; padding: 16px; text-align: center; display: flex; flex-direction: column; align-items: center; border: 1px solid var(--border); box-shadow: 0 4px 18px rgba(15,23,42,0.04); }
        canvas { background: #0f172a; border-radius: 12px; width: 100%; max-width: 320px; height: 300px; margin-top: 8px; box-shadow: inset 0 4px 12px rgba(0,0,0,0.2); touch-action: none; cursor: grab; }
        canvas:active { cursor: grabbing; }
        .layer-controls { display: flex; gap: 14px; margin-bottom: 4px; font-size: 0.85em; font-weight: 700; color: var(--text-muted); }
        .zoom-controls { display: flex; gap: 6px; margin-top: 8px; align-items: center; }
        .btn-zoom { width: auto; padding: 6px 16px; margin: 0; font-size: 1.1em; font-weight: 800; border: none; border-radius: 8px; cursor: pointer; background: var(--slate-dark); color: white; line-height: 1; }
        .zoom-label { font-size: 0.8em; font-weight: 700; color: var(--text-muted); min-width: 50px; text-align: center; }

        /* ── MODAL ── */
        .modal-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.6); z-index: 1000; overflow-y: auto; -webkit-overflow-scrolling: touch; }
        .modal-box { background: var(--surface); margin: 30px auto; padding: 24px; border-radius: 16px; max-width: 440px; width: 90%; box-shadow: 0 20px 60px rgba(0,0,0,0.3); }
        .modal-box h3 { font-size: 1.1em; }
        .modal-field { margin-bottom: 14px; }
        .modal-field label { margin-bottom: 5px; }
        .modal-field input, .modal-field select { padding: 10px; font-size: 1em; }
    </style>
</head>
<body>

<h2>📐 Libreta Topográfica</h2>

<div class="tabs">
    <button id="btn-tab-estacion" class="tab-btn active" onclick="cambiarPestana('pestana-estacion', this)">🛰️ Estacionar</button>
    <button class="tab-btn" onclick="cambiarPestana('pestana-datos', this)">📥 Puntos</button>
    <button class="tab-btn" onclick="cambiarPestana('pestana-rectas', this)">📏 Rectas</button>
    <button class="tab-btn" onclick="cambiarPestana('pestana-areas', this)">🗺️ Áreas</button>
</div>

<!-- PESTAÑA 1: ESTACIONAMIENTO -->
<div id="pestana-estacion" class="tab-content active">
    <div class="card">
        <h3>📍 Configuración del Estacionamiento</h3>
        <div style="margin-bottom: 16px;">
            <label>Método de instalación:</label>
            <select id="metodoEstacion" onchange="conmutarCamposEstacion()">
                <option value="origen">1. Base Nueva (0,0,0 o Coordenadas GPS)</option>
                <option value="anterior">2. Estación en Punto Conocido (Estación Inversa)</option>
            </select>
        </div>
        <div id="bloque-origen">
            <div class="triple">
                <div><label>X (Este):</label><input type="number" id="baseX" value="0.000" step="0.001"></div>
                <div><label>Y (Norte):</label><input type="number" id="baseY" value="0.000" step="0.001"></div>
                <div><label>Z (Cota):</label><input type="number" id="baseZ" value="0.000" step="0.001"></div>
            </div>
        </div>
        <div id="bloque-anterior" style="display:none;">
            <div class="row">
                <div><label>Nº Punto ocupado (ET):</label><input type="text" id="puntoOcupado" placeholder="Ej: 3"></div>
                <div><label>Nº Punto referenciado:</label><input type="text" id="puntoReferenciado" placeholder="Ej: 1"></div>
            </div>
            <div style="margin-top:10px; border: 1px solid var(--border); padding: 14px; border-radius: 12px; background: #fffbeb;">
                <div class="row">
                    <div><label>Lectura Hz ET a Ref (º):</label><input type="number" id="lecturaHzReferencia" value="0.0000" step="0.0001"></div>
                    <div><label>Distancia Medida (m):</label><input type="number" id="distanciaControl" placeholder="Opcional" step="0.001"></div>
                </div>
            </div>
        </div>
        <div class="row" style="margin-top: 14px; border-top:1px solid var(--border); padding-top:12px;">
            <div><label>Alt. Instrumento (m):</label><input type="number" id="altAparato" value="1.500" step="0.001"></div>
            <div><label>Azimut Inicial (º):</label><input type="number" id="azimutRef" value="0.0000" step="0.0001"></div>
        </div>
        <button class="btn-dark" style="margin-top: 16px;" onclick="fijarEstacionBase()">📍 Validar Estacionamiento</button>
        <div id="resEstacion" class="result-box" style="display:block; background:#e0f2fe; color:#0369a1; border-color:#bae6fd;">⚠️ Estación vacía. Registra la base para poder tomar puntos.</div>
    </div>
</div>

<!-- PESTAÑA 2: ENTRADA DE DATOS DESDE LA ET -->
<div id="pestana-datos" class="tab-content">
    <div class="card" style="border-left: 6px solid var(--success);">
        <h3>📥 Entrada desde Estación Total</h3>
        <div class="row">
            <div><label>Nº Punto:</label><input type="text" id="punto" value="1"></div>
            <div><label>Alt. Prisma (m):</label><input type="number" id="altPrisma" value="1.500" step="0.001"></div>
        </div>
        <div style="margin-top: 8px;">
            <label>Ángulo Horiz. (Hz):</label>
            <div class="triple" style="gap: 8px;">
                <div><label style="color: var(--primary); font-size: 0.8em;">Grados (º)</label><input type="number" id="angHorG" placeholder="0" min="0" max="359" step="1" inputmode="numeric"></div>
                <div><label style="color: var(--primary); font-size: 0.8em;">Minutos (')</label><input type="number" id="angHorM" placeholder="0" min="0" max="59" step="1" inputmode="numeric"></div>
                <div><label style="color: var(--primary); font-size: 0.8em;">Segundos (")</label><input type="number" id="angHorS" placeholder="0" min="0" max="59.9" step="0.1" inputmode="decimal"></div>
            </div>
        </div>
        <div style="margin-top: 10px;">
            <label>Ángulo Vert. (V):</label>
            <div class="triple" style="gap: 8px;">
                <div><label style="color: var(--primary); font-size: 0.8em;">Grados (º)</label><input type="number" id="angVertG" value="90" min="0" max="359" step="1" inputmode="numeric"></div>
                <div><label style="color: var(--primary); font-size: 0.8em;">Minutos (')</label><input type="number" id="angVertM" value="0" min="0" max="59" step="1" inputmode="numeric"></div>
                <div><label style="color: var(--primary); font-size: 0.8em;">Segundos (")</label><input type="number" id="angVertS" value="0" min="0" max="59.9" step="0.1" inputmode="decimal"></div>
            </div>
        </div>
        <div class="row" style="margin-top: 8px;">
            <div><label>Distancia Inclinada (Di):</label><input type="text" id="dist" placeholder="0.000" inputmode="decimal"></div>
            <div>
                <label>Código de Campo:</label>
                <select id="codigoPunto">
                    <option value="Marco" selected>Marco (Lindero)</option>
                    <option value="Intersección">Intersección</option>
                    <option value="Ref.">Ref. (Referencia)</option>
                    <option value="Estación">Estación</option>
                </select>
            </div>
        </div>
        <button class="btn-green" style="margin-top: 16px;" onclick="registrarPunto()">💾 Calcular y Anotar</button>
        <div id="resultadoPunto" class="result-box" style="display:none; background:#f0fdf4; border-color:var(--success); color:#065f46; text-align:left; line-height:1.7;"></div>
    </div>
</div>

<!-- PESTAÑA 3: RECTAS E INTERSECCIONES -->
<div id="pestana-rectas" class="tab-content">

    <!-- DISTANCIA ENTRE PUNTOS (nuevo) -->
    <div class="card" style="border-left: 6px solid var(--primary);">
        <h3>📏 Distancia entre Puntos</h3>
        <div class="row">
            <div><label>Punto A:</label><input type="text" id="distPuntoA" placeholder="Ej: 1"></div>
            <div><label>Punto B:</label><input type="text" id="distPuntoB" placeholder="Ej: 2"></div>
        </div>
        <button class="btn-blue" style="margin-top:12px;" onclick="calcularDistanciaPuntos()">📐 Calcular Distancia</button>
        <div id="resultadoDistancia" class="result-box" style="background:#eff6ff; border-color:var(--primary); color:#1e40af; text-align:left; line-height:1.8;"></div>
    </div>

    <div class="card" style="border-left: 6px solid var(--purple);">
        <h3>📏 Herramientas de Rectas y Tramos</h3>
        <div class="row">
            <div><label>Punto Inicial (A):</label><input type="text" id="rectaP1" placeholder="Ej: 1"></div>
            <div><label>Punto Final (B):</label><input type="text" id="rectaP2" placeholder="Ej: 2"></div>
        </div>
        <div class="row" style="margin-top: 8px;">
            <div><input type="number" id="distFija" placeholder="Metros" step="0.01"><button class="btn-purple" onclick="generarPuntosCadaX()">Cada X m</button></div>
            <div><input type="number" id="numPartes" placeholder="Partes" step="1"><button class="btn-purple" onclick="generarPuntosPorDivision()">Dividir en N</button></div>
        </div>
        <div style="margin-top: 16px; border-top: 1px solid var(--border); padding-top: 14px;">
            <label style="color: var(--purple); font-size: 0.95em;"><b>Opción C:</b> Prolongar línea desde punto base:</label>
            <div class="triple" style="margin-top: 8px;">
                <div><label>Punto Base:</label><input type="text" id="proPBase" placeholder="Ej: 1"></div>
                <div><label>Pto Dirección:</label><input type="text" id="proPDireccion" placeholder="Ej: 2"></div>
                <div>
                    <label>Sentido:</label>
                    <select id="proSentido">
                        <option value="adelante">Hacia Adelante</option>
                        <option value="atras">Hacia Atrás</option>
                    </select>
                </div>
            </div>
            <div class="row" style="margin-top: 10px;">
                <input type="number" id="proDistancia" placeholder="Distancia en metros" step="0.01">
                <button class="btn-purple" onclick="prolongarDesdePunto()">Proyectar Punto</button>
            </div>
        </div>
        <div id="resultadoRecta" class="result-box" style="background: #f5eef8; border-color: var(--purple); color: var(--purple);"></div>
    </div>

    <div class="card" style="border-left: 6px solid var(--danger);">
        <h3>✖️ Prolongación e Intersección de 2 Líneas</h3>
        <div class="quad">
            <div><label>L1-Inic</label><input type="text" id="intA" placeholder="P1"></div>
            <div><label>L1-Fin</label><input type="text" id="intB" placeholder="P2"></div>
            <div><label>L2-Inic</label><input type="text" id="intC" placeholder="P3"></div>
            <div><label>L2-Fin</label><input type="text" id="intD" placeholder="P4"></div>
        </div>
        <button class="btn-red" style="margin-top: 16px;" onclick="calcularInterseccionLineas()">Calcular Punto de Cruce</button>
        <div id="resultadoInterseccion" class="result-box" style="background: #fdedec; border-color: var(--danger); color: var(--danger);"></div>
    </div>
</div>

<!-- PESTAÑA 4: CÁLCULO DE ÁREAS -->
<div id="pestana-areas" class="tab-content">
    <div class="card" style="border-left: 6px solid var(--warning);">
        <h3>🗺️ Cálculo de Área de Polígonos</h3>
        <label>Introduce la secuencia ordenada de los vértices (ej: 1, 2, Cruze_1, 3):</label>
        <input type="text" id="secuenciaPuntos" placeholder="1, 2, 3">
        <button class="btn-orange" style="margin-top: 16px;" onclick="calcularAreaPoligono()">📐 Obtener Superficie</button>
        <div id="resultadoArea" class="result-box" style="background: #fef9e7; border-color: var(--warning); color: #b7950b;"></div>
    </div>
</div>

<!-- BOTONES GLOBALES -->
<div class="triple" style="margin-top: 8px; gap: 10px;">
    <button class="btn-blue" onclick="descargarCSV()">💾 Exportar Excel</button>
    <button class="btn-blue" onclick="descargarDXF()" style="background-color: var(--slate-dark);">📐 Exportar AutoCAD</button>
    <button class="btn-red" onclick="borrarTodoElTrabajo()" style="background-color: #94a3b8;">🗑️ Reset General</button>
</div>

<!-- PANEL INFERIOR PERMANENTE -->
<div class="workspace">
    <div class="panel-lista">
        <h3 style="border: none; margin-bottom: 12px; padding: 0;">📋 Registro de Puntos</h3>
        <div id="listaPuntosVisual" class="puntos-container"></div>
    </div>
    <div class="panel-mapa">
        <h3 style="border: none; margin-bottom: 8px; padding: 0;">🗺️ Croquis Inteligente</h3>
        <div class="layer-controls">
            <label style="display:inline-flex; align-items:center; gap:4px;"><input type="checkbox" id="chkLineas" checked onchange="dibujarPlano()"> Linderos</label>
            <label style="display:inline-flex; align-items:center; gap:4px;"><input type="checkbox" id="chkTextos" checked onchange="dibujarPlano()"> Nombres</label>
        </div>
        <canvas id="mapaCanvas" width="300" height="300"></canvas>
        <div class="zoom-controls">
            <button class="btn-zoom btn-dark" onclick="ajustarZoom(1.25)">＋</button>
            <span class="zoom-label" id="zoomLabel">100%</span>
            <button class="btn-zoom btn-dark" onclick="ajustarZoom(0.8)">－</button>
            <button class="btn-dark" style="width:auto; padding:6px 12px; margin:0; font-size:0.8em; border-radius:8px;" onclick="centrarPlano()">⟳ Centrar</button>
        </div>
    </div>
</div>

<!-- ══════════════════════════════════════
     MODAL: EDITAR PUNTO
════════════════════════════════════════ -->
<div id="modalEditarPunto" class="modal-overlay" onclick="cerrarModalSiOverlay(event)">
    <div class="modal-box">
        <h3>✏️ Editar Punto</h3>
        <div class="modal-field">
            <label>Nombre del punto:</label>
            <input type="text" id="editId">
        </div>
        <div class="triple" style="gap:8px;">
            <div class="modal-field"><label>X (Este):</label><input type="number" id="editX" step="0.001"></div>
            <div class="modal-field"><label>Y (Norte):</label><input type="number" id="editY" step="0.001"></div>
            <div class="modal-field"><label>Z (Cota):</label><input type="number" id="editZ" step="0.001"></div>
        </div>
        <div class="row" style="gap:8px;">
            <div class="modal-field"><label>Hz Replanteo (°):</label><input type="number" id="editHz" step="0.0001"></div>
            <div class="modal-field"><label>Dh Replanteo (m):</label><input type="number" id="editDh" step="0.001"></div>
        </div>
        <div class="modal-field">
            <label>Código:</label>
            <select id="editCodigo">
                <option value="Marco">Marco (Lindero)</option>
                <option value="Intersección">Intersección</option>
                <option value="Ref.">Ref. (Referencia)</option>
                <option value="Estación">Estación</option>
            </select>
        </div>
        <div class="row" style="margin-top:8px; gap:10px;">
            <button class="btn-green" onclick="guardarEdicionPunto()">💾 Guardar Cambios</button>
            <button onclick="cerrarModalEditar()" style="background:var(--text-muted); margin-top:6px;">✕ Cancelar</button>
        </div>
    </div>
</div>

<script>
    // ═══════════════════════════════════════
    //  CONVERSIÓN GRADOS DECIMALES → G° M' S"
    // ═══════════════════════════════════════
    function decToDMS(deg) {
        const sign = deg < 0 ? '-' : '';
        const abs = Math.abs(parseFloat(deg) || 0);
        const d = Math.floor(abs);
        const mTotal = (abs - d) * 60;
        const m = Math.floor(mTotal);
        const s = (mTotal - m) * 60;
        return `${sign}${d}° ${String(m).padStart(2,'0')}' ${s.toFixed(1).padStart(4,'0')}"`;
    }

    let puntos = {};
    let contadorCruces = 1;
    let contadorProlongaciones = 1;
    let Estacion = { x: 0, y: 0, z: 0, altInst: 1.5, azimut: 0, id: "0" };

    // ── Canvas zoom / pan state ──
    let mapZoom = 1;
    let mapPanX = 0;
    let mapPanY = 0;
    let isDragging = false;
    let lastMouseX = 0;
    let lastMouseY = 0;

    // ── Edit modal state ──
    let editandoIdOriginal = null;

    // ═══════════════════════════════════════
    //  INICIALIZACIÓN
    // ═══════════════════════════════════════
    window.onload = function() {
        if (localStorage.getItem("topografia_puntos")) {
            puntos = JSON.parse(localStorage.getItem("topografia_puntos"));
            contadorCruces = parseInt(localStorage.getItem("topografia_cruces")) || 1;
            contadorProlongaciones = parseInt(localStorage.getItem("topografia_prolongaciones")) || 1;
            Estacion = JSON.parse(localStorage.getItem("topografia_estacion")) || { x: 0, y: 0, z: 0, altInst: 1.5, azimut: 0, id: "0" };
            document.getElementById('baseX').value = Estacion.x;
            document.getElementById('baseY').value = Estacion.y;
            document.getElementById('baseZ').value = Estacion.z;
            document.getElementById('altAparato').value = Estacion.altInst;
            document.getElementById('azimutRef').value = Estacion.azimut;
            actualizarMensajeEstacion();
            actualizarListadoYPlano();
        }
        setupCanvasEvents();
    };

    // ═══════════════════════════════════════
    //  PESTAÑAS
    // ═══════════════════════════════════════
    function cambiarPestana(idContenido, boton) {
        document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
        document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
        document.getElementById(idContenido).classList.add('active');
        boton.classList.add('active');
        if (idContenido === 'pestana-datos' || idContenido === 'pestana-estacion') dibujarPlano();
    }

    // ═══════════════════════════════════════
    //  ESTACIÓN
    // ═══════════════════════════════════════
    function conmutarCamposEstacion() {
        const metodo = document.getElementById('metodoEstacion').value;
        document.getElementById('bloque-origen').style.display = metodo === 'origen' ? 'block' : 'none';
        document.getElementById('bloque-anterior').style.display = metodo === 'anterior' ? 'block' : 'none';
    }

    function actualizarMensajeEstacion() {
        const box = document.getElementById('resEstacion');
        box.innerHTML = `🟢 <b>Estación Activa (Punto ${Estacion.id}):</b><br>X: ${Estacion.x.toFixed(3)} · Y: ${Estacion.y.toFixed(3)}<br>Azimut de Limbo: <b>${Estacion.azimut.toFixed(4)}°</b>`;
    }

    function guardarEnMemoriaLocal() {
        localStorage.setItem("topografia_puntos", JSON.stringify(puntos));
        localStorage.setItem("topografia_cruces", contadorCruces);
        localStorage.setItem("topografia_prolongaciones", contadorProlongaciones);
        localStorage.setItem("topografia_estacion", JSON.stringify(Estacion));
    }

    function borrarTodoElTrabajo() {
        if (confirm("¿Borrar todo el proyecto?")) { localStorage.clear(); location.reload(); }
    }

    function fijarEstacionBase() {
        const metodo = document.getElementById('metodoEstacion').value;
        Estacion.altInst = parseFloat(document.getElementById('altAparato').value) || 0;

        if (metodo === 'origen') {
            Estacion.x = parseFloat(document.getElementById('baseX').value) || 0;
            Estacion.y = parseFloat(document.getElementById('baseY').value) || 0;
            Estacion.z = parseFloat(document.getElementById('baseZ').value) || 0;
            Estacion.azimut = parseFloat(document.getElementById('azimutRef').value) || 0;
            Estacion.id = "0";
            puntos["0"] = { x: Estacion.x, y: Estacion.y, z: Estacion.z, hzReplanteo: "0.0000", dhReplanteo: "0.000", codigo: "Estación", orden: Date.now() };
        } else {
            const pOcupado = document.getElementById('puntoOcupado').value.trim();
            const pRef = document.getElementById('puntoReferenciado').value.trim();
            const lecturaHz = parseFloat(document.getElementById('lecturaHzReferencia').value);
            const distControl = parseFloat(document.getElementById('distanciaControl').value);

            if (!puntos[pOcupado] || !puntos[pRef] || isNaN(lecturaHz)) {
                alert("Error: Los puntos indicados no existen en el registro o falta la lectura.");
                return;
            }

            const dx = puntos[pRef].x - puntos[pOcupado].x;
            const dy = puntos[pRef].y - puntos[pOcupado].y;
            const distTeorica = Math.sqrt(dx*dx + dy*dy);

            if (!isNaN(distControl)) {
                const errorDist = Math.abs(distTeorica - distControl);
                if (errorDist > 0.03) {
                    if (!confirm(`⚠️ ¡ALERTA DE ERROR! La distancia medida varía ${errorDist.toFixed(3)}m de la teórica (${distTeorica.toFixed(3)}m). ¿Deseas continuar de todos modos?`)) return;
                }
            }

            let azimutReal = Math.atan2(dx, dy) * (180 / Math.PI);
            if (azimutReal < 0) azimutReal += 360;

            let azimutCalculado = azimutReal - lecturaHz;
            if (azimutCalculado < 0) azimutCalculado += 360;

            Estacion.x = puntos[pOcupado].x;
            Estacion.y = puntos[pOcupado].y;
            Estacion.z = puntos[pOcupado].z;
            Estacion.azimut = azimutCalculado;
            Estacion.id = pOcupado;
            document.getElementById('azimutRef').value = azimutCalculado.toFixed(4);
            puntos[pOcupado].codigo = "Estación";
        }

        actualizarMensajeEstacion(); guardarEnMemoriaLocal(); actualizarListadoYPlano();
        alert("Estación configurada con éxito. Ya puedes ir a la pestaña 'Puntos'.");
    }

    // ═══════════════════════════════════════
    //  REGISTRO DE PUNTO
    // ═══════════════════════════════════════
    function registrarPunto() {
        if (Object.keys(puntos).length === 0) { alert("Primero debes validar tu Estación en la pestaña 1."); return; }
        const pt = document.getElementById('punto').value.trim();
        const hzG = parseFloat(document.getElementById('angHorG').value) || 0;
        const hzM = parseFloat(document.getElementById('angHorM').value) || 0;
        const hzS = parseFloat(document.getElementById('angHorS').value) || 0;
        const hzRaw = hzG + hzM / 60 + hzS / 3600;

        const vG  = parseFloat(document.getElementById('angVertG').value);
        const vM  = parseFloat(document.getElementById('angVertM').value) || 0;
        const vS  = parseFloat(document.getElementById('angVertS').value) || 0;
        const vRaw = (isNaN(vG) ? 90 : vG) + vM / 60 + vS / 3600;
        const di = parseFloat(document.getElementById('dist').value);
        const ap = parseFloat(document.getElementById('altPrisma').value);
        const cod = document.getElementById('codigoPunto').value;
        if (!pt || isNaN(di)) { alert("Faltan datos."); return; }

        const anguloFinalDeg = (hzRaw + Estacion.azimut) % 360;
        const hzRad = anguloFinalDeg * (Math.PI / 180);
        const vRad = vRaw * (Math.PI / 180);

        const dh = di * Math.sin(vRad);
        const x = Estacion.x + (dh * Math.sin(hzRad));
        const y = Estacion.y + (dh * Math.cos(hzRad));
        const z = Estacion.z + Estacion.altInst + (di * Math.cos(vRad)) - ap;

        puntos[pt] = { x, y, z, hzReplanteo: hzRaw.toFixed(4), dhReplanteo: dh.toFixed(3), codigo: cod, orden: Date.now() };
        guardarEnMemoriaLocal(); actualizarListadoYPlano();

        // ── Mostrar resultado con el mismo formato que las tarjetas ──
        const resBox = document.getElementById('resultadoPunto');
        resBox.innerHTML =
            `✅ <b>Pt ${pt}</b> <span style="background:#dbeafe;color:#1d4ed8;padding:1px 7px;border-radius:999px;font-size:0.85em;">${cod}</span> registrado<br>` +
            `<span style="font-family:'Courier New',monospace;">X ${x.toFixed(3)} · Y ${y.toFixed(3)} · Z ${z.toFixed(3)}</span><br>` +
            `<span style="font-family:'Courier New',monospace;color:#b7950b;">↺ Hz ${decToDMS(hzRaw)} · Dh ${dh.toFixed(3)} m</span>`;
        resBox.style.display = "block";

        if (!isNaN(pt)) document.getElementById('punto').value = parseInt(pt) + 1;
        document.getElementById('angHorG').value = "";
        document.getElementById('angHorM').value = "";
        document.getElementById('angHorS').value = "";
        document.getElementById('angVertG').value = "90";
        document.getElementById('angVertM').value = "0";
        document.getElementById('angVertS').value = "0";        document.getElementById('dist').value = "";
        document.getElementById('codigoPunto').value = "Marco";
        document.getElementById('angHorG').focus();
    }

    // ═══════════════════════════════════════
    //  CÁLCULO DE DISTANCIA ENTRE PUNTOS (nuevo)
    // ═══════════════════════════════════════
    function calcularDistanciaPuntos() {
        const idA = document.getElementById('distPuntoA').value.trim();
        const idB = document.getElementById('distPuntoB').value.trim();
        const resBox = document.getElementById('resultadoDistancia');
        if (!puntos[idA] || !puntos[idB]) { alert("Uno o ambos puntos no existen en el registro."); return; }
        const A = puntos[idA], B = puntos[idB];
        const dx = B.x - A.x, dy = B.y - A.y, dz = B.z - A.z;
        const dist2D = Math.sqrt(dx*dx + dy*dy);
        const dist3D = Math.sqrt(dx*dx + dy*dy + dz*dz);
        const desnivel = dz;
        const pendPct = dist2D > 0 ? (Math.abs(dz) / dist2D * 100) : 0;
        let azimutAB = Math.atan2(dx, dy) * (180 / Math.PI);
        if (azimutAB < 0) azimutAB += 360;
        resBox.innerHTML =
            `📏 <b>Dist. Horizontal:</b> ${dist2D.toFixed(3)} m<br>` +
            `📐 <b>Dist. 3D (inclinada):</b> ${dist3D.toFixed(3)} m<br>` +
            `⬆️ <b>Desnivel (ΔZ):</b> ${desnivel >= 0 ? '+' : ''}${desnivel.toFixed(3)} m<br>` +
            `📈 <b>Pendiente:</b> ${pendPct.toFixed(2)} %<br>` +
            `🧭 <b>Azimut A→B:</b> ${decToDMS(azimutAB)}`;
        resBox.style.display = "block";
    }

    // ═══════════════════════════════════════
    //  REPLANTEO
    // ═══════════════════════════════════════
    function calcularValoresReplanteo(x, y) {
        const dx = x - Estacion.x; const dy = y - Estacion.y; const dh = Math.sqrt(dx*dx + dy*dy);
        let angDeg = Math.atan2(dx, dy) * (180 / Math.PI);
        let hzMaquina = angDeg - Estacion.azimut;
        if (hzMaquina < 0) hzMaquina += 360;
        return { hz: (hzMaquina % 360).toFixed(4), dh: dh.toFixed(3) };
    }

    // ═══════════════════════════════════════
    //  BORRAR PUNTO
    // ═══════════════════════════════════════
    function borrarPuntoIndividual(id) {
        if (confirm(`¿Seguro que quieres borrar el punto "${id}"?`)) {
            delete puntos[id]; guardarEnMemoriaLocal(); actualizarListadoYPlano();
        }
    }

    // ═══════════════════════════════════════
    //  LISTADO DE PUNTOS (formato renovado)
    // ═══════════════════════════════════════
    function badgeCodigo(codigo) {
        const clases = { "Estación": "badge-estacion", "Marco": "badge-marco", "Intersección": "badge-interseccion", "Ref.": "badge-ref" };
        return `<span class="badge ${clases[codigo] || 'badge-marco'}">${codigo}</span>`;
    }

    function actualizarListadoYPlano() {
        const contenedor = document.getElementById('listaPuntosVisual');
        contenedor.innerHTML = "";
        let keys = Object.keys(puntos).sort((a,b) => isNaN(a)||isNaN(b) ? a.localeCompare(b) : parseInt(a)-parseInt(b));

        keys.forEach(id => {
            const p = puntos[id];
            const div = document.createElement('div');
            div.className = `item-punto ${id === "0" || id === Estacion.id ? "item-punto-base" : ""}`;
            div.innerHTML =
                `<div class="item-punto-acciones">
                    <button class="btn-accion-p btn-editar-p" onclick="abrirEdicion('${id}')">✏️ Editar</button>
                    <button class="btn-accion-p btn-borrar-p" onclick="borrarPuntoIndividual('${id}')">✕</button>
                </div>
                <b>Pt ${id}</b>${badgeCodigo(p.codigo || 'Marco')}
                <div class="pt-coords">X ${p.x.toFixed(3)} · Y ${p.y.toFixed(3)} · Z ${p.z.toFixed(3)}</div>
                <div class="pt-angles">↺ Hz ${decToDMS(p.hzReplanteo)} · Dh ${p.dhReplanteo} m</div>`;
            contenedor.appendChild(div);
        });

        dibujarPlano();
        let maxPt = 0;
        for (let id in puntos) { if (!isNaN(id)) maxPt = Math.max(maxPt, parseInt(id)); }
        document.getElementById('punto').value = maxPt + 1;
    }

    // ═══════════════════════════════════════
    //  MODAL EDITAR PUNTO
    // ═══════════════════════════════════════
    function abrirEdicion(id) {
        editandoIdOriginal = id;
        const p = puntos[id];
        document.getElementById('editId').value = id;
        document.getElementById('editX').value = p.x.toFixed(3);
        document.getElementById('editY').value = p.y.toFixed(3);
        document.getElementById('editZ').value = p.z.toFixed(3);
        document.getElementById('editHz').value = typeof p.hzReplanteo === 'string' ? p.hzReplanteo : p.hzReplanteo.toFixed(4);
        document.getElementById('editDh').value = typeof p.dhReplanteo === 'string' ? p.dhReplanteo : p.dhReplanteo.toFixed(3);
        document.getElementById('editCodigo').value = p.codigo || 'Marco';
        document.getElementById('modalEditarPunto').style.display = 'block';
    }

    function cerrarModalEditar() {
        document.getElementById('modalEditarPunto').style.display = 'none';
        editandoIdOriginal = null;
    }

    function cerrarModalSiOverlay(event) {
        if (event.target === document.getElementById('modalEditarPunto')) cerrarModalEditar();
    }

    function guardarEdicionPunto() {
        const nuevoId = document.getElementById('editId').value.trim();
        if (!nuevoId) { alert("El nombre del punto no puede estar vacío."); return; }
        const x = parseFloat(document.getElementById('editX').value);
        const y = parseFloat(document.getElementById('editY').value);
        const z = parseFloat(document.getElementById('editZ').value);
        const hz = document.getElementById('editHz').value;
        const dh = document.getElementById('editDh').value;
        const cod = document.getElementById('editCodigo').value;
        if (isNaN(x) || isNaN(y) || isNaN(z)) { alert("Las coordenadas X, Y, Z deben ser números válidos."); return; }

        // Si cambia el nombre, verificar conflicto
        if (nuevoId !== editandoIdOriginal && puntos[nuevoId]) {
            if (!confirm(`El punto "${nuevoId}" ya existe. ¿Reemplazarlo?`)) return;
        }

        const puntoActualizado = { ...puntos[editandoIdOriginal], x, y, z, hzReplanteo: hz, dhReplanteo: dh, codigo: cod };

        if (nuevoId !== editandoIdOriginal) {
            delete puntos[editandoIdOriginal];
            if (Estacion.id === editandoIdOriginal) Estacion.id = nuevoId;
        }
        puntos[nuevoId] = puntoActualizado;
        guardarEnMemoriaLocal();
        actualizarListadoYPlano();
        cerrarModalEditar();
    }

    // ═══════════════════════════════════════
    //  DIBUJAR PLANO CON ZOOM + PAN
    // ═══════════════════════════════════════
    function dibujarPlano() {
        const canvas = document.getElementById('mapaCanvas');
        const ctx = canvas.getContext('2d');
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        // Cuadrícula de fondo
        ctx.strokeStyle = "#1e293b"; ctx.lineWidth = 0.5;
        for (let i = 0; i <= canvas.width; i += 30) { ctx.beginPath(); ctx.moveTo(i,0); ctx.lineTo(i,canvas.height); ctx.stroke(); }
        for (let i = 0; i <= canvas.height; i += 30) { ctx.beginPath(); ctx.moveTo(0,i); ctx.lineTo(canvas.width,i); ctx.stroke(); }

        let keys = Object.keys(puntos);
        if (keys.length === 0) return;

        let minX = Infinity, maxX = -Infinity, minY = Infinity, maxY = -Infinity;
        keys.forEach(id => { const p = puntos[id]; minX = Math.min(minX, p.x); maxX = Math.max(maxX, p.x); minY = Math.min(minY, p.y); maxY = Math.max(maxY, p.y); });
        let rangeX = maxX - minX; let rangeY = maxY - minY; let maxRange = Math.max(rangeX, rangeY, 1);
        let baseScale = (canvas.width - 60) / maxRange;
        let baseOffsetX = (canvas.width / 2) - (baseScale * (minX + maxX) / 2);
        let baseOffsetY = (canvas.height / 2) - (baseScale * (minY + maxY) / 2);

        // Aplicar zoom y pan via transform
        ctx.save();
        ctx.translate(canvas.width / 2 + mapPanX, canvas.height / 2 + mapPanY);
        ctx.scale(mapZoom, mapZoom);
        ctx.translate(-canvas.width / 2, -canvas.height / 2);

        const toX = (wx) => baseOffsetX + wx * baseScale;
        const toY = (wy) => canvas.height - (baseOffsetY + wy * baseScale);

        const verLineas = document.getElementById('chkLineas').checked;
        const verTextos = document.getElementById('chkTextos').checked;

        if (verLineas) {
            let puntosMarco = Object.keys(puntos).filter(id => puntos[id].codigo === "Marco").sort((a, b) => puntos[a].orden - puntos[b].orden);
            if (puntosMarco.length > 1) {
                ctx.beginPath(); ctx.strokeStyle = "#10b981"; ctx.lineWidth = 2.5;
                puntosMarco.forEach((id, index) => {
                    const p = puntos[id];
                    if (index === 0) ctx.moveTo(toX(p.x), toY(p.y));
                    else ctx.lineTo(toX(p.x), toY(p.y));
                });
                ctx.stroke();
            }
        }

        keys.forEach(id => {
            const p = puntos[id];
            const cx = toX(p.x); const cy = toY(p.y);
            const codigo = p.codigo || "Marco";

            ctx.beginPath();
            if (codigo === "Estación") {
                ctx.strokeStyle = "#38bdf8"; ctx.lineWidth = 2.5;
                ctx.moveTo(cx, cy - 6); ctx.lineTo(cx - 6, cy + 5); ctx.lineTo(cx + 6, cy + 5); ctx.closePath(); ctx.stroke();
            } else if (codigo === "Marco") {
                ctx.fillStyle = "#ef4444";
                ctx.arc(cx, cy, 4, 0, 2 * Math.PI); ctx.fill();
            } else {
                ctx.strokeStyle = "#f59e0b"; ctx.lineWidth = 2;
                ctx.moveTo(cx - 5, cy); ctx.lineTo(cx + 5, cy);
                ctx.moveTo(cx, cy - 5); ctx.lineTo(cx, cy + 5); ctx.stroke();
            }
            if (verTextos) {
                ctx.fillStyle = "#94a3b8"; ctx.font = "bold 10px sans-serif";
                ctx.fillText(id, cx + 6, cy - 2);
            }
        });

        ctx.restore();
        document.getElementById('zoomLabel').textContent = Math.round(mapZoom * 100) + '%';
    }

    // ═══════════════════════════════════════
    //  EVENTOS DE ZOOM Y PAN DEL CANVAS
    // ═══════════════════════════════════════
    function ajustarZoom(factor) {
        mapZoom = Math.max(0.3, Math.min(15, mapZoom * factor));
        dibujarPlano();
    }

    function centrarPlano() {
        mapZoom = 1; mapPanX = 0; mapPanY = 0;
        dibujarPlano();
    }

    function setupCanvasEvents() {
        const canvas = document.getElementById('mapaCanvas');

        // Rueda del ratón → zoom
        canvas.addEventListener('wheel', (e) => {
            e.preventDefault();
            const factor = e.deltaY < 0 ? 1.15 : 0.87;
            mapZoom = Math.max(0.3, Math.min(15, mapZoom * factor));
            dibujarPlano();
        }, { passive: false });

        // Arrastre con ratón → pan
        canvas.addEventListener('mousedown', (e) => { isDragging = true; lastMouseX = e.clientX; lastMouseY = e.clientY; });
        canvas.addEventListener('mousemove', (e) => {
            if (!isDragging) return;
            mapPanX += e.clientX - lastMouseX; mapPanY += e.clientY - lastMouseY;
            lastMouseX = e.clientX; lastMouseY = e.clientY;
            dibujarPlano();
        });
        canvas.addEventListener('mouseup', () => { isDragging = false; });
        canvas.addEventListener('mouseleave', () => { isDragging = false; });

        // Touch: pellizco → zoom, 1 dedo → pan
        let lastTouchDist = null;
        let lastTouchX = null, lastTouchY = null;

        canvas.addEventListener('touchstart', (e) => {
            e.preventDefault();
            if (e.touches.length === 2) {
                const dx = e.touches[0].clientX - e.touches[1].clientX;
                const dy = e.touches[0].clientY - e.touches[1].clientY;
                lastTouchDist = Math.sqrt(dx*dx + dy*dy);
                lastTouchX = null; lastTouchY = null;
            } else if (e.touches.length === 1) {
                lastTouchX = e.touches[0].clientX;
                lastTouchY = e.touches[0].clientY;
                lastTouchDist = null;
            }
        }, { passive: false });

        canvas.addEventListener('touchmove', (e) => {
            e.preventDefault();
            if (e.touches.length === 2) {
                const dx = e.touches[0].clientX - e.touches[1].clientX;
                const dy = e.touches[0].clientY - e.touches[1].clientY;
                const dist = Math.sqrt(dx*dx + dy*dy);
                if (lastTouchDist) {
                    const factor = dist / lastTouchDist;
                    mapZoom = Math.max(0.3, Math.min(15, mapZoom * factor));
                }
                lastTouchDist = dist;
            } else if (e.touches.length === 1 && lastTouchX !== null) {
                mapPanX += e.touches[0].clientX - lastTouchX;
                mapPanY += e.touches[0].clientY - lastTouchY;
                lastTouchX = e.touches[0].clientX;
                lastTouchY = e.touches[0].clientY;
            }
            dibujarPlano();
        }, { passive: false });

        canvas.addEventListener('touchend', () => {
            lastTouchDist = null; lastTouchX = null; lastTouchY = null;
        });
    }

    // ═══════════════════════════════════════
    //  RECTAS, INTERPOLACIONES
    // ═══════════════════════════════════════
    function obtenerPuntosAB() {
        const p1 = document.getElementById('rectaP1').value.trim();
        const p2 = document.getElementById('rectaP2').value.trim();
        if (!puntos[p1] || !puntos[p2]) { alert("Puntos inválidos."); return null; }
        return { A: puntos[p1], B: puntos[p2], idA: p1, idB: p2 };
    }

    function generarPuntosCadaX() {
        const datos = obtenerPuntosAB(); if (!datos) return;
        const distIntervalo = parseFloat(document.getElementById('distFija').value);
        if (isNaN(distIntervalo) || distIntervalo <= 0) return;
        const dx = datos.B.x - datos.A.x, dy = datos.B.y - datos.A.y, dz = datos.B.z - datos.A.z;
        const distTotal = Math.sqrt(dx*dx + dy*dy + dz*dz); const numPuntos = Math.floor(distTotal / distIntervalo);
        for (let i = 1; i <= numPuntos; i++) {
            const t = (distIntervalo * i) / distTotal;
            const xi = datos.A.x + dx * t, yi = datos.A.y + dy * t, zi = datos.A.z + dz * t;
            const rep = calcularValoresReplanteo(xi, yi);
            puntos[`${datos.idA}-${datos.idB}_m${(distIntervalo*i).toFixed(1)}`] = { x: xi, y: yi, z: zi, hzReplanteo: rep.hz, dhReplanteo: rep.dh, codigo: "Intersección", orden: Date.now() };
        }
        guardarEnMemoriaLocal(); actualizarListadoYPlano();
        document.getElementById('resultadoRecta').innerText = `✅ Tramos calculados con éxito en la lista inferior.`;
        document.getElementById('resultadoRecta').style.display = "block";
    }

    function generarPuntosPorDivision() {
        const datos = obtenerPuntosAB(); if (!datos) return;
        const partes = parseInt(document.getElementById('numPartes').value);
        if (isNaN(partes) || partes <= 1) return;
        const dx = datos.B.x - datos.A.x, dy = datos.B.y - datos.A.y, dz = datos.B.z - datos.A.z;
        for (let i = 1; i < partes; i++) {
            const t = i / partes;
            const xi = datos.A.x + dx * t, yi = datos.A.y + dy * t, zi = datos.A.z + dz * t;
            const rep = calcularValoresReplanteo(xi, yi);
            puntos[`${datos.idA}-${datos.idB}_d${i}`] = { x: xi, y: yi, z: zi, hzReplanteo: rep.hz, dhReplanteo: rep.dh, codigo: "Intersección", orden: Date.now() };
        }
        guardarEnMemoriaLocal(); actualizarListadoYPlano();
        document.getElementById('resultadoRecta').innerText = `✅ Segmento dividido con éxito. Revisa la lista inferior.`;
        document.getElementById('resultadoRecta').style.display = "block";
    }

    function prolongarDesdePunto() {
        const idBase = document.getElementById('proPBase').value.trim();
        const idDir = document.getElementById('proPDireccion').value.trim();
        const distancia = parseFloat(document.getElementById('proDistancia').value);
        const sentido = document.getElementById('proSentido').value;
        if (!puntos[idBase] || !puntos[idDir] || isNaN(distancia) || distancia <= 0) { alert("Verifica los puntos y la distancia."); return; }
        const PBase = puntos[idBase]; const PDir = puntos[idDir];
        let dx = PDir.x - PBase.x; let dy = PDir.y - PBase.y;
        let distSegmento = Math.sqrt(dx*dx + dy*dy);
        if (distSegmento < 0.001) return;
        let vx = dx / distSegmento; let vy = dy / distSegmento;
        if (sentido === "atras") { vx = -vx; vy = -vy; }
        const xi = PBase.x + (vx * distancia); const yi = PBase.y + (vy * distancia);
        const rep = calcularValoresReplanteo(xi, yi);
        const nombreProlongacion = `Pro_${contadorProlongaciones}_base${idBase}`;
        puntos[nombreProlongacion] = { x: xi, y: yi, z: PBase.z, hzReplanteo: rep.hz, dhReplanteo: rep.dh, codigo: "Intersección", orden: Date.now() };
        contadorProlongaciones++; guardarEnMemoriaLocal(); actualizarListadoYPlano();
        const resBox = document.getElementById('resultadoRecta');
        resBox.innerHTML = `🎯 Guardado: <b>${nombreProlongacion}</b><br>X ${xi.toFixed(3)} · Y ${yi.toFixed(3)}<br>↺ Hz ${decToDMS(rep.hz)} · Dh ${rep.dh} m`;
        resBox.style.display = "block";
    }

    // ═══════════════════════════════════════
    //  INTERSECCIÓN DE LÍNEAS
    // ═══════════════════════════════════════
    function calcularInterseccionLineas() {
        const idA = document.getElementById('intA').value.trim(); const idB = document.getElementById('intB').value.trim();
        const idC = document.getElementById('intC').value.trim(); const idD = document.getElementById('intD').value.trim();
        if (!puntos[idA] || !puntos[idB] || !puntos[idC] || !puntos[idD]) { alert("Revisa los puntos."); return; }
        const A = puntos[idA]; const B = puntos[idB]; const C = puntos[idC]; const D = puntos[idD];
        const den = (A.x - B.x) * (C.y - D.y) - (A.y - B.y) * (C.x - D.x);
        if (Math.abs(den) < 0.00001) { alert("Líneas paralelas."); return; }
        const xi = ((A.x*B.y - A.y*B.x)*(C.x - D.x) - (A.x - B.x)*(C.x*D.y - C.y*D.x)) / den;
        const yi = ((A.x*B.y - A.y*B.x)*(C.y - D.y) - (A.y - B.y)*(C.x*D.y - C.y*D.x)) / den;
        const rep = calcularValoresReplanteo(xi, yi);
        const nombreCruce = `Cruze_${contadorCruces}`;
        puntos[nombreCruce] = { x: xi, y: yi, z: (A.z+B.z+C.z+D.z)/4, hzReplanteo: rep.hz, dhReplanteo: rep.dh, codigo: "Intersección", orden: Date.now() };
        contadorCruces++; guardarEnMemoriaLocal(); actualizarListadoYPlano();
        const resBox = document.getElementById('resultadoInterseccion');
        resBox.innerHTML = `🎯 Guardado: <b>${nombreCruce}</b><br>X ${xi.toFixed(3)} · Y ${yi.toFixed(3)}<br>↺ Hz ${decToDMS(rep.hz)} · Dh ${rep.dh} m`;
        resBox.style.display = "block";
    }

    // ═══════════════════════════════════════
    //  ÁREA
    // ═══════════════════════════════════════
    function calcularAreaPoligono() {
        const ids = document.getElementById('secuenciaPuntos').value.split(',').map(item => item.trim());
        let vertices = []; for (let id of ids) { if (puntos[id]) vertices.push(puntos[id]); }
        if (vertices.length < 3) { alert("Mínimo 3 puntos."); return; }
        let suma1 = 0, suma2 = 0, perimetro = 0;
        for (let i = 0; i < vertices.length; i++) {
            let j = (i + 1) % vertices.length;
            suma1 += vertices[i].x * vertices[j].y; suma2 += vertices[i].y * vertices[j].x;
            perimetro += Math.sqrt(Math.pow(vertices[j].x-vertices[i].x,2) + Math.pow(vertices[j].y-vertices[i].y,2));
        }
        const area = Math.abs(suma1 - suma2) / 2;
        const res = document.getElementById('resultadoArea');
        res.innerHTML = `📐 Superficie: <b>${area.toFixed(2)} m²</b><br>🏃 Perímetro: <b>${perimetro.toFixed(2)} m</b>`;
        res.style.display = "block";
    }

    // ═══════════════════════════════════════
    //  EXPORTAR CSV
    // ═══════════════════════════════════════
    function descargarCSV() {
        if (Object.keys(puntos).length === 0) { alert("No hay datos."); return; }
        let csv = "PUNTO;X_ESTE;Y_NORTE;Z_COTA;HZ_REPLANTEO_DEG;DH_REPLANTEO_M;CODIGO\n";
        for (let id in puntos) {
            let p = puntos[id];
            let xStr = p.x.toFixed(4).replace('.', ','); let yStr = p.y.toFixed(4).replace('.', ','); let zStr = p.z.toFixed(4).replace('.', ',');
            let hzStr = typeof p.hzReplanteo === 'string' ? p.hzReplanteo.replace('.', ',') : p.hzReplanteo;
            let dhStr = typeof p.dhReplanteo === 'string' ? p.dhReplanteo.replace('.', ',') : p.dhReplanteo;
            csv += `${id};${xStr};${yStr};${zStr};${hzStr};${dhStr};${p.codigo || 'Marco'}\n`;
        }
        const blob = new Blob([new Uint8Array([0xEF, 0xBB, 0xBF]), csv], { type: "text/csv;charset=utf-8;" });
        const link = document.createElement("a"); link.href = URL.createObjectURL(blob);
        link.setAttribute("download", "levantamiento_excel.csv"); document.body.appendChild(link); link.click(); document.body.removeChild(link);
    }

    // ═══════════════════════════════════════
    //  EXPORTAR DXF
    // ═══════════════════════════════════════
    function descargarDXF() {
        if (Object.keys(puntos).length === 0) { alert("No hay datos."); return; }
        let dxf = "0\nSECTION\n2\nENTITIES\n";
        let puntosMarco = Object.keys(puntos).filter(id => puntos[id].codigo === "Marco").sort((a, b) => puntos[a].orden - puntos[b].orden);
        if (puntosMarco.length > 1) {
            for (let i = 0; i < puntosMarco.length - 1; i++) {
                let p1 = puntos[puntosMarco[i]]; let p2 = puntos[puntosMarco[i+1]];
                dxf += "0\nLINE\n8\nCAPA_LINDEROS\n" + `10\n${p1.x}\n20\n${p1.y}\n30\n${p1.z}\n11\n${p2.x}\n21\n${p2.y}\n31\n${p2.z}\n`;
            }
        }
        for (let id in puntos) {
            let p = puntos[id]; const cod = p.codigo || "Marco";
            let capa = "CAPA_MARCOS";
            if (cod === "Estación") capa = "CAPA_ESTACIONES";
            else if (cod === "Intersección" || cod === "Ref.") capa = "CAPA_AUXILIARES";
            dxf += "0\nPOINT\n" + `8\n${capa}\n10\n${p.x}\n20\n${p.y}\n30\n${p.z}\n`;
            dxf += "0\nTEXT\n8\nCAPA_TEXTOS\n" + `10\n${p.x + 0.2}\n20\n${p.y + 0.2}\n30\n${p.z}\n` + "40\n0.3\n" + `1\n${id}\n`;
        }
        dxf += "0\nENDSEC\n0\nEOF\n";
        const blob = new Blob([dxf], { type: "application/dxf" });
        const link = document.createElement("a"); link.href = URL.createObjectURL(blob);
        link.setAttribute("download", "plano_profesional.dxf"); document.body.appendChild(link); link.click(); document.body.removeChild(link);
    }
</script>
</body>
</html>
