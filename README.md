# ISANDBI Solutions

Landing page corporativa de IS&BI hecha con Astro. Presenta servicios, proyectos digitales con
capturas amplias, filtros, selector de tema y un formulario de contacto.

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

## Estilos e imágenes

Los estilos están separados por responsabilidad en `src/styles/`: `tokens.css` define los temas,
`base.css` contiene los estilos globales, `navigation.css` define navegación y portada,
`sections.css` agrupa servicios, contacto y secciones informativas, `projects.css` contiene el
explorador, y `responsive.css` y `motion.css` atienden adaptación y animaciones. La página principal
importa estos módulos por separado para mantener cada hoja enfocada.

La sección de presencia incluye un mapa de Google Maps centrado en México y Texas, con pines en
Pachuca, Santa Fe, Puerto de Veracruz, Monterrey, Ciudad de México, Guadalajara y Houston. Al
seleccionar un pin, se actualiza una vista de Google Maps centrada en esa ubicación.

El portafolio representa los proyectos web y operativos en equipos portátiles y las aplicaciones
móviles Android en teléfonos, sin tarjetas. GrooveSpace y DeskFlex muestran una sola captura. Las
laptops incluyen una barra de navegador con la dirección de marca del proyecto y un selector de
modelo por proyecto para alternar entre HP y Mac; los teléfonos permiten elegir Android o iPhone
por proyecto. GrooveSpace ocupa el escaparate principal. En móvil, el menú flotante se puede
arrastrar; sus opciones acompañan el movimiento con una onda y se compactan mientras se mueve, sin
mostrar la barra de desplazamiento.

El catálogo de servicios enlaza las áreas de desarrollo web, aplicaciones móviles, operación e
inventario, y reservas con proyectos relacionados del portafolio. Las fichas de proyecto muestran
los íconos y nombres de las tecnologías, además de su estado de lanzamiento cuando está confirmado.

La sección «Nosotros» resume la historia institucional: la fundación en 2011, el origen de la
referencia «It’s Zombie» asociada al nombre IS&BI y la continuidad actual de la misión de crear
software que inspire.

El logotipo institucional está en `public/images/isbi-consultoria-logo.png`. Las capturas de
proyectos del portafolio están en `public/images/solutions/`:

- `public/images/instalaciones.jpeg`
- `public/images/equipo-consultoria.jpg`
- `public/images/oficina.jpeg`
- `public/images/solutions/davila-tours-web.png`
- `public/images/solutions/davila-tours-reservas.png`
- `public/images/solutions/ordersync-ecommerce.png`
- `public/images/solutions/deskflex-reservas.png`
- `public/images/solutions/deskflex-qr-acceso.png`
- `public/images/solutions/groovespace-inicio.png`
- `public/images/solutions/groovespace-estudio.png`
- `public/images/solutions/novatech-landing.png`
- `public/images/solutions/stocktrack-login.png`
- `public/images/solutions/kinder-nahla-mobile.png`
- `public/images/solutions/gavaldoon-go-mobile.png`

Los archivos de `public/` se sirven desde la raíz del sitio; por ejemplo,
`public/images/equipo-consultoria.jpg` se muestra con la ruta `/images/equipo-consultoria.jpg`.

## Formulario de contacto

El formulario usa [Formspree](https://formspree.io/) para recibir consultas sin publicar la dirección
receptora en el HTML. El endpoint público del formulario ya está configurado. Para reemplazarlo
en desarrollo o en el entorno de despliegue, define `PUBLIC_FORMSPREE_ENDPOINT`:

```env
PUBLIC_FORMSPREE_ENDPOINT=https://formspree.io/f/xrpqzkqg
```

El destinatario del aviso del formulario está configurado como `mauricio.garro@ilb.edu.mx`.
Formspree requiere verificar esa dirección desde el correo de confirmación antes de entregar avisos.
El formulario envía el correo del visitante, el asunto y los detalles del proyecto. Para activar la
respuesta automática al visitante, agrega la acción **Auto Response** en **Workflow → Actions**;
Formspree la ofrece en los planes Professional y Business. Para aplicar los colores de IS&BI, crea y
asigna una plantilla HTML de tipo **Autoresponse** desde **Project settings → Templates**, usando
[formspree-autoresponse.html](./docs/emails/formspree-autoresponse.html) y
[formspree-autoresponse.css](./docs/emails/formspree-autoresponse.css). Las plantillas HTML
personalizadas requieren el plan Business. Sin ese plan, configura el mensaje de confirmación en
la acción **Auto Response** cuando esté disponible. Estos cambios se realizan en el panel de
Formspree y no requieren una nueva compilación del sitio.

## Lógica sencilla incluida

- **Interfaz:** diseño responsive con temas claro y oscuro; en móvil, el menú flotante ofrece
  opciones independientes, se puede arrastrar y conserva su posición en el navegador.
- **Explorador de soluciones:** busca por proyecto, descripción o tecnología, y filtra por categoría.
- **Portafolio visual:** incluye capturas de Dávila Tours, OrderSync, DeskFlex, GrooveSpace,
  NovaTech, StockTrack, Kinder Nahla y Gavaldoon Go!
- **Tecnologías y estado:** cada proyecto muestra su stack visualmente y, cuando se conoce, si ya
  fue liberado, está próximo a lanzarse, sigue en preparación o es una propuesta.
- **Animaciones:** transiciones y revelado al desplazarse, respetando la preferencia de movimiento
  reducido del sistema.
- **Formulario:** valida los campos requeridos y envía consultas a Formspree, con
  `mauricio.garro@ilb.edu.mx` como destinatario del aviso; Formspree debe verificar ese correo.
  La autorespuesta y su plantilla HTML se habilitan desde el plan y el panel de Formspree.
