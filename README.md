# Teleprompter Truffaut

Teleprompter para grabar la serie de videos sobre la filmografía de François Truffaut en español, inglés, francés e italiano. En francés e italiano muestra debajo de cada frase cómo se lee (en rosa) y la fonética IPA (en rojo).

Es una página estática: no necesita servidor, base de datos ni instalar nada.

## Qué hay en el repo

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El teleprompter (diseño y funcionamiento). |
| `guiones.js` | Los textos. Acá se agregan los guiones nuevos. |
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

## Agregar un guion nuevo

**Con Claude Code (recomendado):** abrí la carpeta del repo y escribí, por ejemplo:

> Agregá un guion nuevo que se llame "El último metro" con este texto: …

Claude lee `CLAUDE.md`, traduce, arma la pronunciación y la IPA, y lo suma a `guiones.js`.

**A mano:** copiá uno de los bloques de `guiones.js`, cambiale el `title` y los textos, y pegalo al final de la lista. El último guion de la lista es el que abre por defecto. Los demás se eligen desde el título, arriba a la izquierda.

**Desde la página:** el botón del lápiz (editar guion) permite cambiar el texto sin tocar archivos. Esos cambios se guardan solo en el navegador que estés usando, no en el repo.

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
