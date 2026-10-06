<div align="center">

# Tonu.app

[English](README.md) · [中文](README.zh.md) · Español · [Deutsch](README.de.md) · [Français](README.fr.md)

</div>

> **Este repositorio es un escaparate, no una publicación de código.** Tonu.app es un proyecto privado, así que aquí no hay código: solo qué hace, cómo está construido y qué aspecto tiene. Si quieres hablar de él, escríbeme desde mi [perfil de GitHub](https://github.com/frommmmmg).

**Sube una foto y obtén varias decenas de pósters de paleta al estilo de los feeds de inspiración; elige uno, ajusta cada detalle y guarda el PNG o compártelo.** Todo ocurre en el navegador. No se sube nada salvo que decidas compartirlo.

**Puntos clave**

- **Extracción de color perceptual.** La imagen se reduce, se convierte a **OKLab**, se agrupa con **k-means++**, se puntúa cada grupo y un muestreo ponderado del punto más lejano elige colores representativos y distintos entre sí.
- **Nombres de color honestos, en tu idioma.** Los nombres salen de la entrada más cercana en tablas públicas (ISCC-NBS, CSS, Tailwind, Material, xkcd) por distancia OKLab, sin traducción automática. Incluye sistemas tradicionales como los colores tradicionales japoneses y chinos.
- **Un motor de estilos, no una plantilla.** Un estilo es una especificación JSON. **15 motores de diseño, más de 30 preajustes y unos 90 parámetros ajustables**, con ocho diseños circulares, sombras, texturas, acabados, marcos y tratamientos de foto.
- **Arrastra el bloque de colores sobre el póster.** Muévelo libremente o ajústalo a un lado, o fija el desplazamiento exacto con los controles deslizantes. El arrastre empieza tras unos píxeles, así que un toque sigue copiando el valor del color.
- **Vista previa flotante en el móvil.** Mientras te desplazas por los ajustes, el póster queda en una ventana pequeña que puedes mover, redimensionar y fijar. Con pellizco, rueda del ratón o +/- se amplía como una lupa hasta 8x, para revisar un detalle mientras cambias un valor.
- **Pasa el cursor para previsualizar.** Al señalar una opción, se muestra en el póster actual antes de elegirla.
- **Cinco temas de interfaz, cada uno en claro y oscuro:** Sala de pruebas, Pared blanca, Diario de papel, Multicolor y Terminal. Se cargan bajo demanda y solo cambian la interfaz, nunca los pósters.
- **Un panel acoplable.** Colócalo a la izquierda, abajo o a la derecha, cambia su tamaño arrastrando el borde y la elección se recuerda en el dispositivo.
- **14 idiomas de interfaz.**
- **Exportación idéntica a la pantalla.** Las fuentes se incrustan para que el PNG se vea igual en todas partes, en el móvil se usa el menú nativo de compartir y el trabajo reciente se guarda en el dispositivo.
- **Gestión de fuentes bien hecha.** 12 fuentes de licencia abierta incluidas, más tus propios archivos, URLs o fuentes instaladas, con la responsabilidad de licencia indicada con claridad.

**Tecnología:** JavaScript puro · OKLab · html-to-image · Cloudflare Workers + KV + D1 para los pósters compartidos

En línea en **[tonu.app](https://tonu.app)**. La foto de muestra de las capturas es de Andrés Beltrán Espinosa en Unsplash.

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

---

<div align="center">

<sub>Las capturas usan solo datos de ejemplo o públicos. © Todos los derechos reservados. Las descripciones pueden citarse con atribución; el software no se puede redistribuir.</sub>

</div>
