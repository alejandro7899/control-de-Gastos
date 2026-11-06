# Mi casa — instalación y sincronización

## Instalar en iPhone

1. Publicá el contenido de esta carpeta en un sitio con HTTPS. Safari solo puede instalar la app web desde una dirección segura; abrir el archivo HTML directamente no alcanza.
2. En el iPhone, abrí esa dirección en **Safari**.
3. Tocá **Compartir → Añadir a pantalla de inicio → Añadir**.

La app abre desde el icono y conserva los datos localmente. El sitio publicado debe mantener juntos `index.html`, `manifest.webmanifest`, `sw.js`, `icon.svg` y `apple-touch-icon.png`.

## Preparar Google Drive

1. En Google Cloud Console, creá un proyecto, habilitá **Google Drive API** y configurá la pantalla de consentimiento de OAuth.
2. Creá un ID de cliente OAuth de tipo **Aplicación web** y agregá el dominio HTTPS publicado como origen autorizado.
3. Abrí **Datos y sincronización** en la app, pegá el ID de cliente y elegí **Conectar cuenta**.
4. Repetí la conexión en la notebook y el iPhone con el mismo ID de cliente y la misma cuenta de Google.

La aplicación guarda un archivo JSON privado en el espacio de datos de la aplicación de Drive. Google solicitará autorización en cada dispositivo. El token de acceso es temporal; si vence, volvé a tocar **Conectar cuenta**. Al volver a conectar, la app combina altas y ediciones por movimiento y propaga los borrados. Para abrir la app en más dispositivos, usá el mismo sitio HTTPS.

El ID de cliente es público en las aplicaciones web y no es una contraseña. No pegues una clave secreta OAuth en la app.

## Descargar

`mi-casa-pwa.zip` contiene los archivos necesarios para publicar la aplicación. No es un archivo IPA: en iPhone se instala como aplicación web desde Safari.
