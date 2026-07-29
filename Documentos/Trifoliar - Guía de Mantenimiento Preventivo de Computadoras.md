# Trifoliar - Guía de Mantenimiento Preventivo de Computadoras

<!DOCTYPE html>

<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trifoliar - Guía de Mantenimiento Preventivo de Computadoras</title>
    <style>
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --bg-dark: #0a1128;
            --card-bg: #ffffff;
            --text-main: #1e293b;
            --text-muted: #64748b;
            --border-color: #e2e8f0;
            --danger-bg: #fef2f2;
            --danger-border: #fecaca;
            --danger-text: #991b1b;
            --success-bg: #ecfdf5;
            --success-border: #a7f3d0;
            --success-text: #065f46;
            --info-bg: #f0f9ff;
            --info-border: #bae6fd;
            --info-text: #0369a1;
        }

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trifoliar - Guía de Mantenimiento Preventivo de Computadoras</title>
    <style>
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --bg-dark: #0a1128;
            --card-bg: #ffffff;
            --text-main: #1e293b;
            --text-muted: #64748b;
            --border-color: #e2e8f0;
            --danger-bg: #fef2f2;
            --danger-border: #fecaca;
            --danger-text: #991b1b;
            --success-bg: #ecfdf5;
            --success-border: #a7f3d0;
            --success-text: #065f46;
            --info-bg: #f0f9ff;
            --info-border: #bae6fd;
            --info-text: #0369a1;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: #f1f5f9;
            color: var(--text-main);
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 40px;
        }

        .side-title {
            font-size: 1.5rem;
            font-weight: 700;
            color: #334155;
            text-align: center;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        /* Contenedor del Trifoliar (3 paneles por lado) */
        .trifoliar-side {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            width: 100%;
            max-width: 1280px;
            background: #e2e8f0;
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 10px 25px -5px rgba(0, 0, 0, 0.1);
        }

        /* Estilo base de los Paneles (Estilo Físico con Puntos) */
        .panel {
            background-color: var(--card-bg);
            background-image: radial-gradient(#cbd5e1 1.2px, transparent 1.2px);
            background-size: 16px 16px;
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 28px 24px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            min-height: 620px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
            position: relative;
        }

        /* Encabezados de Panel */
        .panel-header {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 0.75rem;
            font-weight: 800;
            color: var(--primary);
            text-transform: uppercase;
            letter-spacing: 0.8px;
            margin-bottom: 20px;
            padding-bottom: 8px;
            border-bottom: 1px dashed #cbd5e1;
        }

        .panel-header-icon {
            width: 16px;
            height: 16px;
            fill: var(--primary);
        }

        .panel-title {
            font-size: 1.75rem;
            font-weight: 800;
            color: #0f172a;
            line-height: 1.2;
            margin-bottom: 16px;
        }

        .panel-content {
            font-size: 0.92rem;
            line-height: 1.6;
            color: #334155;
            display: flex;
            flex-direction: column;
            gap: 16px;
            flex-grow: 1;
        }

        /* Listas y viñetas */
        .feature-list {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-top: 5px;
        }

        .feature-list li {
            display: flex;
            align-items: flex-start;
            gap: 10px;
            font-weight: 600;
            font-size: 0.88rem;
            color: #1e293b;
        }

        .feature-list li svg {
            width: 18px;
            height: 18px;
            fill: var(--primary);
            flex-shrink: 0;
            margin-top: 2px;
        }

        /* Cajas de Alerta y Notificaciones */
        .box-info {
            background-color: var(--info-bg);
            border: 1px solid var(--info-border);
            color: var(--info-text);
            padding: 14px;
            border-radius: 12px;
            font-size: 0.85rem;
            line-height: 1.4;
        }

        .box-warning {
            background-color: var(--danger-bg);
            border: 1px solid var(--danger-border);
            color: var(--danger-text);
            padding: 12px;
            border-radius: 10px;
            font-size: 0.8rem;
            font-weight: 700;
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .box-success {
            background-color: var(--success-bg);
            border: 1px solid var(--success-border);
            color: var(--success-text);
            padding: 14px;
            border-radius: 12px;
            font-size: 0.9rem;
            font-weight: 700;
            text-align: center;
            margin-top: auto;
        }

        /* Estilo específico para PORTADA (Panel 3 - Oscuro) */
        .panel-portada {
            background-color: var(--bg-dark);
            background-image: radial-gradient(rgba(255, 255, 255, 0.08) 1.2px, transparent 1.2px);
            background-size: 16px 16px;
            color: #ffffff;
            border: none;
            text-align: left;
        }

        .portada-badge {
            background-color: rgba(37, 99, 235, 0.2);
            border: 1px solid rgba(59, 130, 246, 0.4);
            color: #60a5fa;
            padding: 6px 14px;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 700;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            width: fit-content;
            margin-bottom: 24px;
        }

        .portada-title {
            font-size: 2.1rem;
            font-weight: 800;
            line-height: 1.25;
            color: #ffffff;
            margin-bottom: 20px;
        }

        .portada-desc {
            font-size: 0.9rem;
            color: #94a3b8;
            line-height: 1.6;
        }

        .portada-graphic {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 14px;
            padding: 30px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 12px;
            margin: auto 0;
        }

        .portada-graphic svg {
            width: 48px;
            height: 48px;
            stroke: #38bdf8;
        }

        .portada-footer {
            font-size: 0.7rem;
            font-weight: 700;
            color: #64748b;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-align: center;
        }

        /* Pasos Numerados (Paneles 2, 5 y 6) */
        .step-list {
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .step-item {
            display: flex;
            gap: 12px;
            align-items: flex-start;
        }

        .step-number {
            background-color: var(--primary);
            color: white;
            font-weight: 800;
            font-size: 0.85rem;
            width: 26px;
            height: 26px;
            border-radius: 6px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
            margin-top: 2px;
        }

        .step-text {
            font-size: 0.88rem;
            color: #334155;
            line-height: 1.5;
        }

        .step-text strong {
            color: #0f172a;
        }

        /* Tabla de Materiales (Panel 4) */
        .materials-table {
            width: 100%;
            border-collapse: collapse;
            font-size: 0.8rem;
            margin-top: 5px;
            border-radius: 8px;
            overflow: hidden;
            border: 1px solid var(--border-color);
        }

        .materials-table th {
            background-color: #0f172a;
            color: #ffffff;
            text-align: left;
            padding: 8px 10px;
            font-weight: 700;
        }

        .materials-table td {
            padding: 7px 10px;
            border-bottom: 1px solid var(--border-color);
            background-color: #ffffff;
            color: #334155;
        }

        .materials-table tr:last-child td {
            border-bottom: none;
        }

        .materials-table td:first-child {
            font-weight: 700;
            color: #0f172a;
            width: 45%;
        }

        /* Registro de Control */
        .control-register {
            background: #f8fafc;
            border: 1px solid var(--border-color);
            border-radius: 10px;
            padding: 12px;
            font-size: 0.8rem;
            color: var(--text-muted);
            margin-top: auto;
        }

        .control-register strong {
            color: #0f172a;
            display: block;
            margin-bottom: 4px;
            font-size: 0.75rem;
            text-transform: uppercase;
        }

        /* Responsividad para pantallas pequeñas */
        @media (max-width: 900px) {
            .trifoliar-side {
                grid-template-columns: 1fr;
            }
            .panel {
                min-height: auto;
            }
        }
    </style>
</head>
<body>

    <!-- ==================== LADO EXTERIOR (A) ==================== -->
    <h2 class="side-title">Lado A (Exterior)</h2>
    <div class="trifoliar-side">
        
        <!-- PANEL 1: INTRODUCCIÓN -->
        <section class="panel">
            <div>
                <div class="panel-header">
                    <svg class="panel-header-icon" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 15h-2v-6h2v6zm0-8h-2V7h2v2z"/></svg>
                    PANEL 1 - INTRODUCCIÓN
                </div>
                <h1 class="panel-title">¿Por qué Mantenimiento?</h1>
                <div class="panel-content">
                    <p>El mantenimiento preventivo sistemático es fundamental para evitar la acumulación de polvo higroscópico y controlar las microdescargas electrostáticas (ESD), las cuales dañan las compuertas de silicio integradas sin que el técnico lo note a simple vista.</p>
                    
                    <ul class="feature-list">
                        <li>
                            <svg viewBox="0 0 24 24"><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41z"/></svg>
                            Protección contra sobrevoltajes.
                        </li>
                        <li>
                            <svg viewBox="0 0 24 24"><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41z"/></svg>
                            Estabilidad de la pasta térmica.
                        </li>
                        <li>
                            <svg viewBox="0 0 24 24"><path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41z"/></svg>
                            Evita el Thermal Throttling.
                        </li>
                    </ul>
                </div>
            </div>
            
            <div class="box-info">
                <strong>Objetivo:</strong> Aplicar metodologías estructuradas para el desmontaje, limpieza física y reensamble de tarjetas integradas.
            </div>
        </section>

        <!-- PANEL 2: CONTRAPORTADA -->
        <section class="panel">
            <div>
                <div class="panel-header">
                    <svg class="panel-header-icon" viewBox="0 0 24 24"><path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-5 14H7v-2h7v2zm3-4H7v-2h10v2zm0-4H7V7h10v2z"/></svg>
                    PANEL 2 - CONTRAPORTADA
                </div>
                <h2 class="panel-title">Competencias Clave</h2>
                <div class="panel-content">
                    <div class="step-list">
                        <div class="step-item">
                            <span class="step-number">1</span>
                            <div class="step-text">Detección de fallas físicas mediante diagnóstico visual veloz.</div>
                        </div>
                        <div class="step-item">
                            <span class="step-number">2</span>
                            <div class="step-text">Utilización sistemática de alcohol isopropílico para desengrase.</div>
                        </div>
                        <div class="step-item">
                            <span class="step-number">3</span>
                            <div class="step-text">Gestión térmica y reemplazo de materiales de interfaz de calor (TIM).</div>
                        </div>
                    </div>

                    <div class="box-warning" style="margin-top: 15px;">
                        ⚠️ EXCLUSIVO PARA MANTENIMIENTO FÍSICO PREVENTIVO
                    </div>
                </div>
            </div>

            <div class="control-register">
                <strong>REGISTRO DE CONTROL</strong>
                <div>Técnico: Estudiante de Práctica</div>
                <div>Fecha: Julio, 2026</div>
            </div>
        </section>

        <!-- PANEL 3: PORTADA -->
        <section class="panel panel-portada">
            <div>
                <div class="portada-badge">
                    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
                    Práctica Profesional
                </div>
                <h1 class="portada-title">Guía de Mantenimiento Preventivo de Computadoras</h1>
                <p class="portada-desc">Un manual didáctico y estandarizado para aprender a preservar componentes, remover impurezas de la circuitería integrada e incrementar la eficiencia del CPU.</p>
            </div>

            <div class="portada-graphic">
                <svg viewBox="0 0 24 24" fill="none" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><rect x="4" y="4" width="16" height="16" rx="2"/><rect x="9" y="9" width="6" height="6"/><line x1="9" y1="1" x2="9" y2="4"/><line x1="15" y1="1" x2="15" y2="4"/><line x1="9" y1="20" x2="9" y2="23"/><line x1="15" y1="20" x2="15" y2="23"/><line x1="20" y1="9" x2="23" y2="9"/><line x1="20" y1="15" x2="23" y2="15"/><line x1="1" y1="9" x2="4" y2="9"/><line x1="1" y1="15" x2="4" y2="15"/></svg>
                <span style="font-size: 0.75rem; color: #38bdf8; font-weight: 700; letter-spacing: 1px;">PROCEDIMIENTO SEGURO</span>
            </div>

            <div class="portada-footer">
                ESTÁNDAR PROFESIONAL TÉCNICO
            </div>
        </section>

    </div>

    <!-- ==================== LADO INTERIOR (B) ==================== -->
    <h2 class="side-title">Lado B (Interior)</h2>
    <div class="trifoliar-side">

        <!-- PANEL 4: PREPARACIÓN -->
        <section class="panel">
            <div>
                <div class="panel-header">
                    <svg class="panel-header-icon" viewBox="0 0 24 24"><path d="M22.7 19l-9.1-9.1c.9-2.3.4-5-1.5-6.9-2-2-5-2.4-7.4-1.3L9 6 6 9 1.6 4.7C.4 7.1.9 10.1 2.9 12.1c1.9 1.9 4.6 2.4 6.9 1.5l9.1 9.1c.4.4 1 .4 1.4 0l2.3-2.3c.5-.4.5-1.1.1-1.4z"/></svg>
                    PANEL 4 - PREPARACIÓN
                </div>
                <h2 class="panel-title">Materiales Indispensables</h2>
                <div class="panel-content">
                    <table class="materials-table">
                        <thead>
                            <tr>
                                <th>Material</th>
                                <th>Uso Práctico</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>Destornilladores Phillips</td>
                                <td>Para desmontar el gabinete y componentes.</td>
                            </tr>
                            <tr>
                                <td>Brocha antiestática</td>
                                <td>Remover polvo sin dañar los circuitos.</td>
                            </tr>
                            <tr>
                                <td>Aire comprimido</td>
                                <td>Limpiar ventiladores y disipadores.</td>
                            </tr>
                            <tr>
                                <td>Alcohol isopropílico (90% o superior)</td>
                                <td>Limpiar residuos de pasta térmica y suciedad.</td>
                            </tr>
                            <tr>
                                <td>Paños de microfibra</td>
                                <td>Limpieza de superficies.</td>
                            </tr>
                            <tr>
                                <td>Hisopos</td>
                                <td>Aplicar alcohol en zonas pequeñas.</td>
                            </tr>
                            <tr>
                                <td>Pasta térmica</td>
                                <td>Sustituir la pasta antigua del procesador.</td>
                            </tr>
                            <tr>
                                <td>Pulsera antiestática (opcional)</td>
                                <td>Evitar descargas electrostáticas.</td>
                            </tr>
                            <tr>
                                <td>Guantes de nitrilo (opcional)</td>
                                <td>Mantener limpios los componentes.</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>

            <div class="box-warning" style="text-align: left; background-color: #fef2f2; border-color: #fecaca; color: #991b1b; padding: 10px; font-size: 0.78rem; line-height: 1.4; margin-top: 10px;">
                <strong>Regla de Seguridad:</strong> Drena la energía residual de la tarjeta madre pulsando el encendido del equipo desconectado durante 5 segundos para vaciar los capacitores.
            </div>
        </section>

        <!-- PANEL 5: PROCEDIMIENTO -->
        <section class="panel">
            <div>
                <div class="panel-header">
                    <svg class="panel-header-icon" viewBox="0 0 24 24"><path d="M3 17.25V21h3.75L17.81 9.94l-3.75-3.75L3 17.25zM20.71 7.04c.39-.39.39-1.02 0-1.41l-2.34-2.34c-.39-.39-1.02-.39-1.41 0l-1.83 1.83 3.75 3.75 1.83-1.83z"/></svg>
                    PANEL 5 - PROCEDIMIENTO
                </div>
                <h2 class="panel-title">Limpieza Profunda</h2>
                <div class="panel-content">
                    <div class="step-list">
                        <div class="step-item">
                            <span class="step-number">1</span>
                            <div class="step-text">
                                <strong>Desensamble Cuidadoso</strong> Extrae de forma segura módulos como discos, tarjetas de video dedicadas y módulos de memoria RAM.
                            </div>
                        </div>
                        <div class="step-item">
                            <span class="step-number">2</span>
                            <div class="step-text">
                                <strong>Soplado de Placa</strong> Sujeta de forma obligatoria las aspas de los ventiladores. El soplado libre genera voltajes inversos nocivos.
                            </div>
                        </div>
                        <div class="step-item">
                            <span class="step-number">3</span>
                            <div class="step-text">
                                <strong>Contactos de RAM</strong> Usa goma de borrar blanca para restaurar los contactos dorados. Quita los residuos de goma con una brocha seca.
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- PANEL 6: FASE CRÍTICA -->
        <section class="panel">
            <div>
                <div class="panel-header">
                    <svg class="panel-header-icon" viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/></svg>
                    PANEL 6 - FASE CRÍTICA
                </div>
                <h2 class="panel-title">Mantenimiento Térmico</h2>
                <div class="panel-content">
                    <div class="step-list">
                        <div class="step-item">
                            <span class="step-number">4</span>
                            <div class="step-text">
                                <strong>Limpieza del IHS</strong> Disuelve pasta endurecida con alcohol isopropílico. Deja la base del CPU impecable.
                            </div>
                        </div>
                        <div class="step-item">
                            <span class="step-number">5</span>
                            <div class="step-text">
                                <strong>Aplicación de Pasta</strong> Dispensa una gota tamaño grano de arroz en el centro exacto. La presión del heatsink la distribuirá sola.
                            </div>
                        </div>
                        <div class="step-item">
                            <span class="step-number">6</span>
                            <div class="step-text">
                                <strong>Verificación</strong> Haz pruebas de inicio. Ingresa de inmediato al menú de BIOS y vigila que la temperatura se mantenga baja.
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div class="box-success">
                ✓ ¡Mantenimiento Completado con Éxito!
            </div>
        </section>

    </div>

</body>
</html>
```

</body>
</html>


