<!DOCTYPE html>
<html lang="es" translate="no">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Verificación de Unidad – Transporte</title>
  <meta name="color-scheme" content="light dark">
  <meta name="theme-color" content="#0ea5e9">
  <style>
    :root{
      --bg: #0b1220;
      --card:#10192b;
      --muted:#8aa0b6;
      --ok:#16a34a;
      --warn:#ca8a04;
      --bad:#dc2626;
      --accent:#0ea5e9;
      --stroke: #20304a;
      --text:#e6edf6;
      --text-strong:#ffffff;
    }
    @media (prefers-color-scheme: light){
      :root{
        --bg:#f3f7fb; --card:#ffffff; --muted:#48607a; --stroke:#e5eef6;
        --text:#1b2a3b; --text-strong:#0b1220;
      }
    }
    *{box-sizing:border-box}
    body{
      margin:0; font:16px/1.5 system-ui, -apple-system, "Segoe UI", Roboto, Ubuntu, "Helvetica Neue", Arial;
      color:var(--text); background:radial-gradient(1200px 800px at 80% -10%, rgba(14,165,233,.15), transparent),
                         linear-gradient(180deg, rgba(14,165,233,.06), transparent 30%),
                         var(--bg);
    }
    .wrap{max-width:980px; margin:auto; padding:28px 16px 80px}
    header{
      display:flex; gap:16px; align-items:center; justify-content:space-between; flex-wrap:wrap
    }
    .brand{display:flex; gap:14px; align-items:center}
    .logo{
      width:52px; height:52px; display:grid; place-items:center; border-radius:14px;
      background:linear-gradient(135deg, var(--accent), #22d3ee);
      color:#fff; font-weight:800; letter-spacing:.5px; box-shadow:0 10px 30px rgba(14,165,233,.35);
    }
    .title h1{margin:0; font-size:1.25rem; color:var(--text-strong)}
    .title small{color:var(--muted)}
    .badge{
      padding:6px 10px; border-radius:999px; font-size:.85rem; font-weight:700; letter-spacing:.3px;
      display:inline-flex; align-items:center; gap:8px; border:1px solid var(--stroke); background:var(--card)
    }
    .badge i{width:10px; height:10px; border-radius:50%}
    .badge.ok i{background:var(--ok)} .badge.warn i{background:var(--warn)} .badge.bad i{background:var(--bad)}

    .grid{display:grid; grid-template-columns:repeat(12, 1fr); gap:16px; margin-top:18px}
    .card{
      grid-column: span 6; background:var(--card); border:1px solid var(--stroke);
      border-radius:18px; padding:16px; box-shadow:0 8px 24px rgba(0,0,0,.12)
    }
    .card.full{grid-column:1 / -1}
    @media (max-width:760px){ .card{grid-column:1 / -1} }
    .card h3{margin:0 0 8px; font-size:1rem; color:var(--text-strong)}
    .muted{color:var(--muted)}
    .kv{display:grid; grid-template-columns: 180px 1fr; gap:10px 16px; margin-top:6px}
    .chip{
      display:inline-flex; align-items:center; gap:8px; padding:8px 10px; border-radius:12px;
      border:1px dashed var(--stroke)
    }
    .chip.ok{background:rgba(22,163,74,.12); border-color:rgba(22,163,74,.35)}
    .chip.warn{background:rgba(202,138,4,.12); border-color:rgba(202,138,4,.35)}
    .chip.bad{background:rgba(220,38,38,.12); border-color:rgba(220,38,38,.35)}

    .cta-row{display:flex; gap:10px; flex-wrap:wrap}
    .btn{
      display:inline-flex; gap:10px; align-items:center; padding:10px 14px; border-radius:12px;
      border:1px solid var(--stroke); background:linear-gradient(180deg, rgba(255,255,255,.06), transparent);
      color:var(--text-strong); text-decoration:none; font-weight:700;
    }
    .btn.primary{background:linear-gradient(135deg, var(--accent), #22d3ee); border-color:transparent; color:white}
    .btn:active{transform:translateY(1px)}
    table{width:100%; border-collapse:collapse; overflow:auto; display:block}
    th,td{padding:10px 12px; border-bottom:1px solid var(--stroke); text-align:left}
    th{color:var(--muted); font-weight:600}
    .status{font-weight:800}
    .status.ok{color:var(--ok)} .status.warn{color:var(--warn)} .status.bad{color:var(--bad)}

    footer{margin-top:18px; display:flex; justify-content:space-between; align-items:center; gap:10px; flex-wrap:wrap}
    .note{color:var(--muted); font-size:.9rem}
    .folio{font-weight:700; letter-spacing:.4px}

    /* Impresión */
    @media print{
      .btn, .cta-row, .badge{display:none !important}
      body{background:white}
      .card{box-shadow:none}
    }
  </style>
</head>
<body>
  <div class="wrap">
    <header>
      <div class="brand">
        <div class="logo" aria-hidden="true">TL</div>
        <div class="title">
          <h1>Verificación de Unidad</h1>
          <small class="muted">Portal de consulta pública</small>
        </div>
      </div>
      <span id="semBadge" class="badge ok" title="Estatus general">
        <i></i><span id="semText">DOCUMENTOS EN REGLA</span>
      </span>
    </header>

    <!-- Tarjeta: Datos principales -->
    <section class="grid">
      <article class="card">
        <h3>Identificación de la unidad</h3>
        <div class="kv">
          <div class="muted">Empresa</div><div id="empresa">Veltrex Logistics</div>
          <div class="muted">Unidad</div><div id="unidad">VT-0012</div>
          <div class="muted">Placas</div><div id="placas">XYZ-123-A</div>
          <div class="muted">Tipo</div><div id="tipo">Tracto camión 6x4</div>
        </div>
      </article>

      <!-- Tarjeta: Semáforo detallado -->
      <article class="card">
        <h3>Estatus de documentos</h3>
        <div class="kv">
          <div class="muted">Legalidad de la unidad</div>
          <div><span id="legalChip" class="chip ok">Vigente</span></div>

          <div class="muted">Permisos</div>
          <div><span id="permChip" class="chip ok">Permiso #PER-98422 — hasta 2026-03-01</span></div>

          <div class="muted">Seguro</div>
          <div><span id="segChip" class="chip warn">Póliza #AXA-77821 — vence 2025-11-30</span></div>

          <div class="muted">Rutas autorizadas</div>
          <div id="rutasList" class="muted">Celaya ⇄ Querétaro, Celaya ⇄ León</div>

          <div class="muted">Volumen de carga</div>
          <div id="volumen">Hasta 28,000 kg / 65 m³</div>
        </div>
      </article>

      <!-- Tabla de comprobación -->
      <article class="card full">
        <h3>Detalle para verificación</h3>
        <div class="muted">Consulta electrónica para autoridades y ciudadanos.</div>
        <div style="margin-top:10px; overflow:auto">
          <table aria-label="Tabla de verificación">
            <thead>
              <tr>
                <th>Documento</th>
                <th>Número / Folio</th>
                <th>Vigencia</th>
                <th>Estatus</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>Tarjeta de circulación</td>
                <td id="tcFolio">TC-553109</td>
                <td id="tcVig">2026-05-31</td>
                <td class="status ok" id="tcSta">Vigente</td>
              </tr>
              <tr>
                <td>Permiso SCT Federal</td>
                <td id="permFolio">PER-98422</td>
                <td id="permVig">2026-03-01</td>
                <td class="status ok" id="permSta">Vigente</td>
              </tr>
              <tr>
                <td>Póliza de seguro</td>
                <td id="segFolio">AXA-77821</td>
                <td id="segVig">2025-11-30</td>
                <td class="status warn" id="segSta">Próxima a vencer</td>
              </tr>
            </tbody>
          </table>
        </div>

        <div class="cta-row" style="margin-top:14px">
          <a class="btn primary" id="btnPDF" href="#" download>
            <!-- ícono PDF -->
            <svg width="18" height="18" viewBox="0 0 24 24" aria-hidden="true"><path fill="currentColor" d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8zm0 2l6 6h-6zM8 13h3a2 2 0 0 1 0 4H9v1H8zm1 1v2h2a1 1 0 0 0 0-2zm6 3h-2v-4h2a2 2 0 1 1 0 4m-1-3v2h1a1 1 0 1 0 0-2z"/></svg>
            Descargar comprobante (PDF)
          </a>
          <a class="btn" id="btnWhats" target="_blank" rel="noopener">
            <!-- ícono Whats -->
            <svg width="18" height="18" viewBox="0 0 24 24" aria-hidden="true"><path fill="currentColor" d="M12 2a10 10 0 0 0-8.66 15l-1.1 4 4.11-1.08A10 10 0 1 0 12 2m5.44 14.56c-.23.65-1.36 1.24-1.88 1.3c-.51.06-1.15.09-1.86-.12c-.43-.14-1-.33-1.72-.64a11.6 11.6 0 0 1-4.24-3.74a9.18 9.18 0 0 1-1.87-3.52c-.2-.76 0-1.4.45-1.9c.23-.25.5-.38.82-.38h.59c.19 0 .44.14.5.33l.71 1.7c.06.15.04.33-.06.51c-.09.18-.14.28-.27.43c-.13.15-.28.34-.4.46c-.13.12-.27.26-.12.51c.15.25.67 1.1 1.44 1.78c.99.88 1.83 1.15 2.1 1.28c.26.12.41.1.57-.05c.16-.14.65-.76.82-1.02c.17-.26.35-.22.59-.13c.24.1 1.52.72 1.78.85c.26.13.43.19.49.3c.06.11.06.65-.17 1.3Z"/></svg>
            Contacto de la empresa
          </a>
        </div>
      </article>
    </section>

    <footer>
      <div class="note">
        Folio: <span class="folio" id="folio">VL-2025-000128</span> ·
        Última actualización: <span id="updated">2025-09-20 12:45</span>
      </div>
      <div class="note">© <span id="empresaFoot">Veltrex Logistics</span></div>
    </footer>
  </div>

  <script>
    // ========= CONFIGURACIÓN POR DEFECTO =========
    const data = {
      empresa: "Veltrex Logistics",
      unidad: "VT-0012",
      placas: "XYZ-123-A",
      tipo: "Tracto camión 6x4",
      rutas: ["Celaya ⇄ Querétaro", "Celaya ⇄ León"],
      volumen: "Hasta 28,000 kg / 65 m³",
      folio: "VL-2025-000128",
      updated: "2025-09-20 12:45",
      whatsapp: "524611234567", // sin '+'; ej. México 52 + 461xxxxxxx
      pdfURL: "#",              // reemplaza por URL real del PDF
      // estatus individuales: ok | warn | bad
      legal: {status:"ok", text:"Vigente"},
      permiso: {status:"ok", folio:"PER-98422", vence:"2026-03-01"},
      seguro: {status:"warn", folio:"AXA-77821", vence:"2025-11-30"},
      tarjeta: {status:"ok", folio:"TC-553109", vence:"2026-05-31"}
    };

    // ========= PARÁMETROS POR URL (opcionales) =========
    // Ejemplo: ?empresa=Mi%20Transporte&unidad=VT-12&placas=ABC123&estatus=ok
    const params = new URLSearchParams(location.search);
    if (params.size){
      if (params.get("empresa")) data.empresa = params.get("empresa");
      if (params.get("unidad")) data.unidad = params.get("unidad");
      if (params.get("placas")) data.placas = params.get("placas");
      if (params.get("tipo")) data.tipo = params.get("tipo");
      if (params.get("rutas")) data.rutas = params.get("rutas").split("|");
      if (params.get("volumen")) data.volumen = params.get("volumen");
      if (params.get("folio")) data.folio = params.get("folio");
      if (params.get("updated")) data.updated = params.get("updated");
      if (params.get("whatsapp")) data.whatsapp = params.get("whatsapp").replace(/\D/g,"");
      if (params.get("pdf")) data.pdfURL = params.get("pdf");
      // Estatus global rápido (ok|warn|bad) para marcar todo
      if (params.get("estatus")){
        const s = params.get("estatus");
        data.legal.status = s; data.permiso.status = s; data.seguro.status = s; data.tarjeta.status = s;
      }
    }

    // ========= RENDER =========
    const $ = (id)=>document.getElementById(id);

    function apply(){
      // Identidad
      $("empresa").textContent = data.empresa;
      $("empresaFoot").textContent = data.empresa;
      $("unidad").textContent = data.unidad;
      $("placas").textContent = data.placas;
      $("tipo").textContent = data.tipo;
      $("rutasList").textContent = data.rutas.join(", ");
      $("volumen").textContent = data.volumen;
      $("folio").textContent = data.folio;
      $("updated").textContent = data.updated;

      // Chips
      setChip("legalChip", data.legal.status, data.legal.text || (data.legal.status==="ok" ? "Vigente" : data.legal.status==="warn" ? "Revisión" : "No vigente"));
      setChip("permChip", data.permiso.status, `Permiso ${data.permiso.folio} — hasta ${data.permiso.vence}`);
      setChip("segChip", data.seguro.status, `Póliza ${data.seguro.folio} — vence ${data.seguro.vence}`);

      // Tabla estados
      setRow("tc", data.tarjeta);
      setRow("perm", data.permiso);
      setRow("seg", data.seguro, {warn:"Próxima a vencer", ok:"Vigente", bad:"Vencida"});

      // Semáforo global
      const rank = rankStatus([data.legal.status, data.permiso.status, data.seguro.status, data.tarjeta.status]);
      const b = $("semBadge"), t = $("semText");
      b.classList.remove("ok","warn","bad"); b.classList.add(rank);
      t.textContent = rank==="ok" ? "DOCUMENTOS EN REGLA" : rank==="warn" ? "DOCUMENTOS POR VENCER" : "DOCUMENTOS NO VIGENTES";

      // Botones
      const w = data.whatsapp ? `https://wa.me/${data.whatsapp}?text=Hola,%20tengo%20dudas%20sobre%20la%20unidad%20${encodeURIComponent(data.unidad)}.` : "#";
      $("btnWhats").href = w;
      $("btnWhats").ariaLabel = "Abrir WhatsApp de contacto";
      $("btnPDF").href = data.pdfURL || "#";
      if (!data.pdfURL || data.pdfURL === "#") $("btnPDF").setAttribute("title","Asocia una URL de PDF en data.pdfURL");
    }

    function setChip(id, status, text){
      const el = $(id);
      el.classList.remove("ok","warn","bad");
      el.classList.add(status);
      el.textContent = text;
    }

    function setRow(prefix, obj, mapText){
      $(prefix+"Folio").textContent = obj.folio || "—";
      $(prefix+"Vig").textContent = obj.vence || "—";
      const cell = $(prefix+"Sta");
      cell.classList.remove("ok","warn","bad");
      cell.classList.add(obj.status);
      const label = mapText ? (mapText[obj.status] || obj.status) :
                    (obj.status==="ok" ? "Vigente" : obj.status==="warn" ? "Por vencer" : "No vigente");
      cell.textContent = label;
    }

    function rankStatus(list){
      // prioridad: bad > warn > ok
      if (list.includes("bad")) return "bad";
      if (list.includes("warn")) return "warn";
      return "ok";
    }

    apply();
  </script>
</body>
</html>
