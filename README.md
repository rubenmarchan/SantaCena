# Santa Cena — transmisión en vivo

Página estática de una sola pantalla para la transmisión diaria. Solo HTML y CSS,
sin JavaScript y sin dependencias que compilar.

```
index.html    la página
styles.css    los estilos
```

## Cambiar el video de cada día

Abre `index.html` y busca el bloque marcado **VIDEO DEL DÍA**. Reemplaza
`VIDEO_ID` por el identificador del video de hoy:

```html
<iframe src="https://www.youtube-nocookie.com/embed/VIDEO_ID" ...>
```

El identificador es la parte que sigue a `v=` en el enlace de YouTube:

```
https://www.youtube.com/watch?v=dQw4w9WgXcQ
                                └─── esto ───┘
```

Es lo único que cambia cada día.

### Alternativa: que no haya que editar nada

Si la transmisión siempre sale del mismo canal, usa esta dirección y YouTube
mostrará solo lo que esté en vivo en ese canal:

```html
<iframe src="https://www.youtube-nocookie.com/embed/live_stream?channel=ID_DEL_CANAL" ...>
```

El `ID_DEL_CANAL` empieza con `UC…` y se encuentra en la configuración avanzada
del canal. La contrapartida: cuando no hay transmisión activa el reproductor
aparece vacío, así que para un evento con fecha fija el ID de video es más
seguro.

## Textos que conviene revisar

En `index.html`:

- **`8:00 PM`** en la sección *Horario* — es un valor de ejemplo, ponle la hora real.
- **`Hoy`** junto a *En vivo* — si prefieres una fecha concreta, escríbela ahí.
- El pie de página.

## Publicar con GitHub Pages

En el repositorio: **Settings → Pages → Source: Deploy from a branch**, rama
`main`, carpeta `/ (root)`. La página queda en
`https://rubenmarchan.github.io/SantaCena/` en un par de minutos.

## Notas de diseño

- Azul noche `#04182b`, azul de marca `#082746`, oro `#cbb058`, lino `#f7f5f1`.
- Tipografías Cinzel (título) y Karla (texto), desde Google Fonts.
- El único elemento con brillo es el marco del video: la transmisión es lo que
  ilumina la página. Todo lo demás se mantiene apagado a propósito.
- Se adapta a móvil, respeta `prefers-reduced-motion` y usa `youtube-nocookie`
  para no dejar cookies de seguimiento antes de que alguien le dé play.
