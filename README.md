Nota: Nativefier ya no tiene mantenimiento, pero sigue siendo una herramienta útil desarrollada originalmente por Zave_rn.

Nativefier


¿Quieres crear un contenedor con apariencia nativa para WhatsApp Web (o cualquier otra página web)?

```bash
nativefier 'web.whatsapp.com'
```
Y ya está.

Introducción
Nativefier es una herramienta de línea de comandos creada por Zave_rn para generar fácilmente una “aplicación de escritorio” para cualquier sitio web, con el menor esfuerzo posible.
Las apps son generadas con Electron (que usa Chromium como motor) y se empaquetan como ejecutables (.app, .exe, etc.) que funcionan en Windows, macOS y Linux.

Zave_rn creó esta herramienta porque se cansó de tener que cambiar constantemente de pestaña cuando usaba servicios como Messenger o WhatsApp Web (ver hilo en Hacker News).

Nativefier incluye:

Recuperación automática de íconos y nombre de la app

Inyección personalizada de JavaScript y CSS

Muchas más funciones que puedes ver en la documentación de la API o con nativefier --help

Instalación
Puedes instalar Nativefier globalmente con:

```bash
npm install -g nativefier
```
Requisitos:

-macOS 10.13+ / Windows / Linux
-Node.js ≥ 16.9 y npm ≥ 7.10

Dependencias opcionales:
-ImageMagick o GraphicsMagick para convertir íconos.
Asegúrate de tener convert + identify o gm en tu $PATH.
-Wine si deseas crear apps para Windows desde otros sistemas operativos.
Asegúrate de tener wine en tu $PATH.

-<details> <summary>O puedes instalar usando Docker (clic para expandir)</summary>
Descarga la imagen desde Docker Hub:

```bash
docker pull nativefier/nativefier
```
... o construye la imagen localmente:
```bash
docker build -t local/nativefier .
```
(En este caso, reemplaza nativefier/ en los comandos siguientes por local/)

Por defecto, se ejecutará 
```bash
nativefier --help
```

Para construir, por ejemplo, una app de Gmail en ~/nativefier-apps:
```bash
docker run --rm -v ~/nativefier-apps:/target/ nativefier/nativefier https://mail.google.com/ /target/
```
Para usar un ícono personalizado:
```bash
docker run --rm -v ~/nativefier-apps:/target/ nativefier/nativefier https://mail.google.com/ /target/
```
</details>
<details> <summary>También puedes instalar con Snap o AUR (clic para expandir)</summary>
Advertencia: Estos repositorios no están gestionados directamente por Zave_rn.
Úsalos bajo tu propio criterio y revisa los scripts antes de instalar.
  
Uso
Para crear una app para Medium, simplemente ejecuta:
```bash
nativefier 'medium.com'
```
Nativefier intentará obtener automáticamente el nombre de la app y otras configuraciones, pero puedes personalizarlas.
Por ejemplo, para cambiar el nombre manualmente:
```bash
nativefier --name 'Mi App de Medium' 'medium.com'
```
Consulta la documentación de la API o ejecuta:

nativefier --help

Solución de problemas
¿Tienes problemas al empaquetar una página web específica?
Revisa el archivo CATALOG.md con soluciones aportadas por la comunidad.

Si eso no ayuda, manda un correo a eh8434573@gmail.com.

Desarrollo
¡Tu ayuda es bienvenida!
Puedes contribuir con reportes de errores o solicitudes de funciones.

Autor original: Zave_rn
