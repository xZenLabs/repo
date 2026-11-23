# v.1.1.6 · 2026-11-23

# Glow-up sesh + Atsumaru! Shiny covers, markers and a new source (AVIF not included 😔)
`v.1.1.6`

[English](#english) · [Español](#español)

---

## English

### Atsumaru

New site: loads of English manga and manhwa. The website is behind Cloudflare but its API isn't, so it works fine from the plugin.
Heads-up: lots of newer chapters only come as AVIF images, which KOReader can't show yet (see below). A chapter often has uploads from several groups, so if one is AVIF, look for the same chapter number in the list; another upload might be WebP, which works.

### Warning for pages KOReader can't show

Before downloading or queueing, the plugin now checks the page format on any site. If a chapter is AVIF, HEIC or JPEG XL, it tells you and lets you cancel, skip it, or download it anyway and convert it yourself on a PC.
When downloading several chapters or running the queue, you're only asked once.
AVIF support in KOReader itself is tracked in koreader/koreader#10973.

### Prettier library

- Reading progress is now a bar on the cover, read comics get a ✓ badge, and titles show their chapter count in the corner.
- Collections look like a pile of covers, with a bold name, so they don't look like just another book.
- Long titles no longer get mangled by brackets and percentages.

### KOReader collections

Hold a comic, a title or a collection in the Library and tap "KOReader collections..." to add them to KOReader's own collections (Favorites and the rest). Needs KOReader 2024.04 or newer.

### Other

- The adult content notice is now a black banner at the top, next to the X, instead of a bubble at the bottom.
- `_template.lua` has been rewritten: you can add a site by filling in blanks, no programming needed.
- New `potential_sources.md`: every site people have asked for, and whether it can be added (short version: it needs a simple open API).
- Both READMEs (English and Spanish) are updated, with a changelog at the top.

### Upgrading

Copy the new `APIKOmicReader.koplugin` folder over the old one and restart KOReader. Your library, bookmarks, queue and settings are kept.

---

## Español

### Atsumaru

Nueva web: una gran cantidad de manga y manhwa en inglés. La web está detrás de Cloudflare, pero su API no, así que funciona sin problemas desde el plugin.
Aviso: muchos de los capítulos más recientes solo están disponibles en imágenes AVIF, que KOReader todavía no puede mostrar (ver más abajo). Muchos capítulos tienen subidas de varios grupos, así que si uno está en AVIF, busca el mismo número de capítulo en la lista; es posible que otra subida esté en WebP, que sí funciona.

### Aviso para páginas que KOReader no puede mostrar

Antes de descargar o añadir algo a la cola, el plugin comprueba el formato de las páginas, en cualquier web. Si un capítulo está en AVIF, HEIC o JPEG XL, te avisa y puedes cancelar, omitirlo o descargarlo de todos modos y convertirlo en el PC.
Al descargar varios capítulos o al procesar la cola, solo se pregunta una vez.
El soporte para AVIF en KOReader se sigue en koreader/koreader#10973.

### Biblioteca mejorada

- El progreso de lectura ahora se muestra como una barra en la portada, los cómics leídos llevan una insignia con ✓ y los títulos muestran en la esquina cuántos capítulos tienen.
- Las colecciones se muestran como un montón de portadas, con el nombre en negrita, para distinguirlas de los demás títulos.
- Los títulos largos ya no se ven afectados por corchetes y porcentajes.

### Colecciones de KOReader

Mantén pulsado un cómic, un título o una colección en la Library y toca "KOReader collections..." para añadirlos a las colecciones de KOReader (Favoritos y las demás). Requiere KOReader 2024.04 o posterior.

### Otros cambios

- El aviso de contenido adulto ahora es una franja negra en la parte superior, junto a la X, en lugar de un recuadro en la parte inferior.
- `_template.lua` se ha reescrito: puedes añadir una web rellenando campos, sin necesidad de programar.
- Nuevo `potential_sources.md` (en inglés): todas las webs que se han solicitado, y si se pueden añadir o no (en resumen: necesitan una API abierta y sencilla).
- Los dos README (inglés y español) están actualizados, con un registro de cambios al principio.

### Actualizar

Copia la nueva carpeta `APIKOmicReader.koplugin` sobre la anterior y reinicia KOReader. Tu biblioteca, marcadores, cola y ajustes se conservan.

# v.1.1.3 · 2026-11-06

What’s new

Download queue

Line up whole titles or single chapters and download them in one go. Add from a result’s long-press menu, a title’s details, or the chapter list.
A “Queue” button appears on the home screen, with a banner in the grid and list views.
You can reorder entries (move to top), remove them, or clear the queue.
The queue survives restarts. Failed titles stay marked “failed” and are retried next time.

Parallel downloads

Pages now download several at a time, which is much faster.
Set the number in Settings > Parallel page downloads (1–6, default 3). Setting it to 1 gives the old one-at-a-time behaviour.

Stays awake while downloading

The device no longer sleeps or loses Wi-Fi in the middle of a chapter, a bulk download or the queue.

Library overhaul

Chapters are now grouped by title, so one manga is one entry.
Each chapter shows unread, half-read (with a percentage) or read (✓).
Collections: make your own groups of titles. You can rename and delete them, and deleting one never deletes comics.
Sorting for the library (Recently added, Oldest first, Name A–Z/Z–A, Continue reading, Unread first, Read first) and for the chapters of a title (Chapter order, Newest first, Continue reading, Unread first). Your choice is remembered.
“Delete all chapters” removes a whole title at once.

Other

Adult content in the queue and library respects the parental controls and PIN.
Both READMEs (English and Spanish) are updated to match.

Upgrading: copy the new APIKOmicReader.koplugin folder over the old one and restart KOReader. Your existing library, bookmarks and settings are kept. Older library files are grouped by the title in their file name until they’re re-downloaded. Iv'e also seen it appear already in Storefront, so you might just be able to update it through there.

# v.1.0.0 · 2026-11-06

# APIKOmicReader v1.0

[English](#english) · [Español](#español)

---

## English

First release! APIKOmicReader is a KOReader plugin for finding and reading manga and comics straight from the internet on your e-reader. No PC, no copying files around. Search, tap and read.

### What's in it

**Sites**
- **MangaDex**: loads of manga in lots of languages, with chapter lists.
- **Internet Archive**: Western comics uploaded to archive.org, limited to uploads that actually contain CBZ/CBR files. Paste an archive.org link to open an upload directly.
- **nhentai**: 18+, hidden by default (yes, I know, see the README).
- **Add your own**: drop a single `.lua` file in `apiko/sources/` and restart KOReader. There's a template to start from.

**Reading and browsing**
- Home screen with search bar, site picker and quick tiles.
- Results as a grid with covers, a list with covers or a plain list.
- Chapter lists with markers for what you've already downloaded or saved.
- "Download all chapters" and "Download a range" for whole series.
- Data saver images on MangaDex, and a language setting for chapters.
- Back arrow everywhere, and closing a comic takes you back to where you were.

**Keeping things**
- **Library** for comics you want to keep for good.
- **History** for what you've read lately (keeps the last 20 by default).
- **Bookmarks** for titles you want to read later.
- **Saved searches** and **Recent** searches.
- Everything is stored per site, in a hidden folder, and kept out of KOReader's own reading history.

**Parental controls**
- Adult content is hidden by default: adult sites don't show up and MangaDex only returns all-ages titles.
- Long-press the logo to show it. The logo blushes and a warning stays on screen while it's visible.
- Optional PIN, asked before showing adult content. Everything locks again when you leave the plugin or the device sleeps.

**Extras**
- Switches on [Panels+](https://github.com/KristanLaimon/PanelsPlus) automatically when you open a comic, if you have it.
- Brings its own icon for the [ZenOS](https://github.com/xZenLabs/zen-os) launcher.
- Windows installer (`unsetup.bat`) that copies the plugin to a USB-connected Kindle, including newer Kindles that connect over MTP.

### Installing

Download `APIKOmicReader.koplugin` from this release, copy it into `koreader/plugins/` on your e-reader and restart KOReader. Or plug in your Kindle and run `unsetup.bat` on Windows. Then open it from Tools > APIKOmicReader.

### Good to know

- Some Wi-Fi networks (work, school) block these sites. A phone hotspot usually works.
- The Internet Archive has no age ratings, so the adult filter can't hide anything there, and its pages only come in original quality.
- The PIN locks the plugin on the device. It doesn't encrypt the downloaded files.
- Found a bug? Open an issue and include the lines starting with `APIKOmic:` from `koreader/crash.log`.

---

## Español

¡Primera versión! APIKOmicReader es un plugin de KOReader para buscar y leer manga y cómics directamente de internet en tu lector. Sin PC y sin andar pasando archivos. Buscas, tocas y a leer.

### Qué trae

**Webs**
- **MangaDex**: mazo de manga en un montón de idiomas, con lista de capítulos.
- **Internet Archive**: cómics occidentales subidos a archive.org, solo las subidas que tienen archivos CBZ/CBR de verdad. Pega un enlace de archive.org para abrir una subida directamente.
- **nhentai**: +18, oculto por defecto (sí, ya lo sé, mira el README).
- **Añade las tuyas**: mete un solo archivo `.lua` en `apiko/sources/` y reinicia KOReader. Hay una plantilla para empezar.

**Leer y cotillear**
- Pantalla de inicio con barra de búsqueda, selector de web y accesos rápidos.
- Resultados en cuadrícula con portadas, lista con portadas o lista simple.
- Listas de capítulos que marcan lo que ya te has bajado o guardado.
- "Download all chapters" y "Download a range" para series enteras.
- Imágenes en modo ahorro de datos en MangaDex, y ajuste de idioma para los capítulos.
- Flecha para volver en todas partes, y al cerrar un cómic vuelves a donde estabas.

**Guardarte cosas**
- **Library** para los cómics que te quieres quedar para siempre.
- **History** para lo último que has leído (guarda los últimos 20 por defecto).
- **Bookmarks** para lo que quieres leer más adelante.
- Búsquedas guardadas (**Saved searches**) y recientes (**Recent**).
- Todo se guarda por web, en una carpeta oculta, y no sale en el historial de lectura de KOReader.

**Control parental**
- El contenido adulto viene oculto por defecto: las webs para adultos no aparecen y MangaDex solo da títulos para todos los públicos.
- Mantén pulsado el logo para mostrarlo. El logo se pone colorado y sale un aviso mientras está visible.
- PIN opcional, que se pide antes de mostrar el contenido adulto. Todo se vuelve a bloquear al salir del plugin o cuando el lector se bloquea.

**Extras**
- Activa [Panels+](https://github.com/KristanLaimon/PanelsPlus) solo al abrir un cómic, si lo tienes instalado.
- Trae su propio icono para el lanzador [ZenOS](https://github.com/xZenLabs/zen-os).
- Instalador para Windows (`unsetup.bat`) que copia el plugin a un Kindle enchufado por USB, también los Kindle nuevos que se conectan por MTP.

### Instalación

Bájate `APIKOmicReader.koplugin` de esta versión, cópialo en `koreader/plugins/` del lector y reinicia KOReader. O enchufa el Kindle y ejecuta `unsetup.bat` en Windows. Luego ábrelo desde Herramientas > APIKOmicReader.

### Conviene saber

- Algunas redes wifi (la del curro, la de clase) bloquean estas webs. Compartiendo datos desde el móvil suele ir.
- El Internet Archive no tiene clasificación por edades, así que el filtro adulto no puede ocultar nada ahí, y las páginas solo vienen en calidad original.
- El PIN bloquea el plugin en el lector. No cifra los archivos descargados.
- ¿Has encontrado un fallo? Abre un issue y pon las líneas que empiezan por `APIKOmic:` de `koreader/crash.log`.
