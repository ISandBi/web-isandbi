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

## Imágenes

Las capturas de proyectos compartidas para el portafolio y las ilustraciones de escalamiento e IA
están en `public/images/solutions/`. Las fotografías de portada se guardan en `public/images/`:

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
- `public/images/solutions/kinder-nahla-mobile.png`
- `public/images/solutions/gavaldoon-go-mobile.png`

Los archivos de `public/` se sirven desde la raíz del sitio; por ejemplo,
`public/images/equipo-consultoria.jpg` se muestra con la ruta `/images/equipo-consultoria.jpg`.

## Formulario de contacto

El formulario usa [Formspree](https://formspree.io/) para recibir consultas sin publicar la dirección
receptora en el HTML. Copia `.env.example` como `.env` y configura el endpoint de tu formulario:

```env
PUBLIC_FORMSPREE_ENDPOINT=https://formspree.io/f/tu-id
```

El endpoint se obtiene al crear el formulario en Formspree. Debe estar configurado al compilar
(`npm run build`); sin él, el botón de envío permanece desactivado. El campo de correo permite
escribir el usuario y elegir `@gmail.com` o `@hotmail.com`.

## Lógica sencilla incluida

- **Tema claro:** el sitio usa una sola paleta clara.
- **Portafolio:** los proyectos destacados enlazan a sus repositorios públicos.
- **Explorador de soluciones:** presenta los nueve repositorios públicos de IS&BI y dos propuestas
  de proyecto descritas en el portafolio interno. Incluye búsqueda por nombre, descripción o
  tecnología y filtros por especialidad; las propuestas sin repositorio enlazan al contacto.
- **Descripciones del portafolio:** los alcances de Dávila Tours, OrderSync, Kinder Nahla,
  Gavaldoon Go!, StockTrack, NovaTech, GrooveSpace, LinguaPro, DeskFlex y SafeCloud se basan en
  los documentos de agosto, septiembre y octubre de 2026.
- **OrderSync:** imagen de portada propia y tecnología Angular 20.
- **GrooveSpace:** capturas de portada y catálogo; aplicación desarrollada con React.
- **Kinder Nahla y Gavaldoon Go!:** incluyen sus imágenes en el explorador y muestran Android Studio
  como entorno de desarrollo.
- **Animaciones al desplazarse:** las secciones aparecen al entrar en pantalla y respetan la
  preferencia de movimiento reducido del navegador. Los degradados, tarjetas y navegación también
  cuentan con transiciones adaptadas a pantallas móviles.
- **Envío del formulario:** los campos obligatorios se validan en el navegador y las consultas se
  envían al endpoint configurado de Formspree.
