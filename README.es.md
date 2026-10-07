<div align="center">

# Tonu.app

[English](README.md) · [中文](README.zh.md) · Español · [Deutsch](README.de.md) · [Français](README.fr.md)

🌐 **[tonu.app](https://tonu.app)** · [GitHub @frommmmmg](https://github.com/frommmmmg)

</div>

> **Este repositorio es un escaparate, no una publicación de código.** Tonu.app no es de código abierto, así que aquí no hay código: solo qué hace, cómo está construido y qué aspecto tiene. Si quieres hablar de él, escríbeme desde mi [perfil de GitHub](https://github.com/frommmmmg).

**Sube una foto y obtén varias decenas de pósters de paleta al estilo de los feeds de inspiración; elige uno, ajusta cada detalle y guarda el PNG o compártelo.** Todo ocurre en el navegador. No se sube nada salvo que decidas compartirlo.

Los buenos diseñadores guardan una colección privada de paletas. Tonu convierte cualquier imagen de referencia en una. Empezó como generador de pósters y creció hasta ser una pequeña caja de herramientas del color: extraer los colores como los ve el ojo, nombrarlos con honestidad, ajustar el aspecto y llevar la paleta a las herramientas que los diseñadores ya usan.

| | |
|---|---|
| **Sitio web** | **[tonu.app](https://tonu.app)** |
| **Mi papel** | Una persona: producto, interfaz, ciencia del color, front end y un pequeño back end en el borde |
| **Estado** | En producción, 14 idiomas de interfaz |
| **Privacidad** | Las fotos se quedan en el navegador. Guardar nunca sube nada; compartir sube el póster durante 24 horas para crear una página para compartir |
| **Tecnología** | JavaScript puro · OKLab · html-to-image · Cloudflare Workers + KV + D1 |

### Qué hace

**Extraer y nombrar**
- **Extracción de color perceptual.** La imagen se reduce, se convierte a **OKLab**, se agrupa con **k-means++**, se puntúa cada grupo y un muestreo ponderado del punto más lejano elige colores representativos y distintos entre sí.
- **Nombres de color honestos, en tu idioma.** Cada nombre sale de la entrada más cercana en tablas públicas (ISCC-NBS, CSS, Tailwind, Material, xkcd y una gran biblioteca de nombres) por distancia OKLab, sin traducción automática. Incluye sistemas tradicionales como los colores tradicionales japoneses y chinos, y un interruptor ajusta las muestras al valor estándar para que nombre y valor coincidan exactamente.

**Diseñar y ajustar**
- **Un motor de estilos, no una plantilla.** Un estilo es una especificación JSON. **15 motores de diseño, más de 30 preajustes y unos 90 parámetros ajustables**, con ocho diseños circulares, sombras, texturas, acabados, marcos y tratamientos de foto.
- **Arrastra el bloque de colores sobre el póster.** Muévelo libremente o ajústalo a un lado, o fija el desplazamiento exacto con los controles deslizantes. El arrastre empieza tras unos píxeles, así que un toque sigue copiando el valor del color.
- **Pasa el cursor para previsualizar.** Al señalar una opción, se muestra en el póster actual antes de elegirla.
- **Vista previa flotante en el móvil.** Mientras te desplazas por los ajustes, el póster queda en una ventana pequeña que puedes mover, redimensionar y fijar. Con pellizco, rueda del ratón o +/- se amplía como una lupa hasta 8x, para revisar un detalle mientras cambias un valor.
- **Cinco temas de interfaz, cada uno en claro y oscuro:** Sala de pruebas, Pared blanca, Diario de papel, Multicolor y Terminal. **Un panel acoplable** a la izquierda, abajo o a la derecha que recuerda su tamaño. **14 idiomas de interfaz.**

**Exportar y compartir**
- **Exportación idéntica a la pantalla.** Las fuentes se incrustan para que el PNG se vea igual en todas partes, en el móvil se usa el menú nativo de compartir y el trabajo reciente se guarda en el dispositivo.
- **Archivos para las herramientas de diseño.** Adobe Swatch Exchange (`.ase`), Procreate (`.swatches`), GIMP (`.gpl`), W3C Design Tokens y Flutter, todos escritos a mano en el navegador. Copia una paleta como HEX, RGB, HSL, CMYK, LAB, OKLCH o P3, o como variables CSS, SCSS, Tailwind, SwiftUI, Swift o Android XML.
- **Enlaces e importación de paletas.** Un enlace como `tonu.app/#b2e1e7-4893b2` reabre una paleta, y Tonu lee enlaces de Coolors o una lista simple de valores HEX.
- **Informe de accesibilidad.** Una matriz de contraste WCAG para cada par de colores, guardada como tarjeta PNG.
- **Gestión de fuentes bien hecha.** 12 fuentes de licencia abierta incluidas, más tus propios archivos, URLs o fuentes instaladas, con la responsabilidad de licencia indicada con claridad.

## Capturas

![La galería: una foto, muchos estilos de póster.](assets/tonu-gallery.jpg)
*La galería: una foto, muchos estilos de póster.*

![La vista grande. El panel de ajustes sigue activo a su lado.](assets/tonu-focus.jpg)
*La vista grande. El panel de ajustes sigue activo a su lado.*

<table><tr><td align="center" width="33%"><img src="assets/tonu-skin-default.jpg" alt="Sala de pruebas"><br><sub>Sala de pruebas</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-white.jpg" alt="Pared blanca"><br><sub>Pared blanca</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-paper.jpg" alt="Diario de papel"><br><sub>Diario de papel</sub></td></tr><tr><td align="center" width="33%"><img src="assets/tonu-skin-multicolor.jpg" alt="Multicolor"><br><sub>Multicolor</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-terminal.jpg" alt="Terminal"><br><sub>Terminal</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-multicolor-dark.jpg" alt="Multicolor, oscuro"><br><sub>Multicolor, oscuro</sub></td></tr></table>

*Cinco temas de interfaz, cada uno con modo claro y oscuro.*

![Arrastra el bloque de colores a cualquier punto del póster.](assets/tonu-drag.jpg)
*Arrastra el bloque de colores a cualquier punto del póster.*

![En el móvil: la galería, la vista previa flotante sobre los ajustes y la vista previa ampliada al 338%.](assets/tonu-mobile.jpg)
*En el móvil: la galería, la vista previa flotante sobre los ajustes y la vista previa ampliada al 338%.*

<table><tr><td align="center" width="50%"><img src="assets/tonu-dock-bottom.jpg" alt="Abajo"><br><sub>Abajo</sub></td><td align="center" width="50%"><img src="assets/tonu-dock-left.jpg" alt="Izquierda"><br><sub>Izquierda</sub></td></tr></table>

*El panel acoplado abajo y a la izquierda.*

![La misma pantalla en cuatro de los 14 idiomas de interfaz. Los nombres de color siguen el idioma, por ejemplo los colores tradicionales japoneses.](assets/tonu-languages.jpg)
*La misma pantalla en cuatro de los 14 idiomas de interfaz. Los nombres de color siguen el idioma, por ejemplo los colores tradicionales japoneses.*

## Cómo funciona

![Un cambio actualiza a la vez la galería, la vista grande y la vista previa flotante.](assets/tonu-live-sync.svg)
*Un cambio actualiza a la vez la galería, la vista grande y la vista previa flotante.*

![Todo, desde la extracción de color hasta la exportación, se ejecuta en el navegador.](assets/tonu-extraction-pipeline.svg)
*Todo, desde la extracción de color hasta la exportación, se ejecuta en el navegador.*

![Los estilos son especificaciones JSON que los motores de diseño convierten en pósters.](assets/tonu-style-engine.svg)
*Los estilos son especificaciones JSON que los motores de diseño convierten en pósters.*

<!--notes-->
## Notas de ingeniería

- **Sin back end para lo esencial.** La extracción de color, los nombres, el renderizado y todas las exportaciones se ejecutan en el cliente. Un pequeño Worker con KV y D1 existe solo para las páginas de compartir, y el editor se sirve como archivos estáticos, por lo que usarlo no consume peticiones del Worker.
- **Formatos de archivo escritos a mano.** El binario `.ase` de Adobe y el archivo `.swatches` de Procreate (un zip con un JSON, con el hash del perfil de color comprobado contra un archivo real de Procreate) se generan sin librerías.
- **Un renderizado por fotograma.** Arrastrar un control deslizante puede disparar eventos más rápido que la pantalla, así que el póster activo se vuelve a renderizar como mucho una vez por fotograma, y la galería, la vista grande y la vista flotante se actualizan con el mismo cambio.
- **Temas que no cuestan nada hasta que se usan.** Cada tema de interfaz es una hoja de estilos acotada que se descarga la primera vez que se elige. El tema de un visitante recurrente se carga durante la carga de la página, reteniéndola un instante para que el tema por defecto no parpadee primero. Los pósters nunca se reestilizan.
- **Internacionalización ligera.** El inglés está escrito en el HTML, los demás idiomas son archivos de script que se piden bajo demanda, funcionan enlaces como `?lang=` y un script de comprobación avisa de claves que faltan.
- **Honesto sobre sus límites.** Las traducciones de la interfaz son automáticas y aún no las han revisado diseñadores nativos, y así lo dicen las propias notas del proyecto.

**Otras muestras:** [AffProof](https://github.com/frommmmmg/AffProof-showcase) · [AutoPin-CS](https://github.com/frommmmmg/AutoPin-CS-showcase) · [AffiliateScraper](https://github.com/frommmmmg/AffiliateScraper-showcase)

---

<div align="center">

<sub>Las capturas usan solo datos de ejemplo o públicos. © Todos los derechos reservados. Las descripciones pueden citarse con atribución; el software no se puede redistribuir.</sub>

</div>
