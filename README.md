# RecordWav

[English version](#english)

## Español

RecordWav es una extensión para Google Chrome y navegadores basados en Chromium que captura el audio de la pestaña activa y lo guarda directamente como un archivo WAV PCM de 24 bits y 48 kHz.

Todo el procesamiento ocurre localmente en el navegador. RecordWav no necesita servidores, codecs adicionales, herramientas de conversión ni conexión a Internet para generar el archivo WAV.

Sitio oficial: [www.alientostudio.com](https://www.alientostudio.com)

### Características

- Captura exclusivamente el audio de la pestaña activa.
- Mantiene audible el contenido de la pestaña durante la grabación.
- Calidad fija: WAV PCM de 24 bits y 48 kHz.
- Grabación seleccionable en mono o estéreo.
- Carpeta de destino elegida por el usuario.
- Nombre de archivo personalizable.
- Nombre automático con fecha y hora cuando no se especifica uno.
- El nombre y la configuración quedan visibles y bloqueados durante la grabación.
- El botón de grabación permanece deshabilitado hasta seleccionar una carpeta.
- Notificación verde cuando el archivo se guarda correctamente.
- Notificación roja cuando la captura o el guardado falla.
- Escritura progresiva para evitar almacenar toda la grabación en memoria.
- Sin telemetría, publicidad ni subida de archivos.

### Compatibilidad

RecordWav requiere Google Chrome 116 o una versión posterior. También puede utilizarse en navegadores recientes basados en Chromium que admitan las APIs necesarias para capturar pestañas y escribir archivos.

| Navegador | Compatibilidad |
|---|---|
| Google Chrome 116 o posterior | Compatible |
| Chromium 116 o posterior | Compatible |
| Microsoft Edge basado en Chromium | Compatible |
| Brave | Compatible |
| Opera | Compatible |
| Vivaldi | Compatible |

### Sistemas operativos

| Sistema | Compatibilidad |
|---|---|
| Windows 10 y 11 | Compatible |
| Linux | Compatible |
| macOS | Compatible |

La extensión utiliza APIs de Chrome y tecnologías web estándar. No depende de comandos, rutas o programas exclusivos de un sistema operativo.

### Formato de salida

| Propiedad | Valor |
|---|---|
| Contenedor | WAV (RIFF) |
| Codificación | PCM lineal con signo |
| Profundidad | 24 bits por muestra |
| Frecuencia de muestreo | 48 000 Hz |
| Canales | 1 mono o 2 estéreo |
| Orden de bytes | Little-endian |
| Extensión | `.wav` |

Los archivos generados son compatibles con reproductores, editores y estaciones de trabajo de audio digital que admitan WAV PCM estándar.

### Instalación manual

1. Descarga y descomprime RecordWav.
2. Abre `chrome://extensions`.
3. Activa el **Modo de desarrollador** en la esquina superior derecha.
4. Pulsa **Cargar descomprimida**.
5. Selecciona la carpeta que contiene `manifest.json`.
6. Fija RecordWav en la barra de herramientas para acceder rápidamente.

Cuando actualices los archivos de la extensión, no es necesario eliminarla ni volver a instalarla. Abre `chrome://extensions` y pulsa **Recargar** en la tarjeta de RecordWav.

### Uso

1. Abre la pestaña cuyo audio quieres grabar.
2. Pulsa el icono de RecordWav.
3. Selecciona la carpeta de destino y concede permiso de escritura.
4. Vuelve a abrir RecordWav si el selector de carpetas cerró el popup.
5. Elige **Mono** o **Estéreo**.
6. Escribe el nombre del archivo o conserva el nombre automático.
7. Pulsa **Iniciar grabación**.
8. Reproduce normalmente el contenido de la pestaña.
9. Abre RecordWav y pulsa **Detener y guardar**.
10. Espera el mensaje verde que confirma que el WAV fue guardado.

La grabación continúa aunque el popup de la extensión se cierre. El nombre del archivo permanece asociado a la captura hasta que termina el proceso.

### Carpeta de destino

Chrome solicita autorización explícita antes de permitir que RecordWav escriba en una carpeta. Por privacidad, la extensión puede mostrar el nombre de la carpeta autorizada, pero Chrome no entrega su ruta absoluta completa.

El navegador puede solicitar acceso nuevamente cuando el permiso expira, se revoca o cambia la sesión. Si esto ocurre, selecciona otra vez la carpeta antes de iniciar una grabación.

Chrome cierra automáticamente el popup de una extensión cuando se abre el selector nativo de carpetas. Este comportamiento pertenece al navegador. Después de seleccionar la carpeta, vuelve a pulsar el icono de RecordWav para continuar.

### Mensajes de estado

- Azul: operación en curso, como iniciar, grabar o guardar.
- Verde: el archivo WAV se guardó correctamente.
- Rojo: ocurrió un problema durante la captura, procesamiento o escritura.

El cuadro de mensajes permanece oculto cuando no existe información relevante.

### Privacidad

RecordWav procesa el audio completamente en tu dispositivo:

- No envía grabaciones a Internet.
- No utiliza servidores de conversión.
- No recopila contenido de audio.
- No requiere una cuenta.
- No añade marcas de agua.
- No incluye telemetría ni seguimiento.

El acceso a la pestaña y a la carpeta solo se utiliza para realizar la grabación solicitada por el usuario.

### Permisos de Chrome

| Permiso | Uso |
|---|---|
| `activeTab` | Identificar la pestaña elegida por el usuario |
| `tabCapture` | Capturar el flujo de audio de la pestaña activa |
| `offscreen` | Mantener el motor de audio mientras el popup está cerrado |
| `storage` | Conservar temporalmente la carpeta, el nombre y el estado |

RecordWav no solicita acceso permanente al historial ni al contenido completo de todas las páginas.

### Tamaño aproximado

WAV PCM no utiliza compresión, por lo que conserva la calidad a cambio de archivos más grandes.

| Configuración | Tamaño aproximado por minuto |
|---|---|
| Mono, 24 bits, 48 kHz | 8,6 MB |
| Estéreo, 24 bits, 48 kHz | 17,3 MB |

El tamaño puede variar ligeramente por la duración exacta y el encabezado WAV.

### Limitaciones conocidas

- Captura la pestaña seleccionada, no el micrófono ni todo el audio del sistema.
- Algunas páginas internas de Chrome no permiten capturar audio.
- Ciertos contenidos protegidos pueden bloquear o limitar la captura.
- Chrome puede revocar el permiso de la carpeta y solicitarlo nuevamente.
- El formato RIFF/WAV estándar tiene un límite cercano a 4 GB por archivo.
- Para sesiones muy largas, detén la grabación e inicia un archivo nuevo antes de alcanzar el límite.

### Solución de problemas

#### El botón de grabación está deshabilitado

Selecciona primero una carpeta de destino. RecordWav no permite iniciar hasta tener un destino autorizado.

#### No se captura ningún audio

Comprueba que la pestaña esté reproduciendo sonido y que no sea una página interna o protegida de Chrome. Detén cualquier otra captura activa y vuelve a intentarlo.

#### Chrome solicita otra vez la carpeta

El permiso guardado expiró o fue revocado. Selecciona nuevamente la carpeta y concede acceso de escritura.

#### El archivo no aparece inmediatamente

Espera la confirmación verde. RecordWav debe vaciar las muestras pendientes, completar el encabezado WAV y cerrar el archivo antes de confirmar el guardado.

#### La extensión fue actualizada

Abre `chrome://extensions` y pulsa **Recargar**. No es necesario borrar ni reinstalar RecordWav.

### Arquitectura

RecordWav utiliza:

- Manifest V3.
- `chrome.tabCapture` para obtener el audio de la pestaña.
- Un documento offscreen para mantener el proceso fuera del popup.
- Web Audio API para enrutar y conservar audible el audio.
- AudioWorklet para mezclar canales y agrupar muestras eficientemente.
- Conversión Float32 a PCM firmado de 24 bits.
- Escritura progresiva con posiciones explícitas.
- Encabezado RIFF/WAV completado al detener la grabación.
- `chrome.storage.session` para conservar el estado de la captura.
- IndexedDB para almacenar la referencia autorizada de la carpeta.

Las muestras se agrupan antes de escribirse para reducir operaciones de disco. Si el guardado falla, la extensión libera los recursos y muestra el error en lugar de confirmar un archivo incompleto.

### Estructura del proyecto

```text
recordwav/
├── aliento.ttf          # Tipografía del logotipo
├── manifest.json        # Configuración Manifest V3
├── offscreen.html       # Documento de captura en segundo plano
├── offscreen.js         # Captura, PCM de 24 bits y escritura WAV
├── pcm-processor.js     # AudioWorklet para procesar muestras
├── popup.css            # Diseño de la interfaz
├── popup.html           # Interfaz de RecordWav
├── popup.js             # Controles, carpeta y mensajes
├── service-worker.js    # Coordinación y estado de la grabación
└── README.md            # Documentación
```

### Desarrollo

El proyecto utiliza JavaScript, HTML y CSS nativos. No necesita `npm install`, empaquetador ni proceso de compilación.

Después de modificar el código:

1. Abre `chrome://extensions`.
2. Pulsa **Recargar** en RecordWav.
3. Abre una pestaña con audio.
4. Realiza una grabación de prueba.
5. Comprueba que el archivo sea WAV PCM de 24 bits y 48 kHz.

### Créditos

RecordWav es un proyecto de [Aliento Studio](https://www.alientostudio.com).

---

## English

RecordWav is an extension for Google Chrome and Chromium-based browsers that captures audio from the active tab and saves it directly as a 24-bit, 48 kHz PCM WAV file.

All processing happens locally inside the browser. RecordWav does not require servers, additional codecs, conversion tools, or an Internet connection to generate the WAV file.

Official website: [www.alientostudio.com](https://www.alientostudio.com)

### Features

- Captures audio exclusively from the active tab.
- Keeps tab content audible while recording.
- Fixed quality: 24-bit, 48 kHz PCM WAV.
- Selectable mono or stereo recording.
- User-selected destination folder.
- Customizable filename.
- Automatic timestamped filename when no name is provided.
- Filename and settings remain visible and locked while recording.
- The recording button remains disabled until a folder is selected.
- Green notification when the file is saved successfully.
- Red notification when capture or saving fails.
- Progressive writing avoids keeping the entire recording in memory.
- No telemetry, advertising, or file uploads.

### Compatibility

RecordWav requires Google Chrome 116 or later. It can also run on recent Chromium-based browsers that support the required tab capture and file writing APIs.

| Browser | Support |
|---|---|
| Google Chrome 116 or later | Supported |
| Chromium 116 or later | Supported |
| Chromium-based Microsoft Edge | Supported |
| Brave | Supported |
| Opera | Supported |
| Vivaldi | Supported |

### Operating systems

| System | Support |
|---|---|
| Windows 10 and 11 | Supported |
| Linux | Supported |
| macOS | Supported |

The extension uses Chrome APIs and standard web technologies. It does not depend on commands, paths, or programs exclusive to a specific operating system.

### Output format

| Property | Value |
|---|---|
| Container | WAV (RIFF) |
| Encoding | Signed linear PCM |
| Bit depth | 24 bits per sample |
| Sample rate | 48,000 Hz |
| Channels | 1 mono or 2 stereo |
| Byte order | Little-endian |
| File extension | `.wav` |

Generated files are compatible with media players, audio editors, and digital audio workstations that support standard PCM WAV files.

### Manual installation

1. Download and extract RecordWav.
2. Open `chrome://extensions`.
3. Enable **Developer mode** in the top-right corner.
4. Click **Load unpacked**.
5. Select the folder containing `manifest.json`.
6. Pin RecordWav to the toolbar for quick access.

When extension files are updated, you do not need to remove or reinstall it. Open `chrome://extensions` and click **Reload** on the RecordWav card.

### Usage

1. Open the tab whose audio you want to record.
2. Click the RecordWav icon.
3. Select the destination folder and grant write permission.
4. Reopen RecordWav if the folder picker closed the popup.
5. Choose **Mono** or **Stereo**.
6. Enter a filename or keep the automatically generated name.
7. Click **Start recording**.
8. Play the tab content normally.
9. Open RecordWav and click **Stop and save**.
10. Wait for the green message confirming that the WAV file was saved.

Recording continues when the extension popup closes. The selected filename remains associated with the capture until processing finishes.

### Destination folder

Chrome requires explicit authorization before RecordWav can write to a folder. For privacy, the extension can display the authorized folder name, but Chrome does not expose its complete absolute path.

The browser may request access again when permission expires, is revoked, or the session changes. If this happens, select the folder again before starting a recording.

Chrome automatically closes extension popups when the native folder picker opens. This is browser behavior. After choosing the folder, click the RecordWav icon again to continue.

### Status messages

- Blue: an operation is in progress, such as starting, recording, or saving.
- Green: the WAV file was saved successfully.
- Red: a problem occurred during capture, processing, or writing.

The message box remains hidden when there is no relevant information.

### Privacy

RecordWav processes audio entirely on your device:

- Recordings are never uploaded to the Internet.
- No conversion servers are used.
- Audio content is not collected.
- No account is required.
- No watermarks are added.
- No telemetry or tracking is included.

Tab and folder access is used only to perform the recording requested by the user.

### Chrome permissions

| Permission | Purpose |
|---|---|
| `activeTab` | Identifies the tab selected by the user |
| `tabCapture` | Captures the active tab audio stream |
| `offscreen` | Keeps the audio engine running while the popup is closed |
| `storage` | Temporarily preserves the folder, filename, and recording state |

RecordWav does not request permanent access to browsing history or the complete content of every page.

### Approximate file size

PCM WAV is uncompressed, preserving quality at the cost of larger files.

| Configuration | Approximate size per minute |
|---|---|
| Mono, 24-bit, 48 kHz | 8.6 MB |
| Stereo, 24-bit, 48 kHz | 17.3 MB |

File size may vary slightly due to exact duration and the WAV header.

### Known limitations

- RecordWav captures the selected tab, not the microphone or all system audio.
- Some internal Chrome pages do not allow audio capture.
- Certain protected content may block or restrict capture.
- Chrome may revoke folder permission and request it again.
- Standard RIFF/WAV files have a limit of approximately 4 GB per file.
- For very long sessions, stop recording and start a new file before reaching the limit.

### Troubleshooting

#### The recording button is disabled

Select a destination folder first. RecordWav cannot start without an authorized destination.

#### No audio is captured

Make sure the tab is playing audio and is not an internal or protected Chrome page. Stop any other active capture and try again.

#### Chrome requests the folder again

The stored permission expired or was revoked. Select the folder again and grant write access.

#### The file does not appear immediately

Wait for the green confirmation. RecordWav must flush pending samples, complete the WAV header, and close the file before confirming success.

#### The extension was updated

Open `chrome://extensions` and click **Reload**. RecordWav does not need to be removed or reinstalled.

### Architecture

RecordWav uses:

- Manifest V3.
- `chrome.tabCapture` to obtain tab audio.
- An offscreen document to keep processing outside the popup.
- Web Audio API to route audio and keep it audible.
- AudioWorklet to mix channels and batch samples efficiently.
- Float32 to signed 24-bit PCM conversion.
- Progressive writing with explicit file positions.
- A RIFF/WAV header completed when recording stops.
- `chrome.storage.session` to preserve capture state.
- IndexedDB to store the authorized folder reference.

Samples are batched before writing to reduce disk operations. If saving fails, the extension releases its resources and displays the error instead of confirming an incomplete file.

### Project structure

```text
recordwav/
├── aliento.ttf          # Logo typeface
├── manifest.json        # Manifest V3 configuration
├── offscreen.html       # Background capture document
├── offscreen.js         # Capture, 24-bit PCM, and WAV writing
├── pcm-processor.js     # AudioWorklet sample processor
├── popup.css            # Interface styles
├── popup.html           # RecordWav interface
├── popup.js             # Controls, folder, and messages
├── service-worker.js    # Recording coordination and state
└── README.md            # Documentation
```

### Development

The project uses native JavaScript, HTML, and CSS. It does not require `npm install`, a bundler, or a build process.

After changing the code:

1. Open `chrome://extensions`.
2. Click **Reload** on RecordWav.
3. Open a tab that plays audio.
4. Make a test recording.
5. Confirm that the file is a 24-bit, 48 kHz PCM WAV.

### Credits

RecordWav is a project by [Aliento Studio](https://www.alientostudio.com).
