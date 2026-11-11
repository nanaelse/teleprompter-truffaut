# Teleprompter Truffaut: instrucciones para Claude

Página estática (sin build). `index.html` tiene el teleprompter; `guiones.js` tiene los textos en `window.GUIONES`.
No hace falta tocar `index.html` para agregar guiones.

## Cuando Nana pasa un texto nuevo

1. Agregá un objeto nuevo **al final** de `window.GUIONES` en `guiones.js` (el último abre por defecto):
   `{ title, es: [...], en: [...], fr: [[...], ...], it: [[...], ...] }`
2. `title`: el nombre que Nana le dé al texto.
3. `es`: el texto de Nana tal como lo dijo. Solo corregí puntuación y errores claros de dictado, y avisale cuáles corregiste.
4. `en`, `fr`, `it`: traducción natural, con el tono hablado y cercano de Nana, no literal. Los títulos de películas van con su nombre oficial en cada idioma (ej.: *La mariée était en noir*, *La sposa in nero*, *The Bride Wore Black*).
5. Al terminar, resumí en el chat las decisiones de traducción que conviene revisar.

## Cortes de línea

- Cada frase se corta en fragmentos cortos con ` | ` (unos 25–45 caracteres), en pausas naturales: comas, conectores, cambio de idea.
- Cada fragmento se ve en UNA sola línea. Si no entra en el ancho, la página lo achica sola.
- En `fr` e `it` cada frase es un bloque de tres textos: `[texto, pronunciación, IPA]`. Los tres tienen que tener **exactamente la misma cantidad de cortes ` | `**, en los mismos puntos.

## Línea de pronunciación (rosa)

Escrita para alguien que habla español rioplatense:

- Tildes en la sílaba tónica.
- **y** = "y/ll" porteña, sirve para el francés /ʒ/ (je → "ye", jour → "yur").
- **sh** = /ʃ/ (chose → "shos").
- **ü** = /y/ francesa (vu → "vü"); **ö** = /ø/ y /œ/ (peu → "pö", -teur → "tör").
- Nasales francesas: "an", "on", "an/in" sin pronunciar la n (dans → "dan", bon → "bon").
- Italiano: **guion** para consonantes dobles (tut-to, ap-péna); **dy** = /dʒ/ (giorno → "dyórno"); **ch** = /tʃ/; **ñ** = /ɲ/; "lio" = /ʎʎ/ (voglio → "vólio").
- Liaisons francesas pegadas: "vusán", "an naryantín".

## Línea de fonética (rojo)

- IPA real entre barras `/.../`, con puntos de sílaba en francés (`/bɔ̃.ʒuʁ/`) y marca de acento `ˈ` en italiano (`/ˈtʃa.o/`).
- Francés: /ʁ/ para la r, ‿ para las liaisons, nasales /ɑ̃ ɔ̃ ɛ̃ œ̃/.
- Italiano: consonantes dobles en IPA (/ˈtut.to/), /dʒ tʃ ʎ ɲ/ según corresponda.

## Verificar antes de terminar

```bash
node -e "global.window={};require('./guiones.js');for(const g of window.GUIONES)for(const l of['fr','it'])g[l].forEach((b,n)=>{const c=b.map(x=>x.split('|').length);if(new Set(c).size>1)console.log('cortes distintos:',g.title,l,'frase',n+1,c)});console.log('ok')"
```

Tiene que imprimir solo `ok`.
