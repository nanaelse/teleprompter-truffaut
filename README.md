# Teleprompter Truffaut

Teleprompter para grabar la serie de videos sobre la filmografía de François Truffaut en español, inglés, francés e italiano. En francés e italiano muestra debajo de cada frase cómo se lee (en rosa) y la fonética IPA (en rojo).

Es una página estática: no necesita servidor, base de datos ni instalar nada.

## Qué hay en el repo

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El teleprompter (diseño y funcionamiento). |
| `guiones.js` | El guion que se ve si todavía no subiste ninguno. |
| `guiones/` | Guiones en `.json`, listos para subir desde la página. |
| `CLAUDE.md` | Instrucciones para que Claude Code agregue guiones con el formato correcto. |

## Probarlo en tu computadora

Abrí `index.html` con doble clic. Funciona en Chrome, Safari y Firefox.

## Publicarlo en internet (GitHub Pages, gratis)

1. Entrá a github.com y creá un repositorio nuevo, por ejemplo `teleprompter`. Puede ser público o privado (para que la página se publique desde un repo privado, GitHub pide un plan pago).
2. En el repo, tocá **Add file → Upload files** y arrastrá los tres archivos: `index.html`, `guiones.js` y `README.md`. Sumá también `CLAUDE.md` si vas a usar Claude Code. Confirmá con **Commit changes**.
3. Andá a **Settings → Pages**. En *Build and deployment* elegí **Deploy from a branch**, la rama **main** y la carpeta **/ (root)**. Guardá.
4. En uno o dos minutos la página queda en `https://TU-USUARIO.github.io/teleprompter/`.

Cada vez que cambies un archivo del repo, la página se actualiza sola en un par de minutos.

**Alternativa sin GitHub:** entrá a app.netlify.com/drop y arrastrá la carpeta entera. Te da un link al instante.

## Cambiar el guion

La página muestra **un solo guion**: el último que subiste.

1. Tocá el título del guion (arriba a la izquierda) y elegí **Subir guion nuevo…**
2. Elegí el archivo `.json` del guion.

El guion queda guardado solo en ese navegador (no hay servidor ni base de datos). Si abrís la página en otra computadora, o borrás los datos del navegador, vas a ver el guion por defecto de `guiones.js` hasta que subas uno.

**Armar el archivo con Claude Code (recomendado):** abrí la carpeta del repo y escribí, por ejemplo:

> Armá un guion nuevo que se llame "El último metro" con este texto: …

Claude lee `CLAUDE.md`, traduce, arma la pronunciación y la IPA, y crea `guiones/el-ultimo-metro.json`. Ese es el archivo que subís.

**A mano:** copiá uno de los `.json` de la carpeta `guiones/`, cambiale el `title` y los textos.

**Desde la página:** el botón del lápiz (editar guion) permite cambiar el texto del guion actual. Esos cambios se guardan solo en el navegador.

## Atajos de teclado

| Tecla | Acción |
|---|---|
| Espacio | Play / pausa |
| ↑ ↓ | Velocidad |
| + − | Tamaño de letra |
| 1 2 3 4 | Español, inglés, francés, italiano |
| R | Volver al inicio |
| M | Espejo |
| F | Pantalla completa |
