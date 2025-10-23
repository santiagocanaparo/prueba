# App de Narrador de Historias con IA

## 1. Concepto General
La aplicación busca ofrecer una experiencia narrativa inmersiva y personalizada. El usuario introduce una idea inicial y la plataforma, impulsada por modelos de IA, genera el desarrollo completo del relato: texto, narración en voz e ilustraciones. Cada historia se construye de forma iterativa, permitiendo que el usuario influya en el transcurso de los eventos y disfrute de un cuento único en cada sesión.

> **¿Qué debes construir?** Una plataforma web donde, a partir de un prompt inicial, el usuario reciba texto, voz e imágenes generados por IA de forma coordinada y evolutiva.

## 2. Características Clave

### a. Generación de Historias (Motor de Texto)
- **Entrada de usuario flexible**:
  - Prompt simple: por ejemplo, "un gato astronauta que descubre un planeta de queso".
  - Selección de género: Fantasía, Ciencia Ficción, Misterio, Aventura, Comedia.
  - Personalización de personajes: nombre, rasgos de personalidad y características físicas.
  - Definición del entorno: descripción del mundo o escenario donde se desarrolla la historia.
- **Generación progresiva**: creación de la narrativa por párrafos o capítulos para mantener el interés y permitir ajustes.
- **Coherencia narrativa**: memoria contextual para preservar detalles relevantes y continuidad en la trama.

### b. Narración por Voz (Motor de Texto a Voz - TTS)
- **Múltiples voces**: selección de narradores con diferentes tonos, géneros y acentos.
- **Controles de reproducción**: botones de Play, Pausa y Detener para manejar la narración.
- **Sincronización de texto**: resaltado de palabras a medida que se narran, similar a un karaoke.

### c. Ilustraciones Automáticas (Motor de Imagen)
- **Generación por escena**: una ilustración distinta para cada párrafo o momento clave.
- **Estilos artísticos**: elección entre opciones como dibujo animado, realista, acuarela o pixel art.
- **Consistencia visual**: mantenimiento del estilo y características de personajes y escenarios a lo largo de la historia.

### d. Interactividad y Control del Usuario
- **Opciones "¿Qué pasa después?"**: decisiones ramificadas al final de cada segmento narrativo.
- **Botón "Continuar la historia"**: la IA retoma la trama desde el último punto.
- **Guardar y exportar**: posibilidad de almacenar historias con texto, imágenes y audio, además de exportar a PDF o video corto.

### e. Interfaz de Usuario (UI/UX)
- **Diseño limpio**: distribución en tres áreas principales (texto, visuales y controles).
- **Modo inmersivo**: visualización a pantalla completa con texto superpuesto a las ilustraciones.
- **Diseño responsivo**: adaptación a dispositivos de escritorio y móviles.

## 3. Flujo de Usuario (Ejemplo)
1. El usuario inicia la app y encuentra una caja de texto que invita a "Escribir el inicio de una historia".
2. Introduce el prompt: "Un detective robot en una lluviosa ciudad del futuro".
3. Pulsa "Crear" y la aplicación solicita a los motores de IA que generen el contenido.
4. La respuesta incluye:
   - Texto: primer párrafo del relato.
   - Imagen: ilustración correspondiente al fragmento narrado.
   - Audio: narración del párrafo con la voz seleccionada.
5. Al finalizar el segmento, aparecen opciones como "Continuar la historia" y "¿Qué quieres que haga ahora?".
6. El proceso se repite, construyendo un relato dinámico y personalizado en cada sesión.

## 4. MVP y Entregables por Fase

Para evitar confusiones, el trabajo se divide en fases progresivas. Cada fase debe cerrarse con un entregable funcional y demostrable.

| Fase | Objetivo | Alcance minimo | Indicador de finalizacion |
|------|----------|----------------|---------------------------|
| 1. Diseno | Validar idea y experiencia | Bocetos de UI, definicion de estilo visual, mock de flujo de usuario | Prototipo navegable en Figma o similar aprobado por stakeholders |
| 2. MVP Texto | Generar historias basicas | Prompt inicial, seleccion de genero, generacion capitulo a capitulo con memoria | Lectura fluida de dos iteraciones completas de historia |
| 3. MVP Voz | Anadir narracion TTS | Integracion con motor TTS, seleccion de voces, controles basicos | Reproduccion y pausa sincronizada con texto |
| 4. MVP Imagenes | Ilustraciones por escena | Generacion de imagen por parrafo, selector de estilo | Dos historias completas con ilustraciones consistentes |
| 5. Interactividad avanzada | Opciones ramificadas | Botones "Que pasa despues?" y continuidad condicionada | Usuario completa una historia eligiendo diferentes ramas |
| 6. Publicacion | Preparar lanzamiento | Guardado/exportacion, onboarding, metricas basicas | Beta cerrada disponible para usuarios reales |

