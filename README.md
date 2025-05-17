Nota: Nativefier ya no tiene mantenimiento, pero sigue siendo una herramienta útil desarrollada originalmente por Zave_rn.

Nativefier


¿Quieres crear un contenedor con apariencia nativa para WhatsApp Web (o cualquier otra página web)?

bash
Copiar
Editar
nativefier 'web.whatsapp.com'


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

bash
Copiar
Editar
npm install -g nativefier
Requisitos
macOS 10.13+, Windows o Linux

Node.js ≥ 16.9 y npm ≥ 7.10

Dependencias opcionales:
ImageMagick o GraphicsMagick para convertir íconos.
Asegúrate de tener convert + identify o gm en tu $PATH.

Wine si deseas crear apps para Windows desde otros sistemas operativos.
Asegúrate de tener wine en tu $PATH.

<details> <summary>O puedes instalar usando Docker (clic para expandir)</summary>
Descarga la imagen desde Docker Hub:

bash
Copiar
Editar
docker pull nativefier/nativefier
... o construye la imagen localmente:

bash
Copiar
Editar
docker build -t local/nativefier .
(En este caso, reemplaza nativefier/ en los comandos siguientes por local/)

Por defecto, se ejecutará nativefier --help.

Para construir, por ejemplo, una app de Gmail en ~/nativefier-apps:

bash
Copiar
Editar
docker run --rm -v ~/nativefier-apps:/target/ nativefier/nativefier https://mail.google.com/ /target/
Para usar un ícono personalizado:

bash
Copiar
Editar
docker run --rm -v ~/mi-carpeta-de-iconos/:/src -v $RUTA_DESTINO:/target nativefier/nativefier --icon /src/icon.png --name WhatsApp -p linux -a x64 https://web.whatsapp.com/ /target/
</details>
<details> <summary>También puedes instalar con Snap o AUR (clic para expandir)</summary>
Advertencia: Estos repositorios no están gestionados directamente por Zave_rn ni el equipo original de Nativefier.
Úsalos bajo tu propio criterio y revisa los scripts antes de instalar.

Snap

AUR (Arch Linux)

</details>
Uso
Para crear una app para Medium, simplemente ejecuta:

bash
Copiar
Editar
nativefier 'medium.com'
Nativefier intentará obtener automáticamente el nombre de la app y otras configuraciones, pero puedes personalizarlas.
Por ejemplo, para cambiar el nombre manualmente:

bash
Copiar
Editar
nativefier --name 'Mi App de Medium' 'medium.com'
Consulta la documentación de la API o ejecuta:

bash
Copiar
Editar
nativefier --help
Solución de problemas
¿Tienes problemas al empaquetar una página web específica?
Revisa el archivo CATALOG.md con soluciones aportadas por la comunidad.

Si eso no ayuda, revisa los issues en GitHub.

Desarrollo
¡Tu ayuda es bienvenida!
Puedes contribuir con reportes de errores o solicitudes de funciones.

Documentación para desarrolladores:

Guía para desarrolladores / compilación / hacking

Documentación de la API / flags

Registro de cambios (changelog)

Licencia: MIT
Autor original: Zave_rn
