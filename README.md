Nota: Nativefier ya no tiene mantenimiento, por favor revisa otras alternativas.

Nativefier


Quieres crear un contenedor con apariencia nativa para WhatsApp Web (o cualquier página web).

bash
Copiar
Editar
nativefier 'web.whatsapp.com'


Y ya terminaste.

Introducción
Nativefier es una herramienta de línea de comandos para crear fácilmente una “aplicación de escritorio” para cualquier sitio web con el mínimo esfuerzo. Las aplicaciones se empaquetan usando Electron
(que usa Chromium internamente) en un ejecutable del sistema operativo (.app, .exe, etc.)
que funciona en Windows, macOS y Linux.

Creé esto porque me cansé de tener que usar Alt-Tab para volver al navegador y luego buscar
entre muchas pestañas abiertas cuando usaba Messenger o
WhatsApp Web (hilo en HN). Funcionalidades de Nativefier:

Recuperación automática del ícono / nombre de la app

Inyección de JS y CSS personalizados

Muchas más, revisa la documentación de la API o ejecuta nativefier --help

Instalación
Instala Nativefier globalmente con npm install -g nativefier . Requisitos:

macOS 10.13+ / Windows / Linux

Node.js ≥ 16.9 y npm ≥ 7.10

Dependencias opcionales:

ImageMagick o GraphicsMagick para convertir íconos.
Asegúrate de que convert + identify o gm estén en tu $PATH.

Wine para construir apps de Windows desde plataformas que no sean Windows.
Asegúrate de que wine esté en tu $PATH.

<details> <summary>O instalar con Docker (haz clic para expandir)</summary>
Descarga la imagen desde Docker Hub: docker pull nativefier/nativefier

... o constrúyela tú mismo: docker build -t local/nativefier .
(en este caso, reemplaza nativefier/ en los ejemplos de abajo con local/)

Por defecto, se ejecutará nativefier --help.
Para construir, por ejemplo, una app de Gmail en ~/nativefier-apps,

bash
Copiar
Editar
docker run --rm -v ~/nativefier-apps:/target/ nativefier/nativefier https://mail.google.com/ /target/
Puedes pasarle opciones a Nativefier y montar volúmenes para pasar archivos locales. Por ejemplo, para usar un ícono:

bash
Copiar
Editar
docker run --rm -v ~/mi-carpeta-de-iconos/:/src -v $RUTA-DESTINO:/target nativefier/nativefier --icon /src/icon.png --name whatsApp -p linux -a x64 https://web.whatsapp.com/ /target/
</details> <details> <summary>O instalar con Snap y AUR (haz clic para expandir)</summary>
Estos repositorios no son mantenidos por los desarrolladores de Nativefier; úsalos bajo tu propio riesgo.
Por tu seguridad, inspecciona el script de construcción.

Snap

AUR

</details>
Uso
Para crear una app para medium.com, simplemente:

bash
Copiar
Editar
nativefier 'medium.com'
Nativefier intentará determinar el nombre de la app, así como otras opciones que puedes sobrescribir.
Por ejemplo, para sobrescribir el nombre:

bash
Copiar
Editar
nativefier --name 'Mi App de Medium' 'medium.com'
Lee la documentación de la API o ejecuta nativefier --help
para aprender sobre los flags disponibles y cómo configurar tu app.

Solución de problemas
Revisa CATALOG.md para ideas y soluciones específicas para sitios, aportadas por la comunidad.

Si eso no ayuda, revisa nuestro seguimiento de problemas.

Desarrollo
¡Se agradece ayuda en errores y
solicitudes de funciones!

Documentación: Desarrollo / compilación / hackeo, API / opciones,
Registro de cambios

Licencia: MIT
