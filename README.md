# BITE Burgers

Sitio web estático para presentar **BITE Burgers**, un restaurante ficticio especializado en hamburguesas. El proyecto está hecho principalmente con HTML y CSS, con un pequeño archivo JavaScript para recordar la preferencia del tema visual(dark/light).


### Página principal

En `index.html` se encuentra la presentación del restaurante:

- Una barra de navegación que lleva a las secciones de inicio, menú, información del restaurante y ubicación/contacto.
- Una portada con una imagen de fondo y enlaces para consultar el menú o ir a la página de reservas.
- Un menú con productos organizados en hamburguesas, entrantes, postres y bebidas. Cada tarjeta muestra una imagen, una descripción y un precio.
- Filtros para ver una categoría del menú a la vez. Se implementan con controles HTML y CSS, sin JavaScript.
- Una sección «Sobre nosotros» y un pie de página con horarios, dirección, correo electrónico y teléfono.

### Reservas

- `reservar.html` contiene información sobre las reservas y un formulario que solicita nombre, correo electrónico, teléfono y fecha. Los campos obligatorios usan la validación del navegador.
- Al enviar el formulario se abre `reserva-confirmada.html`, que muestra un mensaje de confirmación y permite volver al inicio.
- El proceso es una demostración: el formulario no envía ni almacena la reserva en un servidor.

### Diseño y tema

- `styles.scss` reúne los estilos compartidos: colores, tipografías, navegación, portada, menú, tarjetas y pie de página. Se compila a `styles.css`.
- `reservar.css` define la presentación del formulario, la confirmación y el pie de las páginas de reserva.
- El diseño se adapta a pantallas estrechas mediante reglas CSS responsive.
- El selector de tema claro/oscuro está en las páginas. `theme.js` guarda la elección en `localStorage` y restaura el estado del selector al volver a cargar la página; las variables y reglas de `styles.css` aplican los colores.

## Archivos y recursos

| Archivo o carpeta | Contenido |
| --- | --- |
| `index.html` | Página principal del restaurante y menú. |
| `reservar.html` | Formulario de reserva de demostración. |
| `reserva-confirmada.html` | Pantalla de confirmación de demostración. |
| `styles.scss` / `styles.css` | Fuente SCSS y CSS compilado para los estilos generales, menú, tema y adaptación responsive. |
| `reservar.css` | Estilos de las páginas de reserva y confirmación. |
| `package.json` | Dependencia de desarrollo Sass y comandos de compilación. |
| `theme.js` | Persistencia de la preferencia de tema en el navegador. |
| `images/` | Fotografías de portada, interior, platos y bebidas. |
| `.vscode/launch.json` | Configuración de VS Code para abrir el sitio en Chrome en `http://localhost:8080`. |

## Tecnologías

- HTML para el contenido y la estructura.
- Sass/SCSS como fuente de estilos, compilado a CSS para el navegador.
- JavaScript para recordar el tema seleccionado.
- Bootstrap 5.3.3, cargado desde jsDelivr, para componentes de navegación.
- Fuentes Archivo Black y DM Sans, cargadas desde Google Fonts.

Bootstrap y Google Fonts se cargan desde internet, por lo que esas dependencias visuales externas requieren conexión. 

## Compilar Sass

Instala las dependencias de desarrollo una vez con `npm install`. Para compilar `styles.scss` a `styles.css`, ejecuta `npm run build:css`. Para abrir la web y recompilar automáticamente al guardar cambios, ejecuta `npm run dev` y visita `http://localhost:8080`. Este comando inicia tanto el vigilante de Sass como el servidor local; compilar Sass por sí solo no sirve la página web. Para detener ambos procesos, pulsa `Ctrl+C`.

La hoja `styles.scss` de la landing incluye el mixin `respond-to` para las reglas responsive y `pill-shape` para los bordes redondeados, además de las funciones propias `space` y `fluid-size`. También utiliza la función nativa de Sass `math.div` para calcular el espaciado.

## W3C CSS VALIDATOR

Después de pasar nuestro archivo styles.css por el W3C CSS VALIDATOR este es el resultado:

<img width="1915" height="917" alt="Validación" src="https://github.com/user-attachments/assets/51352b41-bc1d-4864-b5ee-4255f4e2dbb3" />
