# Escenario multiagente · El Colorado, Formosa
**Matecito Curioso · Ares · Arthur Schopenhauer**, tres humanos digitales con su propio agente de ElevenLabs, conversando junto al puente de El Colorado. Es el **Paso 2** del Instructivo N.° 42 (Escenario multiagente).

## Qué hay en la carpeta
| Archivo | Para qué sirve |
| --- | --- |
| `index.html` | El escenario: set con la foto del puente, cámaras, director de turnos y las cinco pestañas |
| `personajes/matecito.html`, `ares.html`, `arthur.html` | Cada humano digital (se cargan solos dentro del escenario; también andan por separado) |
| `img/fondo-el-colorado.jpg` | La foto de fondo |
| `guiones/*.txt` | Tres guiones de ejemplo |

## Publicarlo en GitHub Pages
1. Creá un repositorio público y subí **toda la carpeta**, con sus subcarpetas (`personajes`, `img`, `guiones`). Si subís desde la web: **Add file → Upload files**, arrastrando la carpeta completa.
2. **Settings → Pages → Deploy from a branch → main → / (root) → Save**.
3. Abrí `https://TU_USUARIO.github.io/NOMBRE_DEL_REPO/`. Tiene que ser **https**: el micrófono no anda con el archivo suelto.

## Los agentes
| Personaje | Agente |
| --- | --- |
| Ares | `agent_2101m4f68aj1fh8ankzf7cwrh370` (ya cargado) |
| Arthur Schopenhauer | `agent_8701m4s376jmfq4tybga1q3e9ana` (ya cargado) |
| Matecito Curioso | **falta**: todavía no se creó su agente de ElevenLabs |

Para sumar a Matecito en vivo: creá su agente (prompt y base de la habilidad `matecito-curioso`, y para el escenario agregale el «Texto para modo escenario») y pegá el ID en `index.html`, en `const AGENTES`, en `matecito: ''`. Para probar sin editar: `index.html?matecito=agent_...`.
Sin agente, Matecito igual participa en los guiones (pestañas Capítulo y Short) con la voz del dispositivo.
Los agentes tienen que ser **públicos** (ElevenLabs → *Security*, sin autenticación). Si usás lista de dominios, agregá `TU_USUARIO.github.io`.

## Cómo se usa cada pestaña (según el instructivo)
- **En vivo:** tocá **Empezar la charla**. Conecta a los personajes de a uno (cada uno se presenta), y después Matecito arranca la ronda y se van respondiendo entre sí. Podés escribirles, o hablarles con **Hablar yo** (elegís a quién). Hay un tope de turnos para cuidar los créditos y un botón **Seguir la ronda**. Abajo podés practicar sin gastar créditos con **Escuchar sin conexión**.
- **Idea → Guion:** escribí tu idea y armá un esqueleto, o tocá **Copiar pedido para Claude** y traé el guion que te devuelva. También hay tres ejemplos listos. Formato: `NOMBRE: texto`, más `[título: …]`, `[plano: general|dos|matecito|ares|arthur]` y `[pausa: 1.5]`.
- **Capítulo 16:9:** reproduce el guion como pequeña historia cinematográfica, con tarjeta de título, cámaras automáticas y créditos. Se graba con el segundo dispositivo, como en el Paso 1.
- **Short 9:16:** lo mismo en vertical, con la cámara siguiendo a quien habla.
- **YouTube:** título y descripción para copiar (con el aviso de IA y los créditos) y generador de miniatura 1280×720 con los personajes, para descargar en PNG.

## Entrega (Instructivo N.° 42, Paso 2)
- [ ] Video de la charla en vivo con los personajes **o** de la pequeña historia (MP4 16:9 o 9:16), nombrado `42_Apellido_Nombre_Paso2`.
- [ ] El enlace de GitHub Pages del escenario.

## Ajustar el set (`?calibrar=1`)
Abrí `…/index.html?calibrar=1`: aparece un panel con deslizadores para mover y agrandar a cada personaje y para subir o bajar el borde de la baranda. Se guarda en tu navegador y copia los valores para pegarlos en `P` y `BANDA` dentro de `index.html`. **Hacelo en la primera prueba**: las posiciones están calculadas a ojo sobre la foto.

## Si algo falla
| Problema | Qué hacer |
| --- | --- |
| Un personaje no habla | Agente público (Security) y dominio permitido; permitir el micrófono |
| `voice_not_found` | Agregar la voz al espacio de trabajo desde la Voice Library y elegirla de nuevo |
| No aparece un personaje | Revisá que exista su archivo en `personajes/` y que la carpeta se haya subido completa |
| Varios responden a la vez cuando hablás | La librería no permitió silenciar cada micrófono; usá el cuadro de texto |
| Se ve la foto pero no los personajes | Esperá unos segundos (cargan Three.js) y revisá la conexión; probá con otro navegador |
| Aparece un cartel «Error: …» | Copiá el texto exacto y pasáselo a Claude junto con el modelo de celular y el navegador |

## Cómo está armado
El escenario es una **página director**: ubica a cada humano digital en una ventana transparente sobre la foto (Arthur queda detrás de la baranda; Matecito está sobre ella; Ares, en la rama del árbol), mueve la cámara y reparte los turnos. Cada personaje abre su propia sesión con su agente. Cuando uno termina de hablar, el director le pasa lo que dijo al siguiente como mensaje de texto (y avisa al tercero); no hay audio mezclado. En las pestañas Capítulo y Short, las voces salen del dispositivo y la boca se sincroniza igual.
Los personajes se abren con `?escena=1` (sin panel, con fondo transparente). Sin ese parámetro funcionan como siempre.

## Uso ético y responsable
- **Transparencia:** los tres personajes son recreaciones hechas con IA y lo dicen si se les pregunta; está escrito en pantalla, en los créditos y en la descripción de YouTube.
- **Consentimiento:** no se clonan voces ni se usan caras de personas sin permiso por escrito. Nada de deepfakes.
- **Datos personales (Ley 25.326):** la voz viaja a los servidores de ElevenLabs; no compartas datos sensibles.
- **Respeto cultural:** si sumás saberes o personajes pilagá o qom, con fuentes, sin estereotipos y consultando a la comunidad.
- **Costos:** en vivo, cada minuto consume créditos por cada agente conectado. Practicá sin conexión.
- **Foto de fondo:** usá solo imágenes propias o con permiso, y completá la autoría en los créditos y en la descripción de YouTube (hoy dice «completar autoría»).
- Alineado con la Recomendación sobre la Ética de la IA de la UNESCO (2021).

## Qué se probó y qué no
- **Probado:** la página del escenario (set, capas, cámaras, pestañas, director de turnos, guiones, miniatura), usando personajes de mentira que imitan el protocolo, en un navegador real.
- **No probado:** que los tres personajes 3D reales se vean bien dentro del set (en el entorno donde se armó no se podía cargar Three.js ni conectar con ElevenLabs), las conversaciones reales en vivo, y la sincronía de turnos con agentes de verdad. Revisá primero: tamaño y posición de cada personaje (usá `?calibrar=1`), que Ares se vea bien en la rama, y que los micrófonos se silencien por personaje.
- Arthur Schopenhauer se reconstruyó desde su ficha (el motor estándar), así que **no trae la biblioteca ni los gestos extra** (brazos cruzados, mano en la sien) de su versión original.
- Matecito y Arthur usan el motor de la habilidad `humano-digitales`; Ares, su propia página.
