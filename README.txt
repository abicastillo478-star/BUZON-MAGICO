BUZÓN MÁGICO 3.0 — instrucciones

QUÉ INCLUYE
- Sitio web con buzones de Santa Claus y Reyes Magos.
- Formulario para niños y para madres/padres/tutores.
- Contexto opcional de la familia para personalizar la respuesta.
- Animación de sobre/carta y reproductor preparado para videos.
- Servidor Flask que llama a la API de OpenAI cuando se configura una clave.
- Sin base de datos ni almacenamiento propio de cartas. La petición a la API usa store=False.

PUBLICAR EN RENDER
1. Sube TODO el contenido de esta carpeta al repositorio GitHub:
   app.py, requirements.txt, render.yaml, .env.example, README.txt y la carpeta templates.
2. En Render crea un New Web Service conectado al repositorio.
3. Configuración:
   Build Command: pip install -r requirements.txt
   Start Command: gunicorn app:app
4. En Environment agrega OPENAI_API_KEY como variable secreta.
   No la pongas en GitHub, HTML ni mensajes públicos.
5. OPENAI_MODEL puede quedarse como gpt-4.1-mini.
6. Abre la URL de Render. GitHub Pages por sí solo no ejecuta el servidor Python.

IA Y COSTOS
- Sin OPENAI_API_KEY, el sitio funciona en modo de demostración con una respuesta fija.
- Con una clave válida, genera respuestas personalizadas usando la API de OpenAI.
- El uso de la API puede tener costo y requiere una cuenta/API billing configurada por una persona adulta responsable.
- Revisa límites de gasto y supervisa el uso.

VIDEOS
El reproductor está preparado, pero esta entrega NO incluye videos cinematográficos reales.
Para activarlos, añade MP4 con derechos/permisos de uso a static/ y enlázalos en templates/index.html.
Los videos pregrabados no dirán automáticamente el nombre ni leerán el contenido de cada carta.
Para video hablado realmente personalizado se necesita un servicio adicional de voz/video, que también puede tener costo y debe revisarse antes de integrarlo.

PRIVACIDAD Y CUIDADO
- No se guardan cartas en una base de datos de este proyecto; la llamada a la API solicita store=False.
- El texto sí se envía al proveedor de IA para generar la respuesta. No prometas confidencialidad absoluta.
- No pidas apellidos, direcciones, escuela, teléfono, fotos ni otros datos sensibles de menores.
- Las cartas no sustituyen hablar con una persona adulta de confianza si algo preocupa al niño.
