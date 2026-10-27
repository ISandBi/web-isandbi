# ISANDBI Solutions

Landing page de consultoría digital hecha con Astro. La página presenta servicios de desarrollo
web y móvil, escalamiento, uso de inteligencia artificial, colaboración personalizada y un
formulario de contacto.

## Desarrollo local

Abre PowerShell o una terminal en la carpeta del proyecto (`F:\isandbi-solutions`) y ejecuta:

```sh
npm install
npm run dev -- --host 0.0.0.0
```

Cuando Astro indique que el servidor está listo, abre **http://localhost:4321** en tu navegador.
Mantén la terminal abierta mientras ves el sitio; para detener el servidor, presiona `Ctrl+C`.
Al guardar cambios en el código, el navegador actualiza la página automáticamente.

Si solo necesitas verlo en esta computadora, también puedes iniciar el servidor con `npm run dev`.

### Compilar la versión final

Para generar la versión de producción:

```sh
npm run build
```

Para previsualizar localmente la compilación, ejecuta:

```sh
npm run preview
```

Después abre **http://localhost:4321** en el navegador. El servidor de previsualización se detiene
con `Ctrl+C`.

## Fotografías de portada

Agrega tus imágenes dentro de `public/images/` con estos nombres. La página muestra un espacio
de reserva hasta que el archivo correspondiente esté disponible:

- `public/images/equipo-consultoria.jpg`
- `public/images/desarrollo-web.jpg`
- `public/images/apps-moviles.jpg`
- `public/images/reunion-presencial.jpg`

Si prefieres otros nombres, cambia las rutas del arreglo `photos` en `src/pages/index.astro`.
Los archivos de `public/` se sirven desde la raíz del sitio; por ejemplo, `public/images/equipo-consultoria.jpg`
se muestra con la ruta `/images/equipo-consultoria.jpg`.

## Formulario de contacto

El formulario envía nombre, correo, servicio y mensaje a `mauricio.garro@ilb.edu.mx` mediante
[FormSubmit](https://formsubmit.co/). Al publicar el sitio, envía el primer mensaje de prueba y
confirma la activación desde el correo que FormSubmit mande a esa bandeja. Después de activarlo,
los envíos posteriores llegarán a ese correo. FormSubmit procesa los datos del formulario como
servicio externo; no se necesita configurar un servidor propio.

Para cambiar el destinatario, actualiza `contactEmail` en `src/pages/index.astro`.

## Lógica sencilla incluida

- **Tema claro/oscuro:** el navegador carga el tema guardado en `localStorage` o, si aún no se
  eligió uno, usa la preferencia del sistema. El botón del encabezado alterna el tema y guarda
  la selección para la siguiente visita.
- **Espacios para fotografías:** cuando una imagen ya existe en `public/images/`, se muestra en su
  espacio. Si todavía no existe, la página conserva una tarjeta de reserva con la ruta esperada.
- **Envío del formulario:** los campos obligatorios y el correo se validan en el navegador; el
  formulario se envía al servicio de correo al presionar el botón.