## 5. Historias de Usuario Prioritarias

1. **Como usuario nuevo**, quiero introducir una idea breve y recibir el primer capítulo de mi historia para entender el potencial de la app.
2. **Como usuario que disfruta de audiocuentos**, quiero escoger la voz del narrador para sentir la historia más cercana a mis preferencias.
3. **Como usuario visual**, quiero elegir el estilo artístico de las ilustraciones para conectar mejor con el relato.
4. **Como creador curioso**, quiero decidir qué sucede a continuación para sentir que estoy co-creando la trama.
5. **Como usuario recurrente**, quiero guardar mis historias favoritas para revivirlas o compartirlas después.

## 6. Requerimientos Técnicos Sugeridos

- **Backend / APIs**: Node.js (NestJS, Express) o Python (FastAPI) para orquestar las llamadas a modelos de texto, voz e imagen.
- **Modelos de IA**: APIs de texto (GPT, Claude), TTS (Azure Speech, ElevenLabs), y generación de imágenes (DALL·E, Stable Diffusion). Abstraer la integración tras interfaces propias para facilitar sustituciones futuras.
- **Frontend**: React o Vue con componentes modulares para texto, controles de audio y galería de ilustraciones. Uso de Tailwind o Chakra UI para velocidad de iteración.
- **Persistencia**: Base de datos documental (MongoDB, Firestore) para almacenar historias, prompts y activos generados.
- **Estado y Sincronización**: WebSockets o Server-Sent Events para actualizar texto, audio e imágenes en tiempo real a medida que la IA responde.
- **Infraestructura**: Despliegue inicial en Vercel/Netlify (frontend) y Render/Fly.io (backend). Considerar colas (Redis) para tareas pesadas como renderizados de imagen.
- **Observabilidad**: Logging estructurado, métricas de uso (segmentación por género de historia, voces más usadas) y seguimiento de costos por llamada a API.

## 7. Próximos Pasos Claros

1. Validar el alcance del MVP con el equipo y ajustar el backlog si es necesario.
2. Definir stack tecnológico definitivo y crear repositorio monorepo o multi-repo según convenga.
3. Diseñar prototipo de alta fidelidad de la vista principal (texto + imagen + controles).
4. Implementar la fase 2 del MVP (motor de texto) con pruebas de coherencia narrativa y almacenamiento mínimo.
5. Documentar aprendizajes y bloqueos al finalizar cada fase para mejorar la siguiente iteración.

> Si en algún punto tienes dudas, revisa el entregable de la fase correspondiente: cada uno actúa como checklist para saber si puedes continuar a la siguiente etapa.

## 8. ¿Qué hacer si GitHub muestra "Apply changes and continue locally?"

Ese mensaje aparece cuando GitHub no puede aplicar automáticamente un parche porque el trabajo se originó en otro repositorio o la rama tiene cambios nuevos. Para continuar sin bloquearte, sigue estos pasos:

1. **Clona el repositorio correcto:**
   ```bash
   git clone git@github.com:santiagocanaparo/prueba.git
   cd prueba
   ```
   Si ya lo tienes clonado, asegúrate de hacer `git fetch --all` para traer los cambios más recientes.

2. **Crea una rama de trabajo:**
   ```bash
   git checkout -b fix/aplicar-cambios-local
   ```

3. **Sincroniza con la rama base:**
   ```bash
   git checkout main
   git pull origin main
   git checkout fix/aplicar-cambios-local
   git merge main
   ```
   Resuelve cualquier conflicto que aparezca durante el merge.

4. **Aplica manualmente los cambios:**
   - Copia el diff propuesto desde la interfaz de GitHub y pégalo en tus archivos.
   - O usa `git apply <archivo.diff>` si descargaste el parche.

5. **Prueba y valida localmente:** ejecuta los comandos necesarios para verificar que el proyecto sigue funcionando (por ejemplo, `npm test`, `npm run lint`, etc.).

6. **Haz commit y sube la rama:**
   ```bash
   git status
   git add .
   git commit -m "Describe el cambio aplicado"
   git push origin fix/aplicar-cambios-local
   ```

7. **Crea el Pull Request:** desde GitHub, abre un PR desde tu rama `fix/aplicar-cambios-local` hacia `main`.

> Consejo: si el parche viene de una tarea previa y sigue fallando, revisa el historial de commits para asegurarte de que los archivos de destino no cambiaron de ubicación o nombre.
