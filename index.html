<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">
    <title>Salesforce Chat - Prueba GitHub Pages</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Arial, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        .container {
            max-width: 1000px;
            margin: 0 auto;
        }
        .card {
            background: white;
            border-radius: 16px;
            padding: 30px;
            margin-bottom: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.2);
        }
        h1 {
            color: #0070d2;
            margin-bottom: 10px;
        }
        .badge {
            display: inline-block;
            background: #e9ecef;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 12px;
            font-family: monospace;
            margin: 5px 5px 0 0;
        }
        .info-box {
            background: #f8f9fa;
            padding: 15px;
            border-radius: 12px;
            margin: 20px 0;
            border-left: 4px solid #0070d2;
        }
        .status {
            padding: 15px;
            border-radius: 12px;
            margin: 20px 0;
            font-family: monospace;
            font-size: 14px;
        }
        .status.loading { background: #e3f2fd; color: #0c5460; border-left: 4px solid #2196f3; }
        .status.success { background: #d4edda; color: #155724; border-left: 4px solid #28a745; }
        .status.error { background: #f8d7da; color: #721c24; border-left: 4px solid #dc3545; }
        .status.warning { background: #fff3cd; color: #856404; border-left: 4px solid #ffc107; }
        button {
            background: #0070d2;
            color: white;
            border: none;
            padding: 12px 24px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            margin: 5px;
            transition: all 0.2s;
        }
        button:hover {
            background: #005fb2;
            transform: translateY(-1px);
        }
        button.secondary {
            background: #6c757d;
        }
        button.secondary:hover {
            background: #5a6268;
        }
        code {
            background: #e9ecef;
            padding: 2px 6px;
            border-radius: 4px;
            font-family: monospace;
            font-size: 13px;
        }
        .url-card {
            background: #f1f3f5;
            border-radius: 12px;
            padding: 15px;
            margin: 15px 0;
            font-family: monospace;
            word-break: break-all;
        }
        hr {
            margin: 20px 0;
            border: none;
            border-top: 1px solid #dee2e6;
        }
        .footer {
            text-align: center;
            color: rgba(255,255,255,0.8);
            font-size: 12px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="card">
            <h1>💬 Salesforce Embedded Chat</h1>
            <p>Prueba de conexión desde <strong>GitHub Pages</strong> a tu sandbox de Salesforce</p>
            
            <div>
                <span class="badge">🌐 Dominio: <span id="current-domain"></span></span>
                <span class="badge">🔑 Org: 00DS800000DPelu</span>
                <span class="badge">📦 Deployment: EJIE_WebChat</span>
            </div>
        </div>

        <div class="card">
            <h2>📊 Estado de conexión</h2>
            <div id="status" class="status loading">
                🔄 Inicializando chat de Salesforce...
            </div>

            <div style="display: flex; gap: 10px; flex-wrap: wrap; margin: 20px 0;">
                <button onclick="forceOpenChat()">💬 Abrir chat manualmente</button>
                <button onclick="showFullDebug()">🐛 Ver diagnóstico completo</button>
                <button onclick="testCORS()">🌐 Probar CORS</button>
            </div>

            <hr>

            <h3>📋 Configuración necesaria en Salesforce</h3>
            <div class="info-box">
                <strong>✅ Paso 1: Configuración de CORS</strong><br>
                Ve a <code>Configuración → CORS</code> y añade:<br>
                <code id="cors-url" style="display: inline-block; margin-top: 8px; background: #0070d2; color: white; padding: 4px 8px;"></code>
            </div>

            <div class="info-box">
                <strong>✅ Paso 2: Trusted Domains (en el Sitio de Experience Cloud)</strong><br>
                Ve a <code>Configuración → Sitios de Experience Cloud → tu sitio → Orígenes de confianza</code><br>
                Añade el mismo dominio de arriba.
            </div>

            <div class="info-box">
                <strong>✅ Paso 3: Publicar el sitio</strong><br>
                En el Administrador de Sitios, haz clic en <strong>"Publicar"</strong>.
            </div>

            <div class="info-box">
                <strong>✅ Paso 4: Agentes disponibles</strong><br>
                Asegúrate de tener al menos un agente <strong>"Online"</strong> en Omni-Channel.
            </div>
        </div>

        <div class="card" id="debug-card" style="display: none;">
            <h2>🔍 Diagnóstico detallado</h2>
            <div id="debug-info" class="url-card"></div>
        </div>

        <div class="footer">
            🔗 GitHub Pages | El chat debería aparecer en la esquina inferior derecha
        </div>
    </div>

    <script>
        // Mostrar el dominio actual
        const currentOrigin = window.location.origin;
        document.getElementById('current-domain').innerHTML = currentOrigin;
        document.getElementById('cors-url').innerHTML = currentOrigin;

        let initTime = Date.now();
        let bootstrapLoaded = false;
        let initCompleted = false;

        function updateStatus(message, type) {
            const statusDiv = document.getElementById('status');
            statusDiv.innerHTML = message;
            statusDiv.className = `status ${type}`;
        }

        function forceOpenChat() {
            if (typeof embeddedservice_bootstrap !== 'undefined') {
                try {
                    if (embeddedservice_bootstrap.openChat) {
                        embeddedservice_bootstrap.openChat();
                        updateStatus('✅ Chat abierto correctamente. Busca la ventana de chat.', 'success');
                    } else {
                        updateStatus('⚠️ El chat está inicializado. Si no se abre, verifica que haya agentes disponibles en Omni-Channel.', 'warning');
                    }
                } catch(e) {
                    console.error('Error al abrir:', e);
                    updateStatus('❌ Error al abrir: ' + e.message, 'error');
                }
            } else {
                updateStatus('⏳ El chat aún no ha cargado. Espera unos segundos...', 'loading');
            }
        }

        function testCORS() {
            updateStatus('🌐 Probando conexión con Salesforce...', 'loading');
            
            // Intentar hacer una petición fetch para detectar CORS
            const testUrl = 'https://zuzenean--pre.sandbox.my.site.com/ESWEJIEWebChat1780484137965/assets/js/bootstrap.min.js';
            
            fetch(testUrl, { mode: 'no-cors' })
                .then(() => {
                    updateStatus('✅ La conexión a Salesforce es posible. Si el chat no aparece, el problema es de disponibilidad de agentes o configuración del deployment.', 'success');
                })
                .catch((error) => {
                    updateStatus('⚠️ Posible problema de CORS o red. Revisa la consola (F12) para más detalles.', 'warning');
                    console.error('Error de conexión:', error);
                });
        }

        function showFullDebug() {
            const debugCard = document.getElementById('debug-card');
            const debugInfo = document.getElementById('debug-info');
            
            const hasBootstrap = typeof embeddedservice_bootstrap !== 'undefined';
            const isInitialized = hasBootstrap && embeddedservice_bootstrap.isInitialized ? 
                embeddedservice_bootstrap.isInitialized() : false;
            
            const chatContainer = document.querySelector('#embedded-messaging-container');
            const chatIframes = document.querySelectorAll('iframe[src*="salesforce"]');
            
            let html = '<strong>📊 DIAGNÓSTICO COMPLETO</strong><br><br>';
            html += `🕒 Hora de inicialización: ${new Date(initTime).toLocaleTimeString()}<br>`;
            html += `🌐 Dominio actual: ${currentOrigin}<br>`;
            html += `📦 Protocolo: ${window.location.protocol}<br>`;
            html += `🔷 Bootstrap cargado: ${hasBootstrap ? '✅ SÍ' : '❌ NO'}<br>`;
            html += `⚙️ Chat inicializado: ${isInitialized ? '✅ SÍ' : '❌ NO'}<br>`;
            html += `🎨 Container DOM: ${chatContainer ? '✅ SÍ' : '❌ NO'}<br>`;
            html += `🖼️ Iframes Salesforce: ${chatIframes ? chatIframes.length : 0}<br><br>`;
            
            if (hasBootstrap) {
                html += '<strong>🔧 Configuración actual del chat:</strong><br>';
                if (embeddedservice_bootstrap.settings) {
                    html += `Idioma: ${embeddedservice_bootstrap.settings.language || 'no definido'}<br>`;
                }
                
                const methods = [];
                for (let prop in embeddedservice_bootstrap) {
                    if (typeof embeddedservice_bootstrap[prop] === 'function') {
                        methods.push(prop);
                    }
                }
                html += `Métodos disponibles: ${methods.join(', ') || 'ninguno'}<br>`;
            }
            
            html += '<br><strong>💡 Interpretación:</strong><br>';
            if (!hasBootstrap) {
                html += '❌ El script de Salesforce no se cargó. Verifica tu conexión a internet y que la URL del sitio sea correcta.';
            } else if (!isInitialized) {
                html += '⚠️ El chat no se inicializó correctamente. Revisa los parámetros de init().';
            } else if (!chatContainer) {
                html += '⚠️ El chat está inicializado pero no se creó el contenedor. Esto suele ocurrir cuando:<br>';
                html += '• No hay agentes disponibles en Omni-Channel<br>';
                html += '• El horario del chat no permite atención ahora<br>';
                html += '• El deployment no está publicado<br>';
                html += '• El dominio no está en Trusted Domains del sitio';
            } else {
                html += '✅ Todo parece correcto. El chat debería funcionar. Si no ves el botón, intenta "Abrir chat manualmente".';
            }
            
            debugInfo.innerHTML = html;
            debugCard.style.display = 'block';
        }

        function initEmbeddedMessaging() {
            try {
                console.log('🚀 Inicializando Embedded Messaging desde:', currentOrigin);
                updateStatus('🔄 Conectando con Salesforce...', 'loading');
                
                embeddedservice_bootstrap.settings.language = 'es';
                // Forzar que el botón sea visible
                embeddedservice_bootstrap.settings.hideChatButtonOnLoad = false;
                
                embeddedservice_bootstrap.init(
                    '00DS800000DPelu',
                    'EJIE_WebChat',
                    'https://zuzenean--pre.sandbox.my.site.com/ESWEJIEWebChat1780484137965',
                    {
                        scrt2URL: 'https://zuzenean--pre.sandbox.my.salesforce-scrt.com'
                    }
                );
                
                initCompleted = true;
                console.log('✅ Inicialización completada');
                updateStatus('✅ Chat inicializado correctamente. Busca el ícono en la esquina inferior derecha o haz clic en "Abrir chat manualmente".', 'success');
                
                // Verificar después de 3 segundos si apareció el contenedor
                setTimeout(() => {
                    const container = document.querySelector('#embedded-messaging-container');
                    if (container) {
                        console.log('✅ Contenedor del chat detectado en el DOM');
                    } else {
                        console.warn('⚠️ No se detectó contenedor. Posiblemente no hay agentes disponibles.');
                        updateStatus('⚠️ Chat inicializado pero no visible. ¿Hay agentes disponibles en Omni-Channel?', 'warning');
                    }
                }, 3000);
                
            } catch (err) {
                console.error('❌ Error:', err);
                updateStatus('❌ Error: ' + err.message, 'error');
            }
        }

        // Monitorear errores globales
        window.addEventListener('error', function(e) {
            console.error('Error global:', e.message, e.filename);
            if (e.filename && e.filename.includes('salesforce')) {
                updateStatus('⚠️ Error cargando recursos de Salesforce. Verifica que el dominio esté en Trusted Domains.', 'warning');
            }
        });
    </script>

    <!-- Script oficial de Salesforce -->
    <script type='text/javascript' src='https://zuzenean--pre.sandbox.my.site.com/ESWEJIEWebChat1780484137965/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()' onerror="updateStatus('❌ No se pudo cargar el script de Salesforce. Verifica la URL y tu conexión.', 'error')"></script>
</body>
</html>
